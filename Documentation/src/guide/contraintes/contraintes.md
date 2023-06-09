# Identification des contraintes

Avant toute mission, il est indispensable d'identifier les différentes contraites. Comme cette documentation est rédigée dans et pour [Mitsio Motu](https://www.mitsiomotu.com/), les contraintes listées ici seront celle propres au matériel de l'entreprise. Pour toute évolution de matériel, il faut re lister toutes les contraintes pour adapter le projet.

Nous allons lister ici les contraintes suivant trois axes : 
1. **Les contraintes organisationnelles** : Ce sont celles qui sont liées au budget, au temps disponible,...
2. **Les contraintes matérielles** : Ce sont celles liées au matériel disponibles, à ses capacités et ses limites.
3. **Les contraintes du terrain** : Ce sont celles liées à l'opération, la géographie du lieu, la météo, l'accessibilité,...


## Contraintes organisationnelles

Lorsque vous vous lancez dans ce projet, commencez par clarifier quelques points concernant l'organisation tels que : 
- De combien de temps disposez-vous pour chaque étape
- Comment avez-vous accès au site ?
- Possédez-vous déjà les autorisation légales pour le vol du ou des drone(s)
- Quel budget est disponible pour le projet

## Contraintes matérielles

### Drone

Le drone de [Mitsio Motu](https://www.mitsiomotu.com/) est le [Mavic Air 2](https://www.dji.com/mavic-air-2/specs). C'est un très bon drone amateur. Il embarque un appareil photos/caméra et une balise GPS/GLONNASS.

<figure align="center">
    <img src="../../images/guide/drone_mavic.jpg" | width=500/>
    <figcaption>Drone Mavic Air 2</figcaption>
</figure>

Voici les contraintes à prendre en compte avec ce drone : 
- 3 batteries de 20 à 25 minutes d'autonomie
- Appareil photo 12MP (3000x4000 px) ou 48MP (6000x8000 px)
- Pas de capteur hors RGB
- Prise d'images en PNG et DNG (format RAW de DJI)
- Pas de planification de vol prévue par le constructeur (contrainte contournée)
- Papiers relatifs au drone et à son import au Togo égarés
- Stockage de 8Go embarqué sur le drone + une carde micro SD de 128Go


### Ordinateur

La phase de reconstruction dans un modèle 3D demande de la puissance de calcul. Le tableau ci-dessous est extrait de la [documentation de ODM](https://docs.opendronemap.org/installation/#id4) (logiciel que nous utilisons pour la reconstruction) et présente les recommendations de hardware à avoir en fonction du nombre d'images.

| Number of images | RAM of RAM + Swap |
| ---------------: | ----------------: |
| 40               | 4                 |
| 250              | 16                |
| 500              | 32                |
| 1500             | 64                |
| 2500             | 128               |
| 3500             | 192               |
| 5000             | 256               |

Un projet de la taille de celui de l'hôtel de la paix requiert par exemble environ 2500 images. Aucun ordinateur de l'entreprise n'a 128Go de RAM. Plusieurs solutions seront possibles pour contourner ce problèmes : 
1. Reconstruire le bâtiment par section et faire du recalage ensuite
2. Allouer un très grand [swap](https://fr.wikipedia.org/wiki/Espace_d%27%C3%A9change) et traiter la totalité en une seule fois

Nous approndirons ces points dans la section [Reconstruction](../reconstruction/reconstruction.md).


## Contraintes du terrain

### Géographie du lieu

Avant de faire l'acquisition, il est très important de se rendre sur le lieu, surtout si les vols vont se faire de manière automatisée. Cela permet de se rendre compte de potentiels problèmes qui vont être rencontrés le ou les jours de l'acquisition. De plus, c'est très utile pour bien comprendre le lieu. Si possible, il faut faire cette reconnaissance avec le drone pour prendre quelques mesures.

Par exemple, lors du projet de l'hôtel de la paix, se rendre sur le terrain en avance a permis de : 
- Prendre des mesures pour la hauteur des différents toits pour programmer en avance les altitudes de vol du drone
- Repérer des zones problématiques ou les vols devront être effectués manuellement
- Repérer les couloirs de vols qui évitent les palmiers
- Faire des tests de filtres polarisants avec la caméra du drone et la couleur du bâtiment
- Découper le bâtiment en sections à acquérir


### Infrastructures

Des questions utiles doivent être posées : 

- Il y a-t'il de l'électricité sur le lieu (pour le rechargement des batteries du drone le jour J)
