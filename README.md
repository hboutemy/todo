My Maven TODO list
=========

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

## Core 3.7
- ~~[MNG-6562](https://issues.apache.org/jira/browse/MNG-6562) WARN if plugins injected by default lifecycle bindings don't have their version locked in pom.xml or parent~~
- [MNG-6682](https://issues.apache.org/jira/browse/MNG-6682) source-release dependency type
- [jansi Windows perf improvements](https://github.com/fusesource/jansi/pull/150)
- [MNG-5001](https://issues.apache.org/jira/browse/MNG-5001) @readonly Mojo parameter annotation doesn't work
- [MNG-6795](https://issues.apache.org/jira/browse/MNG-6795) define a replacement for ReasonPhrase to display details about transfert failures

## Core future
- [relocation](https://maven.apache.org/guides/mini/guide-relocation.html) (poi:poi becomes officially org.apache.poi:poi)\
vs unofficial release (someone publishes a release in my.personal.group:poi, independently from original project and with same java package names)\
vs fork with classes conflict (a wanted fork but keeping same package names for compatibility)\
vs fork with package names rework (to avoid any conflict)
- [Build vs Consumer POM](https://cwiki.apache.org/confluence/display/MAVEN/Build+vs+Consumer+POM)
- [MNG-5814](https://issues.apache.org/jira/browse/MNG-5814) check signature of plugins against trusted list
- ascii progress bar, probably using ansi escape codes
- check artifact magic numbers, at least for zips, to detect download failures without downloading sha1 files (see [test case](https://github.com/Arnaud-Nauwynck/test-snippets/tree/master/test-http-repo))
- [MNG-5689](https://issues.apache.org/jira/browse/MNG-5689) define strict checksum per repository
- [MNG-6679](https://issues.apache.org/jira/browse/MNG-6679)/[MRESOLVER-90](https://issues.apache.org/jira/browse/MRESOLVER-90) HTML content in POM: Maven should validate content before storing in local repo

## [Reproducible/Verifiable Builds](https://cwiki.apache.org/confluence/pages/viewpage.action?pageId=74682318)
- ~~[MRELEASE-1029](https://issues.apache.org/jira/browse/MRELEASE-1029) maven-release-plugin update outputTimestamp~~
- [Buildinfo](https://reproducible-builds.org/docs/jvm/) plugin
- ~~[ASF 22](https://issues.apache.org/jira/projects/MPOM/versions/12343925) parent POM release, with RB activated~~
- ~~maven-remote-resources-plugin 1.7.0 with [MRRESOURCES-114](https://issues.apache.org/jira/browse/MRRESOURCES-114)~~
- ~~[ASF 23](https://issues.apache.org/jira/projects/MPOM/versions/12346503) parent POM release, with RB fix~~
- ~~[Maven parent POM 34](https://issues.apache.org/jira/projects/MPOM/versions/12344077), with RB activated~~
- ~~track Maven Central for (effective) pom with reproducible timestamp~~
- test reproducibility of these
- Git repo to track and share

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

## Misc
- ~~[maven-remote-resources-plugin](https://maven.apache.org/plugins/maven-remote-resources-plugin/) release [version 1.6.0](https://issues.apache.org/jira/projects/MRRESOURCES/versions/12331230)~~
- ~~[MPIR-373](https://issues.apache.org/jira/browse/MPIR-373) warnings in 3.0.0~~
- ~~[MPIR-375](https://issues.apache.org/jira/browse/MPIR-375) add plugin excludes feature for plugin-management report~~
- [MPLUGIN-339](https://issues.apache.org/jira/browse/MPLUGIN-339) maven-plugin-tools-javadoc broken by com.sun.tools.doclets removal in Java 10
- [MPLUGIN-308](https://issues.apache.org/jira/browse/MPLUGIN-308) plugin-tools complex types
- maven-release-plugin conf phases
- [Classworlds](https://codehaus-plexus.github.io/plexus-classworlds/) ~~doc~~ + dump + graph
- doc new packaging in [Plugin Developers Centre](https://maven.apache.org/plugin-developers/index.html)
- tutorial new default lifecycle phases
- [extension demo](https://maven.apache.org/studies/extension-demo/)
- extensions list like [plugins](https://maven.apache.org/plugins/)
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

- 25/2/2020 Hackergarten
  - make [Quickperf](https://github.com/quick-perf/quickperf) build reproducible (Minh-Trieu Ha)
  - make [Logback](https://github.com/qos-ch/logback) build reproducible (Bakary Djiba)
  - make Felix bundle-maven-plugin output reproducible (Arnaud)
- 11-15/3/2020 [JChateau](https://www.jchateau.org/)

[projects.apache.org](http://projects.apache.org)
========

- index.html fast display (no need for every .json)
- [INFRA-16355](https://issues.apache.org/jira/browse/INFRA-16355) Git mirror
