# Cartographie 3D par drone

<p align=center>
    <img src="./Documentation/src/introduction/presentation_projet/hdp_original_picture.jpg" width=600/><br>
    <em>Hôtel de la Paix (photo d'époque)</em>
</p>

Afin de préserver une trâce d l'Hôtel de la Paix, à Lomé, nous avons réalisé une cartographie 3D du bâtiment. Vous trouverez ici la documentation reprenant tout ce projet : 
- Présentation du projet
- Guide pour mettre en place un projet similaire
- Archives des recherches effectuées en amont
- Crédits et remerciements

Le lien pour accéder à la documentation et les suivant : [https://mitsio-motu-data.github.io/3D-Cartography-Drone/](https://mitsio-motu-data.github.io/3D-Cartography-Drone/)

## Contribuer

***Exclusivement pour les membres de l'organisation [Mitsio Motu](https://github.com/mitsio-motu-data).***

Si vous souhaitez modifier ou étayer cette documentation, il faudra suivre les étapes suiantes. Merci de la tenir à jour de tout changement afin qu'elle reste pertinent le plus longtemps possible.

### Prérequis

La documentation a été écrite grâce à [**mdBook**](https://rust-lang.github.io/mdBook/). Faite un tour sur la documentation pour l'installer et pour vous renseigner sur l'outil.

Clonez ensuite le dépôt :
```bash
git clone <this-repo>
```

### Utilisation

Pour avoir un aperçu de votre travail, il faut générer la documentation. Il faut exécuter la commande suivante :

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

Quelques fonctionnalités sont spécifiques à mdBook. Vous pouvez les consulter sur leur [documentation](https://rust-lang.github.io/mdBook/format/markdown.html).

Certaines règles sont désactivées pour des raisons de compatibilité avec mdBook.
Vous pouvez consulter la configuration dans le fichier [`.markdownlint.json`](.markdownlint.json).

## Auteurs & contributeurs

- [Adèle PLUQUET](https://github.com/apluquet)
- [Adrien ANTON LUDWIG](https://linktr.ee/adrien.ludwig)

## Outils

Ce projet n'aurait pas été possible sans les librairies et logiciels [Open Source](https://opensource.com/resources/what-open-source#:~:text=The%20term%20open%20source%20refers,approach%20to%20creating%20computer%20programs.) que nous avons utilisés. Merci à tous les contributeurs pour leur travail :

**Écritude et illustration de cette documentation**

[![mdBook](https://img.shields.io/badge/-mdBook-000000?logo=mbBook&logoColor=white&style=for-the-badge)](https://rust-lang.github.io/mdBook/)
[![Flameshot](https://img.shields.io/badge/-Flameshot-660081?logo=logoColor=white&style=for-the-badge)](https://flameshot.org/)
[![Inkscape](https://img.shields.io/badge/-Inkscape-000000?logo=Inkscape&logoColor=white&style=for-the-badge)](https://inkscape.org/fr/)

**Réalisation du projet**

[![Python](https://img.shields.io/badge/-Python-3776AB?logo=Python&logoColor=white&style=for-the-badge)](https://www.python.org/)
[![MissionPlanner](https://img.shields.io/badge/-Mission%20Planner-f9b232?logo=logoColor=white&style=for-the-badge)](https://ardupilot.org/planner/)
[![MissionPlannerToLitchi](https://img.shields.io/badge/-Mission%20Planner%20To%20Litchi-c6c6c6?logo=logoColor=white&style=for-the-badge)](https://github.com/YarostheLaunchpadder/MissionPlanner-to-Litchi)
[![Blender](https://img.shields.io/badge/-Blender-F5792A?logo=Blender&logoColor=white&style=for-the-badge)](https://www.blender.org/)
[![Qgis](https://img.shields.io/badge/-Qgis-589632?logo=Qgis&logoColor=white&style=for-the-badge)](https://www.qgis.org/fr/site/)
[![ODM](https://img.shields.io/badge/-Open%20Drone%20Map-f15a24?logo=logoColor=white&style=for-the-badge)](https://opendronemap.org/)
[![Meshlab](https://img.shields.io/badge/-Meshlab-a0cb8f?logo=logoColor=white&style=for-the-badge)](https://www.meshlab.net/)
[![Docker](https://img.shields.io/badge/docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)](https://www.docker.com/)
