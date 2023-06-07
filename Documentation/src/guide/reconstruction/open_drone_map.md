# Open Drone Map

[**Site d'Open Drone Map**](https://opendronemap.org/)
[**Dépôt d'Open Drone Map**](https://community.opendronemap.org/)
[**Forum d'Open Drone Map**](https://github.com/OpenDroneMap/ODM)

> ⚠️ FIXME ⚠️
>
> Expliquer ce qu'est Open Drone Map.
> 
> ```
> Today companies, government entities, professionals and hobbyists alike use some
> or all parts of OpenDroneMap to perform a varieties of tasks, including:
> • Monitoring crops in agriculture.
> • Mapping land areas.
> • Performing hydrological analysis.
> • Reporting construction progress.
> • Classifying and counting trees.
> • Analyzing stockpile volumes.
> • Documenting car crashes.
> • Inspecting roofs and cell towers.
> • Documenting proof of work completion.
> • Archeological artifact scanning.
> • Improving OpenStreetMap.
> • Stitching historical aerial images.
> ```

## Installation

Voir la [documentation d'Open Drone Map](https://docs.opendronemap.org/installation/) qui est très claire.

Dans notre cas, nous avons utilisé la version Docker comme recommandé dans la documentation.

Dans la suite de ce document, nous montrerons les commandes avec Docker.

## Utilisation

Pour une structure de fichiers comme ceci : 
  
```
datasets
├── mission_1
│   ├── images
│   │   ├── img_1.jpg
│   │   ├── img_2.jpg
│   │   ├── ...
│   │   └── img_n.jpg
├── mission_2
├── ...
└── mission_n
```

> Les images doivent **obligatoirement** être dans un dossier `images` à la racine de la mission.

Pour reconstruire la mission 1, il faut lancer la commande suivante :

```bash
docker run -ti --rm -v <chemin_vers>/datasets:/datasets opendronemap/odm --project-path /datasets mission_1
```

## GPU

Afin d'accélérer le processus de reconstruction, il est possible d'utiliser le GPU de la machine, si elle en possède un.
Pour cela, il faut ajouter l'option `--gpus all` à la commande et utiliser l'image Docker `opendronemap/odm:gpu`.

```bash
docker run -ti --rm -v <chemin_vers>/datasets:/datasets --gpus all opendronemap/odm:gpu --project-path /datasets mission_1
                                                        ^^^^^^^^^^                 ^^^^
```

## Processus de reconstruction recommandé

Deux options s'offrent à nous :
1. Reconstruire chaque mission séparément et fusionner les nuages de points.
2. Reconstruire l'ensemble des missions en même temps.

Avantages et inconvénients de chaque méthode :

| Méthode | Avantages | Inconvénients |
| :-----: | :-------: | :-----------: |
| 1 | - Plus facile à mettre en place. <br> - Plus facile à corriger en cas d'erreur. <br> - Nécessite moins de RAM | - Compliqué de recaler toutes les sections ensemble <br> - Comment fusionner et retirer les erreurs ? |
| 2 | - Meilleure robustesse (en théorie) <br> - Pas de recalage à faire <br> - Reconstruit mieux les alentours car pas de mission spécifique mais un peu de chaque mission | - Plus difficile à corriger en cas d'erreur. <br> - Possibilité d'introduire des erreurs avec les imprécisions qui se multiplient sur le dataset général <br> - En fonction du nombre d'images, peu nécessiter beaucoup de RAM |

Dans tous les cas, nous recommandons de commencer par reconstruire chaque mission séparément, même si on souhaite reconstruire l'ensemble des missions par la suite.
En effet, il est plus facile de corriger les erreurs sur une mission que sur l'ensemble des missions.

> Il n'y a pas de réponse universelle quant à la méthode à choisir. Ces choix vont aussi dépendre du projet et de l'acquisition des images.

## Exemple de reconstruction

⚠️ FIXME ⚠️

## Erreurs rencontrées

Nous avons rencontré 2 erreurs majeures lors de la reconstruction des missions.

### Coordonnées GPS aberrantes

Certaines images présentaient des coordonnées GPS aberrantes.
Cela peut être dû à une mauvaise réception GPS au moment de la prise de vue.

Voici un exemple de reconstruction avec des coordonnées GPS aberrantes par rapport à la même reconstruction sans ces images.

| Avec les images aberrantes | Sans les images aberrantes |
| :------------------------: | :-----------------------: |
| ![Avec les images aberrantes](../../images/guide/odm/with_gps_aberrant_images.png) | ![Sans les images aberrantes](../../images/guide/odm/without_gps_aberrant_images.png) |

Pour trouver les images aberrantes, on peut utiliser QGIS.
Pour cela, il faut utiliser la fonction `Import GeoTagged Photos` et sélectionner le dossier contenant les images.

Certaines aberrations sont visibles à l'oeil nu.
Par exemple, sur la figure ci-dessous, nous savons que toutes les images devraient être localisées dans la zone verte.
On peut donc identifier les images aberrantes.

![QGIS_GPS_aberrant](../../images/guide/odm/qgis_gps_aberrant.png)

D'autres aberrations sont moins visibles, comme des images **non localisées** ou **mal localisées**.

Pour les images mal localisées, il est possible de les mettre en évidence en utilisant la fonction `Zoom to Layer Extent` sur la couche `Photos`. 

Les images non localisées n'apparaissent pas sur la carte.
On peut les trouver en sélectionnant toutes les images visibles sur la cartes et en inversant la sélection.

> ⚠️ FIXME ⚠️
> Explorer la possibilité de reconstruire sans utiliser les coordonnées GPS des images.

### Images non exploitables

Comme évoqué sur la page précédente, nous recommandons de supprimer les images qui ne sont pas exploitables.

Voici un exemple d'images que nous avons oublié de supprimer et qui ont généré une erreur lors de la reconstruction.

![Palmier](../../images/guide/odm/palmier.jpg)