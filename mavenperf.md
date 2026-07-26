Maven Performance Mind Map
==========================

[mvnflight](https://github.com/jeanbisutti/mvnflight)

- measure build: 5 [extensions](https://maven.apache.org/extensions/index.html) profiler, Takari profiler, opentelemetry-maven-extension, jfr-maven-extension, maven-timeline
  - Maven extensions [study](https://maven.apache.org/studies/extension-demo/):
    - `pom.xml` `project.build.extensions`,
    - 3.3.1+ project's `.mvn/extensions.xml`,
    - 3.10+ user's `~/m2/extensions.xml` or install's `{maven.home}/conf/extensions.xml`
  - investiguer l'overhead des extensions
- options to improve build:
  - TBD: dev workflow vs CI
  - fastbuild vs with UT vs with UT & ITs, doc/site
  - dependency cache
  - parallel, w/o or with smart-builder
  - mvnd
  - build cache (rebuild avoidance)
- real builds to test:
  - [Modello](https://github.com/codehaus-plexus/modello): [GHA](https://github.com/codehaus-plexus/modello/actions/workflows/maven.yml)
  - [Quarkus](https://github.com/quarkusio/quarkus): [GHA](https://github.com/quarkusio/quarkus/actions) uses Develocity
  - [Keycloak](https://github.com/keycloak/keycloak): TODO test GHA like [CI workflow on main](https://github.com/keycloak/keycloak/actions/workflows/ci.yml?query=branch%3Amain)
- investigations:
  - Surefire fork (safe process isolation) vs in-process
  - overhead of mvnflight
- improvements:
  - ~~beginning mvnflight: build summary (packaging)~~
  - ~~end mvnflight: report size, build summary~~
  - dependency cache
- how to compare 2 measures, to see where improvement have happened?

## Publication

External consumption requires public publication, while keeping source private.

Many options available, with their own complexities:

1. Maven Central [SNAPSHOT](https://central.sonatype.org/publish/publish-portal-snapshots/): see [namespace](https://central.sonatype.org/register/namespace/#by-code-hosting-services), require [GH `mvnflight` org](https://github.com/mvnflight) to be able to deploy to `io.github.mvnflight`
2. [GitHub packages](https://docs.github.com/en/packages/working-with-a-github-packages-registry/working-with-the-apache-maven-registry): how to have public package while keeping Git private?
3. Jitpack.io: [price](https://jitpack.io/private#subscribe) for private Git
4. any web server, like https://jeanbisutti.github.io/mvnflight, at least for SNAPSHOT, waiting for a decision for future releases?
   for example site publishing `target/repo` from `mvn clean deploy -DaltDeploymentRepository=local::file:target/repo`
   Manual deployment done as a POC to https://github.com/hboutemy/mvnflight/tree/gh-pages
