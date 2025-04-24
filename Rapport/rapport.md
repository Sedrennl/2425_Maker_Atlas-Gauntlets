# Atlas Gauntlet

# Table des matières
- [Atlas Gauntlet](#atlas-gauntlet)
- [Table des matières](#table-des-matières)
  - [Etude préalable pour le projet](#etude-préalable-pour-le-projet)
    - [Vision globale](#vision-globale)
    - [Détails](#détails)
      - [Articulations](#articulations)
      - [Fumée](#fumée)
    - [Détail](#détail)
      - [Lights](#lights)
    - [Recherche modèles 3D](#recherche-modèles-3d)
  - [Alimentation et Batterie](#alimentation-et-batterie)
    - [Composants et consommation](#composants-et-consommation)
    - [Courant total requis (scénario maximal)](#courant-total-requis-scénario-maximal)
    - [Puissance totale nécessaire](#puissance-totale-nécessaire)
    - [Batterie sélectionnée](#batterie-sélectionnée)
    - [Configuration choisie : 4S2P](#configuration-choisie--4s2p)
    - [Vérification des besoins en courant et puissance](#vérification-des-besoins-en-courant-et-puissance)
    - [Autonomie estimée](#autonomie-estimée)
    - [Réalisation](#réalisation)
  - [Cricuit Electrique](#cricuit-electrique)
    - [Liste composants à contrôler](#liste-composants-à-contrôler)
    - [PCB](#pcb)
      - [Schematic](#schematic)
      - [Routage](#routage)
      - [Soudure](#soudure)
  - [Modélisation 3D](#modélisation-3d)
    - [Recherche modèles 3D](#recherche-modèles-3d-1)

-------------------------------------------------------------
 
## Etude préalable pour le projet

Afin de préparer au mieux le projet et ses objectifs, j'ai tout d'abord reponcé la série en *0.5 pour récupérer des images de références.

### Vision globale

![Atlas Gantlet](ImagesVideos/Preparation/photos/Atlas_gauntlet.jpg)  
*Figure 1 :* Atlas Gantlet

On peut voir un peu le détail des différentes pièces

![Atlas Gantlet](ImagesVideos/Preparation/photos/vibe.png)  
*Figure 2 :* Vibe

**Référence taille :**

![photo](ImagesVideos/Preparation/photos/hexgloves_size.png)  
*Figure 3 :* Reference Taille par rapport à Jayce

### Détails

#### Articulations 

![photo](ImagesVideos/Preparation/gifs/hexgloves-on.gif)  
*Figure 4 :* Mode ON

![photo](ImagesVideos/Preparation/gifs/hexgloves-fightmode.gif)  
*Figure 5 :* fight mode 

![photo](ImagesVideos/Preparation/gifs/hrxgloves-fightmode2.gif)  
*Figure 6 :* fight mode 2

#### Fumée

![Hexgloves smoke](ImagesVideos/Preparation/gifs/Hexgloves-smoke.gif)  
*Figure 7 :* effet fumé 1

![Hexgloves smoke](ImagesVideos/Preparation/gifs/Hexgloves-smoke2.gif)  
*Figure 8 :* effet fumé 2

![Hexgloves smoke](ImagesVideos/Preparation/gifs/Hexgloves-smoke3.gif)  
*Figure 9 :* effet fumé 3

### Détail

![Hexgloves smoke](ImagesVideos/Preparation/gifs/aiguille.gif)  
*Figure 10 :* Aiguille

#### Lights

![Hexgloves smoke](ImagesVideos/Preparation/photos/Hexgloveslight.png)  
*Figure 11 :* lights

---

### Recherche modèles 3D

[Texte du lien](https://sketchfab.com/3d-models/arcane-vi-gauntlet-fanart-7dc0ebd2584741f3a2eabc1929bdca8d)  
Gratuit mais peu détaillé

[Texte du lien](https://www.etsy.com/fr/listing/1168945847/gantsgantelets-vis-atlas-arcane-fichiers)  
23€ mais pièces différentes

-------------------------------------------------------------

## Alimentation et Batterie

Dans le cadre de l'option Maker, nous avons un cours sur les batteries lithium et leur fabrication à partir de cellules. 
Vous retrouverez les slides de cours dans le document lié.

Pour le projet Atlas Gauntlet, l'objectif est d'avoir une seule batterie pour alimenter l'ensemble des composants.  
Le choix final pour la batterie est une configuration 4S2P (4 cellules en série et 2 groupes en parallèle). Les détails et calculs sont expliqués ci-dessous.

---

### Composants et consommation

- 6 micro-servos SG90 : ~3,9 A max.  
- Ruban LED RGB (40 cm) : ~0,5 A à 5 V (si alimenté en 5 V).  
- Électrovanne : ~1 A (si alimentée en 12 V, typique).  
- Résistance chauffante : ~1,67 A (si alimentée en 12 V, 20 W).  

---

### Courant total requis (scénario maximal)

Si tous les composants sont activés simultanément :
- À 5 V : 3,9 A + 0,5 A = 4,4 A.
- À 12 V : 1 A + 1,67 A = 2,67 A.

---

### Puissance totale nécessaire

- À 5 V : 5 V × 4,4 A = 22 W.
- À 12 V : 12 V × 2,67 A = 32 W.
- Puissance totale : 22 W + 32 W = 54 W.

---

### Batterie sélectionnée

Nous utilisons des cellules Li-Ion 18650 INR18650-35E Samsung avec les caractéristiques suivantes :
- Tension nominale : 3,7 V.
- Capacité : 3450 mAh (3,45 Ah).
- Courant de décharge maximal : 8 A.

### Configuration choisie : 4S2P
- 4 cellules en série (4S) :  
  - Tension nominale totale : 3,7 V × 4 = 14,8 V.
  - Tension maximale (complètement chargée) : 4,2 V × 4 = 16,8 V.
  - Tension minimale (déchargée) : 3,0 V × 4 = 12,0 V.

- 2 groupes en parallèle (2P) :  
  - Capacité totale : 3,45 Ah × 2 = 6,9 Ah.
  - Courant de décharge maximal : 8 A × 2 = 16 A.

---

### Vérification des besoins en courant et puissance

- Courant maximal requis par le système : 4,4 A + 2,67 A = 7,07 A.  
  Le courant de décharge max de 16 A de la batterie est largement suffisant.

- Puissance maximale requise : 54 W.  
  La tension nominale de 14,8 V et un courant maximal de 16 A donnent une puissance potentielle de :  
  14,8 V × 16 A = 236,8 W, ce qui est également suffisant.

---

### Autonomie estimée

La capacité totale de la batterie est de 6,9 Ah.  
Pour une consommation moyenne de 7,07 A (scénario maximal) :
Autonomie = Capacité (Ah) / Courant moyen (A) = 6,9 / 7,07 ≈ 0,98 heures.  

L'autonomie estimée est d'environ 1 heure en fonctionnement continu à pleine charge.

---

### Réalisation

Avec une configuration 4S2P, nous obtenons une tension nominale de 14,8 V, une capacité de 6,9 Ah, et un courant maximal de 16 A, ce qui couvre largement les besoins du projet tout en offrant environ 1 heure d’autonomie à pleine charge.

J'ai donc réalisé une batterie 4S1, en rajoutant d'ailleurs quelques supports 3D pour faciliter le positionnement et améliorer la stabilité de l'ensemble. 


![batterie montée](ImagesVideos/realisations/bat.jpeg)  
*Figure 12 :* Batterie réalisée



## Cricuit Electrique

A ce stade du projet, les attentes ont été revues à la baisse j'ai essayé de me reconcentrée sur les mouvements et la lumière, éliminant la fumée par exemple.

### Liste composants à contrôler 

- 5 micro-servos SG90 
- Ruban LED RGB 
  

### PCB 

J'ai donc réalisé une PCB avec ces contraintes. 
Vous trouverez la carte dans le dossier suivant : 
[PCB](../Hardware/PCB_Atlas_Gauntlet)

#### Schematic

On est sur une carte vraiment simple, avec juste des connecteurs.
Je suis restée sur une deux couches, il n'y avait pas besoin de plus sincèrement.

![schematic](ImagesVideos/realisations/PCB/schematic/alim.png)  
*Schematic Alimentation* 

![schematic](ImagesVideos/realisations/PCB/schematic/conn_led.png)  
*Schematic connecteurs LED* 

![schematic](ImagesVideos/realisations/PCB/schematic/conn_PCB.png)  
*Schematic connecteurs PCB* 

![schematic](ImagesVideos/realisations/PCB/schematic/microC.png)  
*Schematic micro Controleur* 


#### Routage 
![Routage front](ImagesVideos/realisations/PCB/routage/top.png)  
*Routage Top Layer* 

![Routage back](ImagesVideos/realisations/PCB/routage/back.png)  
*Routage Back Layer* 

#### Soudure

Une fois recu j'ai pu souder les différents composants nécessaires pour la carte.

![Routage back](ImagesVideos/realisations/carte.jpeg)  
*Routage Back Layer* 

Manque de temps, de moyens et de compétences (attention cette phrase sera récurrente à partir d'ici). Je n'ai pas pu la tester. 

## Modélisation 3D

Grosse partie, première tentative de modélisation seule.
Manque de temps, de moyens et de compétences, j'ai pris la décision de trouver un modèle sur internet. 

### Recherche modèles 3D

[Texte du lien](https://sketchfab.com/3d-models/arcane-vi-gauntlet-fanart-7dc0ebd2584741f3a2eabc1929bdca8d)  
Gratuit mais peu détaillé

[Texte du lien](https://www.etsy.com/fr/listing/1168945847/gantsgantelets-vis-atlas-arcane-fichiers)  
23€ mais pièces différentes choix final 

Vous trouverez les différentes pièces et leurs modèles convertis en STEP ici : 
[3D](../Hardware/3D)

S'il vous plait ne les utilisez pas. Il sont la propriété de la créatrice de ce modèle. Vous poyuvez les acheter. 


