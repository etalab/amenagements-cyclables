# Template de départ pour Table Schema

Ce dépôt contient les fichiers nécessaires pour démarrer la création d'un dépôt pour un schéma [Table Schema](https://specs.frictionlessdata.io/table-schema/).

## Utiliser ce template

- Si vous créez votre dépôt sur GitHub, il vous suffit d'appuyer sur le bouton vert "Use this template". Consultez [la documentation](https://help.github.com/en/github/creating-cloning-and-archiving-repositories/creating-a-repository-from-a-template) pour plus d'infos ;
- Si votre projet sera hébergé ailleurs (par exemple Gitlab), vous pouvez cloner ce répertoire ou télécharger les fichiers correspondants. Utilisez le bouton "Clone or download".

## Fichiers disponibles

Ce dépôt contient un ensemble de fichiers utiles pour un dépôt d'un schéma [Table Schema](https://specs.frictionlessdata.io/table-schema/).

- [`CHANGELOG.md`](CHANGELOG.md) contient la liste des changements entre les différentes versions de votre schéma ;
- [`exemple-valide.csv`](exemple-valide.csv) est un fichier CSV d'exemple conforme par rapport au schéma décrit dans `schema.json`  ;
- [`exemple-valide.xlsx`](exemple-valide.xlsx) est un fichier XLSX d'exemple conforme par rapport au schéma décrit dans `schema.json` ;
- [`LICENSE.md`](LICENSE.md) est le fichier de licence du dépôt. Nous recommandons d'utiliser la [Licence Ouverte](https://www.etalab.gouv.fr/licence-ouverte-open-licence), cette licence est recommandée par l'administration française pour le partage de données et de documents ;
- [`README.md`](README.md) est le fichier que vous lisez actuellement. À terme, il devra présenter votre schéma ;
- [`requirements.txt`](requirements.txt) liste les dépendances Python nécessaires pour effectuer des tests en intégration continue sur votre dépôt ;
- [`schema.json`](schema.json) est le schéma au format Table Schema.

### Intégration continue

Ce dépôt est configuré pour utiliser de l'intégration continue, si vous utilisez GitHub. À chaque commit, une suite de tests sera lancée via [GitHub Actions](https://github.com/features/actions) afin de vérifier :

- que votre schéma est valide à la spécification Table Schema ;
- que vos fichiers d'exemples sont conformes au schéma.

Si vous n'utilisez pas GitHub, vous pouvez lancer ces tests sur votre machine ou sur un autre service d'intégration continue comme Gitlab CI, Jenkins, Circle CI, Travis etc. Consultez la configuration utilisée dans [`.github/workflows/test.yml`](.github/workflows/test.yml).

Localement, voici la procédure à suivre pour installer l'environnement de test et lancer les tests :

```bash
# Création d'un environnement virtuel en Python 3
python3 -m venv venv
source venv/bin/activate

# Installation des dépendances
pip install -r requirements.txt

# Test de la validité du schéma
tableschema validate schema.json

# Test de la conformité des fichiers d'exemples
goodtables validate --schema schema.json exemple-valide.csv
goodtables validate --schema schema.json exemple-valide.xlsx
```

## Étapes à suivre

Nous détaillons ci-dessous les étapes que nous vous conseillons de suivre après avoir créé votre dépôt Git, tout en utilisant les fichiers d'exemples.

- [ ] Décrire votre schéma dans le fichier `schema.json` en respectant la spécification Table Schema. Le fichier d'exemple comprend des valeurs d'exemples pour toutes les métadonnées possibles. Notez que les champs d'exemple ne comprennent qu'une petite partie des types, formats et contraintes disponibles, référez-vous à [la documentation](https://specs.frictionlessdata.io/table-schema/#types-and-formats) pour toutes les valeurs possibles. Si certaines métadonnées ne sont pas nécessaires pour votre projet, vous pouvez les supprimer. Pour vérifier que votre schéma est conforme, vous pouvez utiliser l'outil [tableschema](https://pypi.org/project/tableschema/) en ligne de commande : `tableschema validate schema.json`
- [ ] Modifier les fichiers d'exemples CSV et XLSX avec des données conformes à votre schéma. L'outil [goodtables](https://pypi.org/project/goodtables/) permet de vérifier que vos fichiers sont conformes au schéma en ligne de commande `goodtables validate --schema schema.json exemple-valide.csv`
- [ ] Modifier le fichier [`CHANGELOG.md`](CHANGELOG.md) pour indiquer la publication initiale
- [ ] Modifier le fichier [`README.md`](README.md), en supprimant tout son contenu tout d'abord. Au sein de plusieurs paragraphes, vous indiquerez le contexte, les modalités de production des données, le cadre juridique, la finalité, les cas d’usage etc. Consultez plusieurs schémas sur [schema.data.gouv.fr](https://schema.data.gouv.fr) pour découvrir quelles informations sont pertinentes à indiquer
- [ ] Vérifier que la licence ouverte vous convient. Si vous devez utiliser une autre licence, modifiez le fichier [`LICENSE.md`](LICENSE.md) et indiquez la licence dans le fichier [`schema.json`](schema.json), dans la clé `licenses`


## Documentation

Pour vous aider dans la construction de votre dépôt, nous vous recommandons de vous référer à :

- [Le guide à destination des producteurs de schéma](https://guides.etalab.gouv.fr/producteurs-schemas/)
- [La documentation de schema.data.gouv.fr](https://schema.data.gouv.fr)
- [La spécification Table Schema](https://specs.frictionlessdata.io/table-schema/)
