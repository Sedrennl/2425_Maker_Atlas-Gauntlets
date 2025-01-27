#Atlas Gauntlet



## Alimentation et Batterie

Dans le cadre de l'option Maker, nous avons un cours lié aux batteries lithium et la fabrication de ces dernières à partir de cellules. 
Vous retrouverez les slides de cours dans le document lié.

Dans mon cas le but est d'avoir une seule batterie pour l'ensemble du projet. 
A ce jour, pour un gant, j'aurais besoin de :

## 1. Composants :
- **6 micro-servos SG90** : ~3,9 A max.
- **Ruban LED RGB (40 cm)** : ~0,5 A à 5V (si alimenté en 5V).
- **Électrovanne** : ~1 A (si alimentée en 12V, typique).
- **Résistance chauffante** : ~1,67 A (si alimentée en 12V, 20W).

## 2. Courant total requis (scénario maximal) :
Si tous les composants sont activés simultanément :
- **À 5V** :  
  \( 3,9 \, \text{A} + 0,5 \, \text{A} = 4,4 \, \text{A} \)
- **À 12V** :  
  \( 1 \, \text{A} + 1,67 \, \text{A} = 2,67 \, \text{A} \)

Je fais le choix d'avoir une alim à 12 V et d'ajouter dans mon circuit un buck pour obtenir des tension à 5 V pour les Servos et les LED.

Nous avons à notre disposition des batteries LiIon 18650 INR18650-35E Samsung 3,7V 3450mAh 8A
Une cellule délivre : 
Tension : 3,7 V
Capacité : 3450 mAh (3,45 Ah).
Courant de décharge maximum : 8A.

# Courants nécessaires (scénario maximal)

- **À 5V** : 4,4 A.  
- **À 12V** : 2,67 A.

## Puissance totale nécessaire (en W)

- **À 5V** :  
  \( 5 \, \text{V} \times 4,4 \, \text{A} = 22 \, \text{W} \)

- **À 12V** :  
  \( 12 \, \text{V} \times 2,67 \, \text{A} = 32 \, \text{W} \)

- **Puissance totale** :  
  \( 22 \, \text{W} + 32 \, \text{W} = 54 \, \text{W} \)


Pour couvrir nos besoins, nous aurons donc besoin de :
- **12 V** soit 3 batteries de 3,7 V en parrallèl => 11,1V (en nominal)
    Mais on pourra monter jusqu'à 4,2V par cellule => 12,8V (en maximal)
- **14,6 A** soit 2 séries de batteries en parralèle => 16 A

Nous aurons donc besoin d'une batterie 3S2P qui devrait sortir 11,1V à 16 A



