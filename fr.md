1) Ajouter les éléments qui manquent au lifecycle en 2018 :
- Ajouter une sorte de bundle phase, qui n'est pas le packaging. Typiquement je veux faire un tar.gz de mes jars ou encore creer un conteneur Docker apres que mes jars aient été produits.

- Pouvoir ajouter / supprimer les étapes de notre choix.

- Pouvoir exécuter des étapes en parallèle.

- Ajouter une etape test integration arrivant après la phase de packaging  
  => [integration-test](https://maven.apache.org/ref/3.5.3/maven-core/lifecycles.html) existe déjà, avec pre et post

- Idem avec la notion d'analyse du code

- Idem mais avec la notion d'appeler un autre outil (genre npm ou angular-cli)


2) La conf
- Autant être clair, le xml c'est bien mais c'est verbeux. Ce qui rebute la jeune génération qui vient du yaml et du json. Maven devrait pouvoir gerer au moins l'un des deux autres par défaut.

- Séparer la conf des plugins (build) de celle des dependances pour reduire la taille des pom.  
  => [Consumer POM](https://cwiki.apache.org/confluence/display/MAVEN/Build+vs+Consumer+POM)

- Gérer les dependances via la ligne de commande à la npm ou Yarn. Par exemple "yarn add @angular" ajoute la dernière version de disponible au package.json (équivalent du pom).
yarn add @angular.5.2.1 prendra la version 5.2.1

- Avoir un release et un dev modes. Le second préparamètre le compilo en mode debug et sans optimisation, le premier fait l'inverse. 
  => quel intérêt ?


3) Le build
- Build incrémental du code (on ne recompile que la classe qui a changé).

- Idem mais avec les modules.

- Avoir un dev mode (ie. recompilation des classes changées et execution des TU à la volée). Module par module évidemment. Exemple [lustest](https://github.com/itametis/lustest-maven-plugin)

- Exécution en parallèle du build des modules par défaut.

- Lancer un démon en background pour ne pas relancer une jvm de zéro à chaque build.

- Un mode CI ou le build courant ne va jamais chercher les jar des modules du projet en cours dans le repo local mais dans les target des modules eux-mêmes.
  => a priori existe déjà avec le réacteur

- Moins de logs. Par défaut, on se tait si tout va bien ! (Cf. Unix & GNU way) Et on affiche que les infos utiles. Par exemple :
* Compile ok
* TU ok
* Package ko
* Et voici pourquoi...
* ...

- Un analyseur de build qui indique les doublons, d'autres problèmes et peut dessiner le process exécuté.



4) Doc

- Mettre en avant des exemples de code pour créer des plugins, utiliser des boms.
  => [Plugin Developers Centre](https://maven.apache.org/plugin-developers/index.html)

- Séparer les docs de fonctionnement (ce que sait faire Maven), des docs d'utilisation (comment le faire avec Maven), des docs techniques (comment c'est codé dans Maven). C'est ce sur quoi je travaille.

5) Communauté
- Mettre en place un discorde / twitter ou équivalent pour parler à la communauté.
  => [Twitter](https://twitter.com/ASFMavenProject) depuis le site
- Utiliser une forge sur laquelle tout le monde a accès.
  => GitHub?
- Faire des appels à contribution, typiquement "hey on recherche quelqu'un pour faire ça".
- Tisser des partenariats avec des Universités.
