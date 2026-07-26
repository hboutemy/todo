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
- public publication, while keeping source private:
  - Maven Central SNAPSHOT:
  - GitHub packages: 
  - Jitpack.io: [price](https://jitpack.io/private#subscribe)
  - any web server...
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
