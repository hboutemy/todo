https://github.com/google/oss-rebuild

bucket gs://google-rebuild-metadata

## liste
- `oss-rebuild get pypi a`
- `oss-rebuild get npm a`
- `oss-rebuild get crates.io a`

```
$ oss-rebuild get pypi absl-py 2.0.0
NOTE:  artifact is being inferred as "absl_py-2.0.0-py3-none-any.whl"
Rebuild found!
Rebuilt at: "2024-05-17T01:13:42Z"
Upstream target: https://files.pythonhosted.org/packages/01/e4/dc0a1dcc4e74e08d7abedab278c795eef54a224363bb18f5692f416d834f/absl_py-2.0.0-py3-none-any.whl
Upstream target digest: {"sha256":"9a28abb62774ae4e8edbe2dd4c49ffcd45a6a848952a5eccc6a49f3f0fc1e2f3"}
Dockerfile: |-
  #syntax=docker/dockerfile:1.4
  FROM gcr.io/cloud-builders/gsutil AS timewarp_provider
  RUN gsutil cp -P gs://google-rebuild-bootstrap-tools/timewarp .
  FROM alpine:3.19
  COPY --from=timewarp_provider ./timewarp .
  RUN <<'EOF'
   set -eux
   ./timewarp -port 8080 &
   while ! nc -z localhost 8080;do sleep 1;done
   apk add git python3
   mkdir /src && cd /src
   git clone 'https://github.com/abseil/abseil-py' .
   git checkout --force '37dad4d356ca9e13f1c533ad6309631b397a2b6b'
   /usr/bin/python3 -m venv /deps
   /deps/bin/pip install build
   /deps/bin/pip install wheel==0.41.2
   /deps/bin/pip install setuptools==67.7.2

  EOF
  RUN cat <<'EOF' >build
   set -eux
   /deps/bin/python3 -m build --wheel -n
   mkdir /out && cp /src/dist/absl_py-2.0.0-py3-none-any.whl /out/
  EOF
  WORKDIR "/src"
  ENTRYPOINT ["/bin/sh","/build"]
```

```
oss-rebuild get pypi absl-py 2.0.0 --output=dockerfile \
| docker run $(docker buildx build -q -)
```

## Airflow
https://downloads.apache.org/airflow/providers/ vs PyPI https://pypi.org/search/?q=apache-airflow-providers

source: https://github.com/apache/airflow/tree/main/providers
