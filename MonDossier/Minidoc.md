# Documentation Stage Gaëlle Cosma/stylo
## Contexte 

Cosma est un outil de visualisation conçu pour les professionnels de l'information qui transforme des fichiers de texte simple avec des liens wiki en un réseau dynamique de cartes indexées. Cosma est prévu pour se superposer à un éditeur de texte tel que Stylo ; comme tous deux utilisent le langage markdown et héritent d’une philosophie des formats ouverts et de l’interopérabilité, leur articulation est donc non seulement possible, mais entrevue par les développeurs de Cosma. L’enrichissement et l’exploitation des données sémantiques contenues dans les articles est également une des pistes de développement en cours pour l’éditeur Stylo. 
Cette intégration permet un enrichissement des données des articles sur Stylo, pour les auteurs comme pour les revues. Les auteurs pourront valoriser les liens entre leurs propres textes, dans un prolongement de leurs propres activités de recherche en sciences humaines, et analyser et synthétiser leurs données de recherche de façon innovante et opérante. Les revues, quant à elles, pourront visualiser les références, les enjeux, les thématiques traversant l’ensemble de leur production, mais aussi des unités plus discrètes, comme les dossiers ou les articles eux-mêmes.

## Mofification pour généré le cosma
### En tête YAML 
Sur les fiches Markdown, nous avons récupéré tout le texte en markdown, mais nous avons ajouté une en-tête YAML à la main :
Exemple :

---
title : De *Lourdes* à *Paris*, en train ou à bicyclette  <!-- peut être récupéré avec les métadonnées dans stylo. -->
types: <!-- pas obligatoire, peut être rajouté aux métadonnées dans stylo et récupéré ou rajouté par défaut. -->
  - test
tags: <!-- pas obligatoire, peut être récupéré avec les métadonnées dans stylo ("mots clés" dans stylo) -->
  - Hybridations médiatiques 
  - machiniques dans le cycle des *Trois Villes* 
  - Émile  Zola (1893-1898)
---

### Bibliographie
Nous avons créé un dossier avec :
<!-- capture ecran : dossier bibliographie -->
- Roch a créé un fichier contenant des métadonnées décrivant les références bibliographiques qui regroupé toutes les bibliographies cités dans toutes les fiches et non un fichier de bibliographie par fiches. Le format requis est CSL JSON (extension .json). 
- Nous avons ajouté un fichier contenant les règles de formatage pour les citations et les bibliographies. Le format requis est CSL (extension .csl), que nous avons téléchargé à partir du répertoire des styles CSL de Zotero.
- Roch  ajouté un fichier contenant les termes localisés utilisés dans les bibliographies (par exemple « éditeur », « numéro »…). Le format requis est XML (extension .xml). 

### CSS
Nous avons ajouté un CSS en plus, mais ce n'est pas obligatoire.

### Fichier config
Nous avons généré le config.yml avec la commande Cosma puis modifié le YAML.

select_origin: directory 
files_origin: ./fiches <!-- chemin pour trouver les fiches -->
nodes_origin: ""
links_origin: ""
nodes_online: ""
links_online: ""
images_origin: ""
export_target: ""
history: true
focus_max: 2
record_types: <!-- Rajout des types que nous voulions, pas obligatoire d'en avoir plusieurs.  -->
  undefined:
    fill: "#005C53"
    stroke: "#005C53"
  litterature: 
    fill: "#DBF227"
    stroke: "#DBF227"
  test: 
    fill: "#D6D58E"
    stroke: "#D6D58E"
  Concept:
    fill: "#042940"
    stroke: "#042940"
  perso:
    fill: "#005C53"
    stroke: "#005C53"
  référence: <!-- ajouté pour que les références aient le bon type, sinon le titre sera obligatoirement : "undefined"-->
    stroke: "#6C6C6C"
    fill: "#6C6C6C"
link_types:
  undefined:
    stroke: simple
    color: "#e1e1e1"
references_as_nodes: true <!--écrire "true" au lieu de "false"-->
references_type_label: "référence"
record_filters: []
graph_background_color: "#ffffff"
graph_highlight_color: "#ff6a6a"
graph_highlight_on_hover: true
graph_text_size: 10
graph_arrows: true
node_size_method: degree
node_size: 10
node_size_max: 20
node_size_min: 2
attraction_force: 200
attraction_distance_max: 250
attraction_vertical: 0
attraction_horizontal: 0
views: {}
record_metas: []
generate_id: always
link_context: tooltip
hide_id_from_record_header: false
title: ""
author: ""
description: ""
keywords: []
link_symbol: ""
csl: ./bibliographie/apa.csl  <!-- chemin pour trouver le style bibliographique -->
bibliography: ./bibliographie/biblio.json  <!-- chemin pour trouver la bibliographie -->
csl_locale: ./bibliographie/locales-fr-FR.xml  <!-- chemin pour trouver la localisation bibliographique -->
css_custom: ./csstest.css  <!-- chemin pour trouver le css -->
devtools: false
lang: en


## Idées pour l'implémentation Cosma

### Revue
- Lier les intervenants, mots-clés, notions, termes entre eux dans le même dossier.
- En quoi ces auteurs appartiennent-ils, qui sont-ils ? [style de Open Data Sphere].
- Quelque chose dans un article peut avoir un lien avec un autre sans s'en rendre compte.

### Général
- Mieux comprendre sa pensée et sa structure :
  - Personnes, concepts, Wikidata.
  - Réseau de personnes.
- Explorer l'idée de pouvoir visualiser différentes versions et différences, tel que mon rapport.
- Citations.

## Besoins spécifiques de Cosma
- Voir doc.
- Possibilités avec Wikidata ?

## Problèmes rencontrés
### Test 1
Création de dossiers avec les fiches, certaines avec un ID via Zetler. Cosma -c fonctionne mais pas Cosma m :

```sh
Last login: Tue Jul  9 13:58:59 on ttys000
~ /Users/gaelledufaut-knipping/Documents/test-github
➜ test-github git:(main) ✗ cosma c
➜ Configuration file created: /Users/gaelledufaut-knipping/Documents/test-github/config.yml 
➜ test-github git:(main) ✗ cosma m 
[Cosma v.2.4.1]  /Users/gaelledufaut-knipping/Documents/test-github/config.yml
Err. Cannot modelize from directory with this config.
➜  test-github git:(main) ✗**
```

### Test 2
Refonte des fiches avec Zetler, toutes avec un ID et création de liens entre elles. Création de fausses métadonnées copiées d'un fichier qui fonctionne. L'en-tête YAML.

- Le souci se trouve dans le dossier car j’ai testé de copier-coller les fiches du graphe qui fonctionne et dans le dossier test GitHub ça ne fonctionne pas.
- Vérification sur toutes les fiches avec titre, ID, mots-clés, etc., toujours erreur.
- Changer les noms, enlever les tirets = même problème.

- J'ai tenté de le reproduire à partir de zéro, point par point de la doc, mais à partir du 4.1 plus rien ne fonctionne.

```sh
➜  cosma-test pwd
/Users/gaelledufaut-knipping/Documents/cosma-test
➜  cosma-test % record cosma
titre : test         
fg: no current job
zsh: command not found: titre
➜  cosma-test cosma record
[Cosma v.2.4.1]  /Users/gaelledufaut-knipping/Documents/cosma-test/config.yml
Err. Unable to create record: missing value for files_origin in the configuration file
➜  cosma-test /Users/gaelledufaut-knipping/Documents/cosma-test
➜  cosma-test cosma record
[Cosma v.2.4.1]  /Users/gaelledufaut-knipping/Documents/cosma-test/config.yml
Err. Unable to create record: missing value for files_origin in the configuration file
```