# Cartographie 3D par drone

Ce dépôt contient la documentation du projet de cartographie 3D par drone.

Il s'agit d'un site web généré à partir de fichiers Markdown.
Pour le générer, nous utilisons [mdBook](https://rust-lang.github.io/mdBook/).

Pour le moment, il n'y a pas de déploiement automatique, il faut donc le générer localement. Pas d'inquiétude, c'est très simple ! Il suffit d'appliquer les quelques commandes expliquées ci-dessous.

## Contribuer

### Prérequis

- [mdBook](https://rust-lang.github.io/mdBook/)

### Installation

D'abord, il faut cloner le dépôt :

```bash
git clone <this-repo>
```

### Utilisation

Pour générer la documentation, il faut exécuter la commande suivante :

```bash
cd <this-repo>/Documentation
mdbook serve --open # Génère la documentation et l'ouvre dans votre navigateur
```

Une fenêtre de votre navigateur par défaut devrait s'ouvrir sur la documentation.
Vous pouvez également accéder à la documentation en allant sur l'adresse suivante : [http://localhost:3000](http://localhost:3000).

Vous pouvez maintenant naviguer dans la documentation.


### Structure du dépôt

```sh
.
├── Documentation/ # Contient la documentation
│   ├── book.toml # Configuration de mdBook
│   ├── src/ # Contient les fichiers Markdown et les images,
│   │   │    # organisés en dossiers hiérarchiques selon la table des matières
│   │   ├── <chapitre>/
│   │   │   ├── <chapitre>.md
│   │   │   ├── <image>.jpg
│   │   │   ├── <sous-chapitre>/
│   │   │   │   ├── <sous-chapitre>.md
│   │   │   │   ├── <image>.jpg
│   │   │   │   └── ...
│   │   │   └── ...
│   │   └── ...
│   ├── theme/ # Contient le thème utilisé par mdBook
│   │   ├── css/
│   │   │   └── <variable>.css # Contient les couleurs du thème Mitsio Motu
│   │   └── ...
│   └── SUMMARY.md # Table des matières
├── .gitignore
├── .github/ # Contient les fichiers de configuration de GitHub
│   └── workflows/ # Contient les workflows GitHub Actions
│       └── deploy.yml # Déploiement automatique de la documentation sur GitHub Pages
└── .markdownlint.json # Configuration de markdownlint
```

### Syntaxe Markdown

Il n'y a pas de règles strictes concernant la syntaxe Markdown,
mais nous essayons de suivre quelques bonnes pratiques pour que contribuer soit le plus agréable possible.

Nous utilisons [markdownlint](https://github.com/DavidAnson/markdownlint) pour vérifier la syntaxe des fichiers Markdown.
Différentes extensions existent pour les éditeurs de texte,
vous pouvez donc l'installer pour votre éditeur préféré.

Certaines règles sont désactivées pour des raisons de compatibilité avec mdBook.
Vous pouvez consulter la configuration dans le fichier [`.markdownlint.json`](.markdownlint.json).

## Auteurs

- [Adèle PLUQUET](https://github.com/apluquet)
- [Adrien ANTON LUDWIG](https://linktr.ee/adrien.ludwig)
