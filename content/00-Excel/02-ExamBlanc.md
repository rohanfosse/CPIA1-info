---
section: Excel
nav_order: 2
title: EI Blanc Excel
topics: Excel
---

### **Contexte**

Dans cette étude, nous modélisons la consommation horaire cumulée $ C(t) $ d’un bâtiment en fonction de plusieurs paramètres. L’objectif est d’analyser cette consommation, identifier les moments où elle dépasse 50 % de sa valeur maximale, et visualiser les données de manière pertinente.

L'équation récurrente utilisée est la suivante :

$$C(t+1) = C(t) + \Delta t \times \left(P*{base} + N(t) \cdot P*{moyen} + T(t) \cdot k_T + A(t) \cdot k_A \right)$$


---

### **Données Initiales**

Voici le fichier excel à télécharger pour réaliser cette étude : [EI_Excel_Blanc.xlsx](EIBlancExcel.xlsx)

#### **Paramètres**

Les paramètres suivants doivent être fixés dans votre fichier Excel (colonne **H**, ou autre zone dédiée) :

| **Paramètre**    | **Valeur par défaut** | **Description**                         |
| ---------------- | --------------------- | --------------------------------------- |
| $ C_0 $        | 0                     | Consommation initiale à $ t = 0 $.    |
| $ P\_{base} $  | 200                   | Consommation minimale des équipements.  |
| $ P\_{moyen} $ | 50                    | Consommation moyenne par personne.      |
| $ k_T $        | 5                     | Impact de la température extérieure.    |
| $ k_A $        | 100                   | Impact énergétique d’un pic d’activité. |
| $ \Delta t $   | 1                     | Intervalle de temps constant (1 heure). |

#### **Données mesurées**

- **$ N(t) $** : nombre de personnes présentes par heure.
- **$ T(t) $** : température extérieure (en °C).
- **$ A(t) $** : activité spécifique (0 ou 1).


### **Objectifs et Étapes**

Vous devez réaliser les étapes suivantes dans Excel :


#### **1. Fixer les paramètres dans des cellules** _(2 points)_

1. Placez les paramètres ci-dessus dans une zone dédiée de votre feuille Excel.


#### **2. Ajouter une colonne $ C(t) $ en fonction de l’équation et des paramètres fixés** _(6 points)_

1. Créez une colonne `C(t)` dans l’onglet **Data** à côté des données mesurées.
2. Implémentez l’équation récurrente pour calculer $ C(t) $ à chaque instant $ t $, en utilisant les paramètres fixés.


#### **3. Vérification et Analyse** _(6 points)_

1. **Calcul de 50 % de la valeur maximale de $ C(t) $** :

   - Dans une cellule sous la colonne $ C(t) $, calculez directement **50 % de la valeur maximale** de cette colonne.

2. **Vérification avec "Oui" ou "Non"** :
   - Ajoutez une colonne intitulée `Vérification`.
   - Remplissez cette colonne avec une condition : si $ C(t) $ est inférieur à 50 % de la valeur maximale, affichez "Non". Sinon, affichez "Oui".

#### **4. Visualisation Graphique et Analyse Supplémentaire** _(6 points)_

1. **Graphique de $ C(t) $ en fonction du temps** :

   - Tracez une courbe pour représenter $ C(t) $ en fonction de l’heure.

2. **Graphique en barres basé sur la colonne `Vérification`** :

   - Comptez le nombre de "Oui" et de "Non" dans la colonne `Vérification`.
   - Créez un graphique en barres pour illustrer cette répartition.

3. **Analyse supplémentaire** :
   - Affichez la proportion de "Oui" par rapport à la durée totale (en pourcentage) dans une cellule distincte.
   - Indiquez si le bâtiment dépasse 50 % de sa consommation maximale sur plus de la moitié de la journée.
