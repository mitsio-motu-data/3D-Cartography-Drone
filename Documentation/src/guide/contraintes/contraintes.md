# Identification des contraintes

Avant toute mission, il est indispensable d'identifier les différentes contraites. Comme cette documentation est rédigée par et pour [Mitsio Motu](https://www.mitsiomotu.com/), les contraintes listées ici seront celles propres au matériel de l'entreprise. Pour toute évolution de matériel, il faut re-lister toutes les contraintes pour adapter le projet.

Nous allons lister ici les contraintes suivant trois axes :

1. **Les contraintes organisationnelles** : budget, temps disponible,...
2. **Les contraintes matérielles** : matériel disponible, ses capacités et ses limites.
3. **Les contraintes du terrain**, liées à l'opération: géographie du lieu, météo, accessibilité,...

## Contraintes organisationnelles

Lorsque vous vous lancez dans ce projet, commencez par clarifier quelques points concernant l'organisation tels que :

- De combien de temps disposez-vous pour chaque étape ?
- Pouvez-vous accéder au site sans problème ?
- Possédez-vous déjà les autorisations légales pour le vol du ou des drone(s) ?
- Quel budget est disponible pour le projet ?

## Contraintes matérielles

### Drone

Le drone de [Mitsio Motu](https://www.mitsiomotu.com/) est le [Mavic Air 2](https://www.dji.com/mavic-air-2/specs). C'est un très bon drone amateur. Il embarque une caméra (photo et vidéo) et une balise GPS/GLONNASS.

<figure align="center">
    <img src="../../images/guide/drone_mavic.jpg" | width=500/>
    <figcaption>Drone Mavic Air 2</figcaption>
</figure>

Voici les contraintes à prendre en compte avec ce drone :

- 3 batteries de 20 à 25 minutes d'autonomie
- Appareil photo 12MP (3000x4000 px) ou 48MP (6000x8000 px)
- Capteur RGB (pas multispectral)
- Prise d'images en JPG et DNG (format RAW de DJI)
- Pas de planification de vol prévue par le constructeur (contrainte contournée par l'[utilisation de Litchi Fly](../planification/planification.md))
- Papiers relatifs au drone et à son import au Togo égarés
- Stockage de 8Go embarqué sur le drone + une carde micro SD de 128Go

### Ordinateur

La phase de reconstruction d'un modèle 3D demande de la puissance de calcul. Le tableau ci-dessous est extrait de la [documentation d'ODM](https://docs.opendronemap.org/installation/#id4) (logiciel que nous utilisons pour [la reconstruction](../reconstruction/reconstruction.md)) et présente les recommendations de hardware en fonction du nombre d'images.

| Number of images | RAM of RAM + Swap |
| ---------------: | ----------------: |
| 40               | 4                 |
| 250              | 16                |
| 500              | 32                |
| 1500             | 64                |
| 2500             | 128               |
| 3500             | 192               |
| 5000             | 256               |

Le projet de l'Hôtel de la Paix requiert par exemble environ 2500 images. Aucun ordinateur de l'entreprise n'a 128Go de RAM. Plusieurs solutions sont possibles pour contourner ce problème :

1. Reconstruire le bâtiment par section et faire du recalage ensuite
2. Allouer un très grand [swap](https://fr.wikipedia.org/wiki/Espace_d%27%C3%A9change) et traiter la totalité en une seule fois

Nous approfondirons ces points dans la section [Reconstruction](../reconstruction/reconstruction.md).

## Contraintes du terrain

### Géographie du lieu

Avant de faire l'acquisition, il est très important de se rendre sur le lieu, surtout si les vols vont se faire de manière automatisée. Cela permet de se rendre compte de potentiels problèmes lors de l'acquisition. Si possible, il faut faire cette reconnaissance avec le drone pour prendre quelques mesures.

Par exemple, lors du projet de l'Hôtel de la Paix, se rendre sur le terrain en avance a permis de :

- Prendre des mesures de hauteur des différents toits pour programmer ensuite les altitudes de vol du drone
- Repérer des zones problématiques où les vols devront être effectués manuellement
- Repérer les couloirs de vols qui évitent les palmiers 🌴
- Faire des tests de filtres polarisants avec la caméra du drone et la couleur du bâtiment
- Découper le bâtiment en sections à acquérir

### Infrastructures

Des questions utiles doivent être posées :

- Y a-t-il de l'électricité sur le lieu ? Pour le rechargement des batteries du drone le jour J.
- Y a-t-il un endroit pratique pour travailler sur ordinateur ? Pour modifier les plans de vol en direct si besoin.
- Le lieu est-il fréquenté ? Si oui, quelles sont les meilleures horaires pour éviter d'être dérangé ?
