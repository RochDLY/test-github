# Mini doc

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
- Citation.

## Besoin spécifique de Cosma
- Voir doc.
- Possibilités avec Wikidata ?

## Soucis rencontrés
### Test 1
Création de dossier avec les fiches, certaines avec un ID via Zetler. Cosma -c fonctionne mais pas Cosma m :

```sh
Last login: Tue Jul  9 13:58:59 on ttys000
~ /Users/gaelledufaut-knipping/Documents/test-github
➜ test-github git:(main) ✗ cosma c
➜ Configuration file created : /Users/gaelledufaut-knipping/Documents/test-github/config.yml 
➜ test-github git:(main) ✗ cosma m 
[Cosma v.2.4.1]  /Users/gaelledufaut-knipping/Documents/test-github/config.yml
Err. Cannot modelize from directory with this config.
➜  test-github git:(main) ✗**
```

### Test 2
Refonte des fiches avec Zetler, toutes avec un ID et création de liens entre elles. Création de fausses métadonnées copiées d'un qui fonctionne. L'en-tête YAML.

- Le souci se trouve dans le dossier car j’ai testé de copier-coller les fiches du graphe qui fonctionne et dans le dossier test GitHub ça ne fonctionne pas.
- Point sur toutes les fiches avec titre, ID, mots-clés, etc., toujours erreur.
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