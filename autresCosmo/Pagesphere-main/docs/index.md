# "Il faut revenir à Pagès"

## Explications sur le graphe

Ce document a pour but d'expliquer la constitution du [graphe du réseau social de *Robert Pagès*](https://oledeuff.github.io/Pagesphere/pagesphere.html)
Le titre du document est une référence aux propos de Suzanne Briet.
Ce livrable fait partie du projet [*Documentation and Knowledge Infrastructure: The Case of Robert Pagès*](https://fbf.berkeley.edu/publications/documentation-and-knowledge-infrastructure-case-robert-pagès) financé par France-Berkeley Fund
Une première *présentation* du graphe a eu lieu durant le Colloque *Docam 2023* à Paris au Cnam.
## Structure du graphe
Le graphe repose sur un work in progress qui comprend pour l'instant environ une centaine d'entités, principalement des personnes mais auss des organisations ou des concepts.
Les entités sont classés selon plusieurs types. Chaque entité pouvant avoir deux types associés.
La *typologie* est la suivante :

Une première forme de catégorie qui définit *la nature de la relation* à Robert Pagès :
- Collaborateur désigne une personne avec qui Robert Pagès a été amené à collaborer et à travailler notamment dans des cadres de publications communes.
- Influenceur désigne une personne qui a eu une influence sur Robert Pagès. Cette influence peut-être de nature intellectuelle sans qu'il n'y ait eu nécessairement de rencontres.
- Famille désigne un lien familial (épouse,enfants, etc.)
- Organisation renvoie à une organisation de type laboratoire.
- Objet renvoie à une réalisation.
La seconde forme est de *nature disciplinaire*
Pour le moment, nous avons retenu les disciplines suivantes :
- Psychologie 
- Psychiatrie 
- Sciences de l'information et de la communication 
- Transdisciplinaire 
- Sociologie 
- Philosophie 
Les choix opérés restent discutables et susceptibles d'être révisés ultérieurement.
Les entités non définies sont classées comme *undefined*

La typologie est provisoire et est susceptible d'évoluer.

### A propos des liens

Les liens du graphe possèdent également quelques spécificités.
Les liens restent en *gris* quand la nature du lien n'a pas été précisée ou quand elle ne mérite pas une précision spécifique. Le lien reste sémantisé dans le contexte de la fiche quelque soit le cas de figure.
Nous avons défini des liens spécifiques avec une visualisation particulière sur le graphe pour mieux les distinguer
Les liens d'influence sont en vert. Ils concernent des influences qui peuvent s'exercer sur Robert Pagès mais aussi sur les autres membres du graphe.
Les personnes qui ont eu Robert Pagès comme directeur de thèse sont également distingués par une couleur
Enfin, les liens d'opposition entre des entités apparaissent en rouge et en pointillé. Cette spécificité nous apparaît essentielle pour rappeler que si des liens existent, ils ne sont pas équivalents.
Quelques part, cela reprend la théorie des noeuds du concept d'*emprise* de Robert Pagès.
Pour les utilisateurs du logiciel Cosma, j'ai rajouté ces précisions dans le fichier config.yml après la définition des liens "undefined":
```
  i:
    stroke: simple
    color: "#6495ED"
  d:
    stroke: simple
    color: "#50C878"
  o:
    stroke: dash
    color: "#FF4500"
```

Dernière mise à jour. 30 août 2023. Olivier Le Deuff. Oledeuff@gmail.com 
![le checheur contemplant son graphe](./bd1.JPG)
