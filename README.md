My Maven TODO list
=========

## Core 3.5.x
- ~~jansi [1.7.1 release](https://github.com/fusesource/jansi/issues/114)~~
- ~~[MNG-6411](https://issues.apache.org/jira/browse/MNG-6411) readability of available modules~~
- ~~[MNG-6410](https://issues.apache.org/jira/browse/MNG-6410) multiple modules with same artifactId~~

## Core 3.6
- ~~[MNG-5951](https://issues.apache.org/jira/browse/MNG-5951) add an option to avoid path addition to inherited URLs~~
  - more flexible idea would be to have multiple strategies with a Plexus role and multiple hints:
    by default, appends artifactId (or project.directory) like currently, another would not add anything (hint id to be found),
    another hint could work with git specific url rules. Interface = `String getInheritedUrl( String parentUrl, MavenProject parent, MavenProject child )`
    issue: this would create a dependency on Plexus container/Sisu
- ~~[MNG-4508](https://issues.apache.org/jira/browse/MNG-4508) No way to avoid adding artifactId to site urls~~
- ~~[MNG-6059](https://issues.apache.org/jira/browse/MNG-6059) Important use cases not covered, as child.inherit.append.path affects all children~~
- ascii progress bar, probably using ansi escape codes
- check artifact magic numbers, at least for zips, to detect download failures without sha1

## Core future
- relocation (poi:poi becomes officially org.apache.poi:poi) vs unofficial release (someone publishes a release in my.personal.group:poi, independently from original project and with same java package names) vs fork with classes conflict (a wanted fork but keeping same package names for compatibility) vs fork with package names rework (to avoid any conflict)
- [Build vs Consumer POM](https://cwiki.apache.org/confluence/display/MAVEN/Build+vs+Consumer+POM)
- [Verifiable Builds](https://cwiki.apache.org/confluence/pages/viewpage.action?pageId=74682318)
- [MNG-5814](https://issues.apache.org/jira/browse/MNG-5814) check signature of plugins against trusted list

## Doxia/site/pdf
- [DOXIA-569](https://issues.apache.org/jira/browse/DOXIA-569) Markdown Sink
- ~~[MPDF-8](https://issues.apache.org/jira/browse/MPDF-8) pdf multi-modules, **merge [m-pdf-p PR1](https://github.com/apache/maven-pdf-plugin/pull/1)**~~
- [MPDF-89](https://issues.apache.org/jira/browse/MPDF-89) missing "Project Information" and "Project Reports" pages
- [MPDF-10](https://issues.apache.org/jira/browse/MPDF-10) Support menu sub-items in table of contents
- [DOXIA-570](https://issues.apache.org/jira/browse/DOXIA-570) links escape
- m-site-p classloader provide Doxia
- Doxia Book Git repo from [renderer and maven-plugin](https://github.com/apache/maven-doxia-tools/)
- [DOXIASITETOOLS-174](https://issues.apache.org/jira/projects/DOXIASITETOOLS/issues/DOXIASITETOOLS-174) rename site.xml's "project" root tag

## Misc
- [maven-remote-resources-plugin](https://maven.apache.org/plugins/maven-remote-resources-plugin/) release [version 1.6.0](https://issues.apache.org/jira/projects/MRRESOURCES/versions/12331230)
- [MPIR-373](https://issues.apache.org/jira/browse/MPIR-373) warnings in 3.0.0
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

## Conf
- ~~12/6/2018 [Paris JUG](https://www.parisjug.org/xwiki/wiki/oldversion/view/Meeting/20180612)~~
- ~~20/9/2018 [Bordeaux JUG](http://www.bordeauxjug.org/)~~
- ~~25/9/2018 [Orleans JUG](http://www.jugorleans.fr/soiree-apache-maven-35-et-java-9/)~~
- 13/11/2018 Devoxx Belgium [BOF](https://dvbe18.confinabox.com/talk/EVC-1727/Apache_Maven_BOF)
- 15/11/2018 [Lyon JUG](http://www.lyonjug.org/)
- 5-6/12/2018 [Paris Open Source Summit](http://www.opensourcesummit.paris/)


[projects.apache.org](http://projects.apache.org)
========

- index.html fast display (no need for every .json)
- [INFRA-16355](https://issues.apache.org/jira/browse/INFRA-16355) Git mirror
