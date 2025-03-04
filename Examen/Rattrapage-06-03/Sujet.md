---
title: "EXAMEN – Simulation et Analyse de Températures Horaires"
layout: lesson-content
permalink: /Rattrapage-Conception.html
---

**Durée :** 1h00

**Critères d’évaluation :**

- Clarté et structure du **pseudocode**
- Qualité et fonctionnalité du **code Python**
- Respect des consignes et lisibilité du programme
- Qualité des courbes générées

Vous pouvez trouver une correction dans le fichier jupyter suivant : [Rattrapage-Conception-Correction.ipynb](Rattrapage-Conception-Correction.ipynb)

---

## **Contexte**

Une station météorologique enregistre la **température extérieure** d'une ville **chaque heure pendant 24 heures**.

L’objectif est de concevoir un **algorithme** (en Pseudo Code) et un **programme Python** qui :

1. **Simule les températures horaires** de la journée.
2. **Analyse les températures** en trouvant la valeur minimale, maximale et moyenne.
3. **Calcule un indicateur de variation thermique**.
4. **Affiche un graphique montrant l’évolution des températures et leur distribution**.

---

## **Partie 1 – Pseudocode (6 points)**

Écrire un **algorithme en pseudocode** permettant de :

1. **Générer 24 températures aléatoires** comprises entre **-5°C et 30°C**, en utilisant uniquement la fonction `random.uniform()`.
2. **Stocker ces valeurs dans une liste** où chaque indice représente une heure de la journée (0 à 23).
3. **Déterminer et afficher** :
   - La **température minimale et l’heure correspondante**.
   - La **température maximale et l’heure correspondante**.
   - La **température moyenne sur la journée**.
4. **Calculer et afficher l’écart absolu moyen des températures**, défini par la formule :

$$
\Delta T*{\text{moyen}} = \frac{|T*{\max} - T\_{\min}|}{n-1}
$$

où :

- \( T\_{\max} \) est la température maximale enregistrée dans la journée.
- \( T\_{\min} \) est la température minimale enregistrée dans la journée.
- \( n \) est le nombre total de mesures (ici \( n = 24 \)).

5. **Afficher les températures** de chaque heure sous forme de tableau.

**Contraintes** :

- Ne pas utiliser les fonctions `min()`, `max()`, `sum()`, ni `index()`.

---

## **Partie 2 – Implémentation en Python (8 points)**

Écrire un **programme Python** qui :

1. Génère une **liste des températures** contenant **24 valeurs aléatoires** entre **-5°C et 30°C**, en respectant les contraintes mentionnées.
2. Effectue les calculs demandés et affiche les résultats.
3. Affiche les **températures par heure sous forme de tableau**.
4. **Affiche un graphique en courbe** représentant **l’évolution des températures au cours de la journée** (heures en abscisse, températures en ordonnée).
5. **Affiche un histogramme** montrant **la répartition des températures** en classes de valeurs.

---

## **Partie 3 – Analyse des Données et Visualisation (6 points)**

1. **Personnaliser les graphiques** avec :
   - Un titre clair
   - Un axe X représentant les heures de la journée (0 à 23 h) pour la courbe
   - Un axe X représentant des intervalles de température pour l’histogramme
   - Un axe Y représentant les températures en degrés Celsius pour la courbe
   - Un axe Y représentant le nombre d’occurrences pour l’histogramme
   - Une légende pour distinguer les courbes
2. Interpréter visuellement la répartition des températures grâce à l’histogramme.

---

### **Bonus (2 points)**

- Ajouter une option permettant à l’utilisateur de **modifier les limites de génération des températures** pour simuler différentes conditions climatiques.


