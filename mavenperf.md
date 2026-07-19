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
  - fastbuild vs with UT vs with UT & ITs
  - dependency cache
  - parallel, w/o or with smart-builder
  - mvnd
  - build cache (rebuild avoidance)
- real builds to test:
  - Modello ()
  - Quarkus
  - Keycloak: TODO test GHA
- investigations:
  - Surefire fork (safe process isolation) vs in-process
  - overhead of mvnflight
- improvements:
  - beginning mvnflight: build summary (packaging)
  - end mvnflight: report size, build summary
  - dependency cache
