My Maven TODO list
=========

<details><summary>past</summary>

## Core 3.5.x
<details><summary>details</summary>

- ~~jansi [1.7.1 release](https://github.com/fusesource/jansi/issues/114)~~
- ~~[MNG-6411](https://issues.apache.org/jira/browse/MNG-6411) readability of available modules~~
- ~~[MNG-6410](https://issues.apache.org/jira/browse/MNG-6410) multiple modules with same artifactId~~
</details>

## Core 3.6
<details><summary>3.6.0</summary>

- ~~[MNG-5951](https://issues.apache.org/jira/browse/MNG-5951) add an option to avoid path addition to inherited URLs~~
  - more flexible idea would be to have multiple strategies with a Plexus role and multiple hints:
    by default, appends artifactId (or project.directory) like currently, another would not add anything (hint id to be found),
    another hint could work with git specific url rules. Interface = `String getInheritedUrl( String parentUrl, MavenProject parent, MavenProject child )`
    issue: this would create a dependency on Plexus container/Sisu
- ~~[MNG-4508](https://issues.apache.org/jira/browse/MNG-4508) No way to avoid adding artifactId to site urls~~
</details>

<details><summary>3.6.1</summary>

- ~~[MNG-6059](https://issues.apache.org/jira/browse/MNG-6059) Important use cases not covered, as child.inherit.append.path affects all children~~
- ~~[MNG-6505](https://issues.apache.org/jira/browse/MNG-6505) inheritance~~
- OSSRH & others Nexus staging controls for new attributes from MNG-6059
  - [MVNCENTRAL-4841](https://issues.sonatype.org/browse/MVNCENTRAL-4841) update central sync requirements
  - ~~[NEXUS-19912](https://issues.sonatype.org/browse/NEXUS-19912) Nexus Repo Pro update for POM format~~
- ~~[MNG-6538](https://issues.apache.org/jira/browse/MNG-6538) [MRESOLVER-64](https://issues.apache.org/jira/browse/MRESOLVER-64) Maven 3.6.0 regression in IntelliJ~~ [IDEA-201282](https://youtrack.jetbrains.com/issue/IDEA-201282) caused by [MRESOLVER-36](https://issues.apache.org/jira/browse/MRESOLVER-36)
- ~~merge Mickael Istria's [MNG-6529](https://issues.apache.org/jira/browse/MNG-6529) [PR 193](https://github.com/apache/maven/pull/193) for Eclipse m2e performance~~
- ~~merge Mickael Istria's [MNG-6533](https://issues.apache.org/jira/browse/MNG-6533) [PR 197](https://github.com/apache/maven/pull/197) for Eclipse m2e performance~~
- ~~review Mickael Istria's [MNG-6530](https://issues.apache.org/jira/browse/MNG-6530) [PR 194](https://github.com/apache/maven/pull/194) for Model cache~~
- ~~revert [MNG-6548](https://issues.apache.org/jira/browse/MNG-6548)~~
- ~~[MNG-6571](https://issues.apache.org/jira/browse/MNG-6571) memory consumption~~
- ~~[MNG-6572](https://issues.apache.org/jira/browse/MNG-6572) int or long instead of BigInteger~~
- ~~[MNG-6374](https://issues.apache.org/jira/browse/MNG-6374) infinite loop for invalid XML content~~
- ~~input location tracking improvement: [MNG-6597](https://issues.apache.org/jira/browse/MNG-6597) [MNG-6599](https://issues.apache.org/jira/browse/MNG-6599) [MNG-6600](https://issues.apache.org/jira/browse/MNG-6600) [MNG-6601](https://issues.apache.org/jira/browse/MNG-6601)~~
</details>

<details><summary>3.6.2</summary>

- ~~[MNG-6636](https://issues.apache.org/jira/browse/MNG-6636) NPE on reporting convertion (DefaultReportingConverter) when inheritance of with no reports~~
- ~~[MNG-6668](https://issues.apache.org/jira/browse/MNG-6668) [Modello PR#31](https://github.com/codehaus-plexus/modello/pull/31) Make location handling more memory efficient~~
- ~~[MNG-6629 PR](https://issues.apache.org/jira/browse/MNG-6629) Make ID validation faster~~
- ~~[MNG-6630 PR](https://issues.apache.org/jira/browse/MNG-6630) Make ComparableVersion faster~~
- ~~[MNG-6631 PR](https://issues.apache.org/jira/browse/MNG-6631) Make DefaultArtifactVersion faster~~
- ~~[MNG-6632 PR](https://issues.apache.org/jira/browse/MNG-6632) Remember artifact handlers after they've been used once~~
- ~~[MNG-6633 PR](https://issues.apache.org/jira/browse/MNG-6633) Reduce memory usage of excludes~~
- ~~[MNG-6638 PR](https://issues.apache.org/jira/browse/MNG-6638) Prevent reparsing POMs in MavenMetadataSource~~
- ~~[MNG-6681](https://issues.apache.org/jira/browse/MNG-6681) dependency type documentation~~
- ~~[MNG-6549](https://issues.apache.org/jira/browse/MNG-6549) Remove unused transitive dependencies of Guava~~
</details>

<details><summary>3.6.3</summary>

- ~~[MNG-6765](https://issues.apache.org/jira/browse/MNG-6765) Regression tycho pom-less builds fails with 3.6.2~~
- ~~[MNG-6771](https://issues.apache.org/jira/browse/MNG-6771) licensing issues (not really "up for grabs", but quite specific issue)~~
- ~~[MNG-6584](https://issues.apache.org/jira/browse/MNG-6584) Maven version 3.6.0 does not show ReasonPhrase anymore~~
- ~~[MNG-6789](https://issues.apache.org/jira/browse/MNG-6789) Maven Reproducible Build~~
</details>
</details>
<details><summary>3.8.0</summary>

- ~~[MNG-7118](https://issues.apache.org/jira/browse/MNG-7118) Block HTTP repositories by default~~
</details>

## Core 4
- ~~[MNG-6562](https://issues.apache.org/jira/browse/MNG-6562) WARN if plugins injected by default lifecycle bindings don't have their version locked in pom.xml or parent~~
- ~~[MNG-6656](https://issues.apache.org/jira/browse/MNG-6656) [Build vs Consumer POM](https://cwiki.apache.org/confluence/display/MAVEN/Build+vs+Consumer+POM)~~
- [MNG-5001](https://issues.apache.org/jira/browse/MNG-5001) @readonly Mojo parameter annotation doesn't work
- [MNG-5222](https://issues.apache.org/jira/browse/MNG-5222) warn when using deprecated plugin parameter
- [MNG-6772](https://issues.apache.org/jira/browse/MNG-6772) dependencyManagement import or dependencyManagement import
- [MNG-6795](https://issues.apache.org/jira/browse/MNG-6795) define a replacement for ReasonPhrase to display details about transfert failures
- [MNG-6763](https://issues.apache.org/jira/browse/MNG-6763) Restrict repositories to specific groupIds
- [MNG-5588](https://issues.apache.org/jira/browse/MNG-5588) provide easy way to define default plugins versions (after MNG-6562): pluginManagement import like dependencyManagement
- [MNG-6682](https://issues.apache.org/jira/browse/MNG-6682) source-release dependency type
- [jansi Windows perf improvements](https://github.com/fusesource/jansi/pull/150)

## Core future
- [relocation](https://maven.apache.org/guides/mini/guide-relocation.html) (poi:poi becomes officially org.apache.poi:poi)\
vs unofficial release (someone publishes a release in my.personal.group:poi, independently from original project and with same java package names)\
vs fork with classes conflict (a wanted fork but keeping same package names for compatibility)\
vs fork with package names rework (to avoid any conflict)
- [MNG-5814](https://issues.apache.org/jira/browse/MNG-5814) check signature of plugins against trusted list
- ascii progress bar, probably using ansi escape codes
- check artifact magic numbers, at least for zips, to detect download failures without downloading sha1 files (see [test case](https://github.com/Arnaud-Nauwynck/test-snippets/tree/master/test-http-repo))
- [MNG-5689](https://issues.apache.org/jira/browse/MNG-5689) define strict checksum per repository
- [MNG-6679](https://issues.apache.org/jira/browse/MNG-6679)/[MRESOLVER-90](https://issues.apache.org/jira/browse/MRESOLVER-90) HTML content in POM: Maven should validate content before storing in local repo
- provide CLI test demo program to do artifact resolution then easily debug in an IDE
- provide CLI test demo program to launch a Maven build then easily debug in an IDE
- import [mvnsh](https://github.com/jdillon/mvnsh)
- [mvnd](https://github.com/mvndaemon/mvnd) daemon and multi-threaded display
- [MNG-7129](https://issues.apache.org/jira/browse/MNG-7129) Deutsche Bank incremental build and cache
- [MVNCENTRAL-1365](https://issues.sonatype.org/browse/MVNCENTRAL-1365) Olaf [ApacheCon BigData Sevilla 2016 talk](https://apachebigdataeu2016.sched.com/event/8U07/attacking-a-big-data-developer-olaf-flebbe-sciencecomputing-ag) [slides](http://events17.linuxfoundation.org/sites/events/files/slides/AttackingBigDataDeveloper_0.pdf) and [ApacheCon Berlin 2018 IoT update](https://oflebbe.de/presentations/2018/attackingiotdev.pdf)

## [Reproducible/Verifiable Builds](https://cwiki.apache.org/confluence/pages/viewpage.action?pageId=74682318)
- ~~[MRELEASE-1029](https://issues.apache.org/jira/browse/MRELEASE-1029) maven-release-plugin update outputTimestamp~~
- [versions-maven-plugin/issues/453](https://github.com/mojohaus/versions-maven-plugin/issues/453) add an option to update Reproducible Build project.build.outputTimestamp while updating version
- ~~[ASF 22](https://issues.apache.org/jira/projects/MPOM/versions/12343925) parent POM release, with RB activated~~
- ~~[ASF 23](https://issues.apache.org/jira/projects/MPOM/versions/12346503) parent POM release, with RB fix~~
- ~~[Maven parent POM 34](https://issues.apache.org/jira/projects/MPOM/versions/12344077), with RB activated~~
- [Buildinfo plugin](https://github.com/apache/maven-studies/tree/maven-buildinfo-plugin)
  - ~~ability to generate [buildinfo file](https://reproducible-builds.org/docs/jvm/)~~
  - ~~ability to check local build output against reference build~~
  - ~~ability to detect JDK+OS from reference build, display (from reference buildinfo or manifest) and add to generated minimal buildinfo when no reference available~~
  - refactor to add separate check mojo in addition to check during buildinfo
  - ~~add explanations on how to test locally reproducibility (deploy reference to local dir)~~
  - ~~save comparison result of local build vs reference artifact~~
  - ~~detect that a Maven module is not installed or deployed, then should not be part of buildinfo~~
  - ~~move code from studies buildinfo:buildinfo to [maven-artifact-plugin](https://github.com/apache/maven-artifact-plugin):buildinfo~~
  - detect used plugins/goals and display if known non-reproducible
  - add a goal to report on dependencies reproducibility (against a trusted list...)
- effective reproducibility tracking:
  - ~~track Maven Central for (effective) pom with reproducible timestamp~~
  - track Maven Central for projects built with Maven, that could be enhanced to have reproducible build
  - ~~test reproducibility of these, manually or with containers~~
  - ~~Git repo to track and share rebuild recipes:~~ [reproducible-central](https://github.com/jvm-repo-rebuild/reproducible-central)
  - ~~statistics on reproduced builds in [reproducible-central](https://github.com/jvm-repo-rebuild/reproducible-central)~~
  - buildpsec for GuicedEE (daily) releases
  - ~~statistics on Maven-owned projects reproducibility~~ [reproducible-maven-HEAD](https://github.com/jvm-repo-rebuild/reproducible-maven-HEAD)
  - statistics on Plexus-owned projects reproducibility [reproducible-plexus-HEAD](https://github.com/jvm-repo-rebuild/reproducible-plexus-HEAD)
  - statistics on MojoHaus-owned projects reproducibility [reproducible-mojohaus-HEAD](https://github.com/jvm-repo-rebuild/reproducible-mojohaus-HEAD)
- [dist-tool-plugin](https://builds.apache.org/view/M-R/view/Maven/job/dist-tool-plugin/site/) report on reproducibility for Maven projects
- (DREAM) provide a GitHub badge showing that a project has Reproducible Build with link to [reproducible central](https://github.com/jvm-repo-rebuild/reproducible-central) proof
- add Maven to [RB's "who is involved"](https://reproducible-builds.org/who/)
- provide PRs to make projects builds reproducible:
  - ~~AWS java SDK [PR #2223](https://github.com/aws/aws-sdk-java/pull/2223)~~ to be merged
  - ~~AWS SDK for Java v2 [PR #1759](https://github.com/aws/aws-sdk-java-v2/pull/1759)~~ to be merged
  - ~~[Logback](https://github.com/qos-ch/logback) [PR#484](https://github.com/qos-ch/logback/pull/484)~~ to be merged
  - ~~[Arthas](https://github.com/alibaba/arthas) [PR#1128](https://github.com/alibaba/arthas/pull/1128)~~
  - ~~[CycloneDX core java PR #63](https://github.com/CycloneDX/cyclonedx-core-java/pull/63)~~
  - ~~[CycloneDX Maven Plugin PR #78](https://github.com/CycloneDX/cyclonedx-maven-plugin/pull/78)~~ to be merged
  - [Package URL Java](https://github.com/package-url/packageurl-java)
  - [Quarkus](https://github.com/quarkusio/quarkus)
  - [Jenkins](https://github.com/jenkinsci/jenkins)
  - [Jakarta EE APIs and RIs](https://github.com/eclipse-ee4j)
    - ~~[ee4j parent PR #71](https://github.com/eclipse-ee4j/ee4j/pull/71)~~ to be merged
    - ~~[Servlet API PR #384](https://github.com/eclipse-ee4j/servlet-api/pull/384)~~ to be merged
    - ~~[JakartaEE API PR #96](https://github.com/eclipse-ee4j/jakartaee-api/pull/96)~~ to be merged
  - [Drools](https://github.com/kiegroup/drools)
  - [Vaadin](https://github.com/vaadin/platform)
  - [Apache CXF](https://github.com/apache/cxf)
  - [Apache Directory](https://github.com/apache?q=directory-)
    - [directory-project](https://github.com/apache/directory-project)
    - [directory-buildtools](https://github.com/apache/directory-buildtools)
    - [directory-scimple](https://github.com/apache/directory-scimple)
    - [directory-ldap-api](https://github.com/apache/directory-ldap-api)
    - [directory-fortress-core](https://github.com/apache/directory-fortress-core)
    - [directory-fortress-commander](https://github.com/apache/directory-fortress-commander)
    - [directory-fortress-enmasse](https://github.com/apache/directory-fortress-enmasse)
    - [directory-fortress-realm](https://github.com/apache/directory-fortress-realm)
    - [directory-kerby](https://github.com/apache/directory-kerby)
    - [directory-studio](https://github.com/apache/directory-studio)
    - [directory-server](https://github.com/apache/directory-server)
  - ~~[Apache Dubbo](https://github.com/apache/dubbo/pull/5954)~~
  - [Apache Johnzon](https://github.com/apache/johnzon)
  - [Apache OpenWebBeans](https://github.com/apache/openwebbeans)
  - [Apache ServiceMix](https://github.com/apache/servicemix)
  - org.apache.hbase
  - org.apache.qpid
  - Hibernate
  - JBPM
  - Neo4j
  - [OWASP Dependency Check](https://github.com/jeremylong/DependencyCheck)
  - Webjars
  - ~~WSO2 Carbon [PR #50](https://github.com/wso2/carbon-parent/pull/50)~~ to be merged
  - XWiki
  - [Airbus Cybersecurity Graylog plugins](https://github.com/airbus-cyber?q=graylog)
  - ~~[Guiced EE](https://guicedee.com/) [PR#3](https://github.com/GedMarc/JWebMPDevKit/pull/3)~~
  - Liferay
  - Cucumber
  - Vertx
  - [Google Cloud Java client libraries](https://github.com/googleapis/java-shared-config)
  - ~~[Micronaut Maven plugin](https://github.com/micronaut-projects/micronaut-maven-plugin) [PR#11](https://github.com/micronaut-projects/micronaut-maven-plugin/pull/11)~~ merged for 1.0.0.RC4
  - ~~[Swagger PR #3841](https://github.com/swagger-api/swagger-core/pull/3841)~~ to be merged
  - Eclipse RDF4J
  - Societe Generale [ci-droid*](https://github.com/societe-generale?q=ci-droid)
  - com.vladsch.flexmark:flexmark
  - ~~[org.jline3 PR #628](https://github.com/jline/jline3/pull/628)~~ to be merged
  - ~~[JFlex](https://jflex.de/) [PR#765](https://github.com/jflex-de/jflex/pull/765)~~ to be merged
  - ~~[Fabric8 Kubernetes Client](http://fabric8.io/) [PR#2604](https://github.com/fabric8io/kubernetes-client/pull/2604)~~
- fix plugins issues to produce reproducible output:
  - ~~maven-remote-resources-plugin 1.7.0 with [MRRESOURCES-114](https://issues.apache.org/jira/browse/MRRESOURCES-114)~~
  - ~~[MSHADE-352](https://issues.apache.org/jira/browse/MSHADE-352) fix m-shade-p when using transorfmer~~
  - ~~springboot-maven-plugin:repackage [PR#20176](https://github.com/spring-projects/spring-boot/issues/20176)~~
  - [JFlex Maven Plugin](https://github.com/jflex-de/jflex) generates .java files containing current timestamp
  - [org.jboss.jandex:jandex-maven-plugin](https://github.com/wildfly/jandex-maven-plugin) [PR#26](https://github.com/wildfly/jandex-maven-plugin/pull/26) .idx
- check if plugins are able to produce reproducible output:
  - Quarkus
  - [Jenkins hpi plugin](https://github.com/jenkinsci/maven-hpi-plugin)
- provide process/tooling to check dependencies (projects dependencies, but also build dependencies, ie parent+plugins+their deps)

## Doxia/site/pdf
- [DOXIA-569](https://issues.apache.org/jira/browse/DOXIA-569) Markdown Sink
- ~~[MPDF-8](https://issues.apache.org/jira/browse/MPDF-8) pdf multi-modules, **merge [m-pdf-p PR1](https://github.com/apache/maven-pdf-plugin/pull/1)**~~
- [MPDF-89](https://issues.apache.org/jira/browse/MPDF-89) missing "Project Information" and "Project Reports" pages
- [MPDF-10](https://issues.apache.org/jira/browse/MPDF-10) Support menu sub-items in table of contents
- ~~[DOXIA-570](https://issues.apache.org/jira/browse/DOXIA-570) links escape~~
- m-site-p classloader provide Doxia
- ~~Doxia Book Git repo from [renderer and maven-plugin](https://github.com/apache/maven-doxia-tools/)~~
- [DOXIASITETOOLS-174](https://issues.apache.org/jira/projects/DOXIASITETOOLS/issues/DOXIASITETOOLS-174) rename site.xml's "project" root tag
- add live reload to site when run with `mvn site:run`
- ~~[DOXIA-575](https://issues.apache.org/jira/browse/DOXIA-575) Add support for (X)HTML5~~
- ~~[MSITE-836](https://issues.apache.org/jira/browse/MSITE-836) show report plugin when it fails with RuntimeException~~
- [MSHARED-650](https://issues.apache.org/jira/browse/MSHARED-650) Fire ExecutionEvent from DefaultMavenReportExecutor
- [DOXIA-614](https://issues.apache.org/jira/browse/DOXIA-614) source reference in Doxia Parser

## Misc
- ~~[maven-remote-resources-plugin](https://maven.apache.org/plugins/maven-remote-resources-plugin/) release [version 1.6.0](https://issues.apache.org/jira/projects/MRRESOURCES/versions/12331230)~~
- ~~[MPIR-373](https://issues.apache.org/jira/browse/MPIR-373) warnings in 3.0.0~~
- ~~[MPIR-375](https://issues.apache.org/jira/browse/MPIR-375) add plugin excludes feature for plugin-management report~~
- ~~[MPLUGIN-339](https://issues.apache.org/jira/browse/MPLUGIN-339) maven-plugin-tools-javadoc broken by com.sun.tools.doclets removal in Java 10~~
- [MPLUGIN-308](https://issues.apache.org/jira/browse/MPLUGIN-308) plugin-tools complex types
- maven-release-plugin conf phases
- [Classworlds](https://codehaus-plexus.github.io/plexus-classworlds/) ~~doc~~ + dump + graph
- doc new packaging in [Plugin Developers Centre](https://maven.apache.org/plugin-developers/index.html)
- tutorial new default lifecycle phases
- [extension demo](https://maven.apache.org/studies/extension-demo/)
- extensions list like [plugins](https://maven.apache.org/plugins/)
  - [raydac/mvn-finisher](https://github.com/raydac/mvn-finisher)
- [MASFRES-20](https://issues.apache.org/jira/browse/MASFRES-20) [resource bundles](https://maven.apache.org/apache-resource-bundles/) to Git as single multi-module build and removal of parent POM from Maven parent POMs
- ~~[INFRA-16467](https://issues.apache.org/jira/browse/INFRA-16467) move components out of CMS space~~
- [Vestige](https://gaellalire.fr/gitlab/vestige/vestige/wikis/home)
- replace plexus-default-container with sisu in tests and anywhere else
- ~~[MPH-160](https://issues.apache.org/jira/browse/MPH-160) help:effective-pom with source location display~~
- help:build-plan
- ~~rebuild GCE~~
- ~~[MARCHETYPES-63](https://issues.apache.org/jira/browse/MARCHETYPES-63) archetypes should work with Java 11~~
- [Package url](https://github.com/package-url/purl-spec) refinements: type vs extension, meaning of no type nor classifier
- ~~[MDEP-653](https://issues.apache.org/jira/browse/MDEP-653) add info message to purge-local-repository goal~~
- [MDEP-644](https://issues.apache.org/jira/browse/MDEP-644) Re-Add Dependency Tree Verbose
- ~~archive old Maven Git repositories~~
- contribute Maven Plugin to [Uno-Jar](https://github.com/nsoft/uno-jar)
- add repository format intro to [repositories documentation](http://maven.apache.org/guides/introduction/introduction-to-repositories.html)
- ~~[MWAR-433](https://issues.apache.org/jira/browse/MWAR-433) war oudated feature deletes generated content~~
- profile builds:
  - [MNG-4639](https://issues.apache.org/jira/browse/MNG-4639)
  - [takari/maven-profiler](https://github.com/takari/maven-profiler)
  - [jcgay](https://jeanchristophegay.com/posts/maven-profiler/) [jcgay/maven-profiler](https://github.com/jcgay/maven-profiler)
  - [intuit](https://medium.com/@alex_collins/10x-faster-maven-builds-at-intuit-5b7bb60c65e6) [intuit/maven-build-scanner](https://github.com/intuit/maven-build-scanner)

## Conf
<details><summary>2018</summary>
  
- ~~12/6/2018 [Paris JUG](https://www.parisjug.org/xwiki/wiki/oldversion/view/Meeting/20180612)~~
- ~~20/9/2018 [Bordeaux JUG](http://www.bordeauxjug.org/)~~
- ~~25/9/2018 [Orleans JUG](http://www.jugorleans.fr/soiree-apache-maven-35-et-java-9/)~~
- ~~13/11/2018 Devoxx Belgium [BOF](https://dvbe18.confinabox.com/talk/EVC-1727/Apache_Maven_BOF)~~
- ~~15/11/2018 [Lyon JUG](http://www.lyonjug.org/)~~
- ~~5-6/12/2018 [Paris Open Source Summit](http://www.opensourcesummit.paris/)~~
- ~~11/12/2018 [Reproducible Builds Summit 2018 in Paris](https://reproducible-builds.org/events/paris2018/)~~
</details>
<details><summary>2019</summary>
  
- ~~2-3/2/2019 [FOSDEM](https://cwiki.apache.org/confluence/display/MAVEN/FOSDEM)~~
- ~~15/6/2019 [Hack Commit Push](https://hack-commit-pu.sh/) contributions expected:~~
  - site content fixes and improvement
  - README.md améliorations et généralisation
  - low hanging fruits: see [up-for-grabs issues](https://s.apache.org/for-the-grabs_maven)
  - Jansi (console color) performance measure and improvement (particularly on Windows)
  - Reproducible Builds: archive entries timestamp configuration
  - depending on contributor knowledge or interest (web design <== WANTED!!!, performance, some specific plugins), oriented contribution
  - looking for help on scripting Google Storage work...
- ~~15/6/2019 [Hack Commit Push](https://hack-commit-pu.sh/) actual contributions:~~
  - ~~[MSKINS-107](https://issues.apache.org/jira/browse/MSKINS-107) up-for-grabs generator meta tag, done by Antoine~~
  - [DOXIATOOLS-59](https://issues.apache.org/jira/browse/DOXIATOOLS-59) up-for-grabs linkcheck issue, wip by Chris
  - [MNGSITE-353](https://issues.apache.org/jira/browse/MNGSITE-353) up-for-grabs Document maven.repo.local system property, wip by Elmehdi
  - how to [get full Maven sources](https://maven.apache.org/scm.html) on Windows, given Google Repo does not work here? wip by Joseph
  - [MSKINS-97](https://issues.apache.org/jira/projects/MSKINS/issues/MSKINS-97) upgrade Fluido Skins Bootstrap version from 2.3 to 4, wip by Vasile
  - check of pgp signatures for plugins, wip by Andrei and Charles
  - ~~Reproducible Builds force archive entries timestamp in plexus-archiver: explain/review/improve [PR #113](https://github.com/codehaus-plexus/plexus-archiver/pull/113) in light of pre-existing [PR #49](https://github.com/codehaus-plexus/plexus-archiver/pull/49), wip by Arnaud~~
  - Jansi improvements explanations/review (see [PR 146 to 153](https://github.com/fusesource/jansi/pulls)), wip by Arnaud
- ~~22-24/10/2019 [ApacheCon Europe 2019](https://aceu19.apachecon.com/)~~
</details>
<details><summary>2020</summary>

- 25/2/2020 Hackergarten
  - ~~[PR #58](https://github.com/quick-perf/quickperf/pull/58) make [Quickperf](https://github.com/quick-perf/quickperf) build reproducible (Minh-Trieu Ha)~~
  - make [Logback](https://github.com/qos-ch/logback) build reproducible (Bakary Djiba)
  - make Felix bundle-maven-plugin output reproducible (Arnaud)
- 31/03/2020 Hackergarten
  - make [Logback](https://github.com/qos-ch/logback) build reproducible (Bakary Djiba)
  [PR#484](https://github.com/qos-ch/logback/pull/484)
- 14/4/2020 Hackergarten
  - ~~[MKSINS-167](https://issues.apache.org/jira/browse/MSKINS-167) add anchors to headers (Bakary Djiba)~~
- ~~11-15/3/2020 [JChateau](https://www.jchateau.org/)~~
- ~~27/6/2020 [Hack Commit Push](https://paris2020.hack-commit-pu.sh/)~~
</details>

- 11/2021 Open Source Experience
  - 30/3/2021 comité programme
- 29/5/2021 [Hack Commit Push 2021](https://paris2021.hack-commit-pu.sh/)
- 2021 Hackergarten

[projects.apache.org](http://projects.apache.org)
========

- index.html fast display (no need for every .json)
- [INFRA-16355](https://issues.apache.org/jira/browse/INFRA-16355) Git mirror


Other
=====

- Attic 
