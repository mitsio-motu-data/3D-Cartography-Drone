# Grille de survol avec Mission Planner

[**Site de Mission Planner**](https://ardupilot.org/planner/)


> Tutoriel écrit avec la version **1.3.8479.20539** de Mission Planner


Réaliser un vol d'acquisition est long et fastidieux. De plus, les images de la zone acquise doivent être prises avec un recouvrement spécifique. Utiliser un logiciel qui planifie les missions permet de s'assurer que la prise d'images sera bonne et permet que l'opérateur drone réalise la mission plus facilement. Pour faire cela, nous utilisons [Mission Planner](https://ardupilot.org/planner/). C'est un logiciel gratuit et Open Source qui permet de prévoir des grilles de vol autonome.

Nous appelerons **mission horizontale** un vol sur un plan parrallèle au sol (par exemple pour cartographier un parc) et **mission verticale** un vol sur un plan perpendiculaire au sol (par exemple pour cartographier une façade de bâtiment).


> 🚨 On vous prévient, Mission Planner est un logiciel qui présente de nombreux bugs.
> Nous allons essayer de vous guider au mieux dans le logiciel. Il est possible qu'avec
> de nouvelles mises à jour, certains soient résolus et que d'autres apparaissent.


## Installation

Commencez par installer Mission Planner en suivant les instructions de ce [lien](https://ardupilot.org/planner/docs/mission-planner-installation.html).

## Ouverture de Mission Planner et *Home*
En ouvrant Mission Planner, vous arriverez sur un écran similaire. Rendez-vous dans la section **PLAN**, accessible par le boutton encadré en bleu. 

<figure align="center">
    <img src="../../images/guide/mission_planner/home.jpg"/>
    <figcaption>Écran d'accueil de Mission Planner</figcaption>
</figure>

Placez le point de départ et d'arrivée (*Home*) : 
- Soit à la main : `Clic droit` > `Set home here`
- Soit avec les coordonnées GPS : en bas du panneau de droite (voir photo ci-dessous)

L'idéal est de placer ce point vers la zone de la mission mais sa position n'a pas de véritable importance car il ne sera en fait pas utilisé dans nos mission. Le placer permet cependant de travailler plus facilement avec Mission Planner qui veut qu'un point *Home* soit défini. 

<figure align="center">
    <img src="../../images/guide/mission_planner/set_home.jpg"/>
    <figcaption>Définition d'un point <em>Home</em></figcaption>
</figure>

## Mission horizontale

Créez un polygon représentant la zone que le drone doit couvrir. `Clic droit` > `Polygon` > `Draw a Polygon` (ou `Load Polygon` pour importer un fichier)

<figure align="center">
    <img src="../../images/guide/mission_planner/draw_polygon.jpg"/>
    <figcaption>Création d'un polygone</figcaption>
</figure>

Voici à quoi devrait ressembler votre interface une fois le polygone dessiné :

<figure align="center">
    <img src="../../images/guide/mission_planner/polygon.jpg"/>
    <figcaption>Polygone</figcaption>
</figure>

Il faut ensuite générer le parcours. Pour cela, utilisez la fonction de quadrillage (ou `Survey (Grid)`). `Clic droit` > `Auto WP` > `Survey (Grid)`


<figure align="center">
    <img src="../../images/guide/mission_planner/survey_grid.jpg"/>
    <figcaption>Chemin vers <em>Survey grid</em></figcaption>
</figure>

Une nouvelle fenêtre apparaît. Elle va permettre de paramétrer le quadrillage pour la grille de survol.
1. Commencez par activer les options avancées. Dans le panneau de droite : `Simple` > `Display` > `Advanced Options` 
2. Vérifiez si le modèle du drone (et donc les paramètres de sa caméra) est connu de Mission Planner. Si c'est le cas sélectionnez le modèle du drone. Si ce n'est pas le cas nous déterminerons les paramètres de la caméra dans les étapes suivantes, **la première fois uniquement**.

    Dans le panneau de droite : `Simple` > `Simple Options` > `Camera`
    
    Ce n'est le cas pour le **DJI Mavic Air 2** lors de la rédaction de ce tutoriel.

3. Rendez-vous dans le menu des paramètres de la caméra.
Dans le panneau de droite : `Camera Config`

<figure align="center">
    <img src="../../images/guide/mission_planner/start_survey_grid.jpg"/>
</figure>




