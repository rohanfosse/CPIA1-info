---
section: Excel
nav_order: 4
title: Exercices Supplémentaires
topics: Excel, Exercices
---


Voici une série d'exercices rapides pour améliorer vos compétences en Excel, couvrant différentes fonctionnalités comme les formules, les graphiques, et les analyses de données.

Vous pouvez télécharger le fichier de base pour les exercices : [Donnees_Exercices.xlsx](Exercices_Excel.xlsx)

---

Les exercices ont été mis à jour pour inclure des solutions interactives. Vous pouvez afficher les solutions en cliquant sur le bouton "Solution" sous chaque question.

### **Exercice 1 : Somme Automatique et Calculs de Base**

{% include question.html header="Exercice 1 - Somme Automatique" text="Créez une colonne C pour calculer le Total (Quantité × Prix unitaire). Ensuite, calculez la somme totale et la valeur moyenne. Bonus : ajoutez une réduction de 10 % et un Total après Réduction." solution="Pour calculer le Total : utilisez la formule `=B2*A2`. Pour la somme totale : `=SOMME(C2:C10)`. Pour la moyenne : `=MOYENNE(C2:C10)`. Pour la réduction : `=C2*0.1`. Pour le Total après Réduction : `=C2-D2`." %}

---

### **Exercice 2 : Mise en Forme Conditionnelle**

{% include question.html header="Exercice 2 - Mise en Forme Conditionnelle" text="Appliquez une mise en forme conditionnelle pour mettre en vert les scores supérieurs à 70 et en rouge ceux inférieurs à 50. Bonus : ajoutez des commentaires automatiques avec la formule SI." solution="Mise en forme : règle pour vert : `=B2>70`. Règle pour rouge : `=B2<50`. Formule pour les commentaires : `=SI(B2>=70,'Bon','À améliorer')`." %}

---

### **Exercice 3 : Création d’un Graphique Simple**

{% include question.html header="Exercice 3 - Graphique Simple" text="Créez un histogramme représentant les ventes mensuelles, avec un titre 'Ventes Mensuelles' et des étiquettes sur les axes. Bonus : ajoutez une ligne de tendance." solution="Créez un histogramme à partir des données des mois et des ventes. Ajoutez le titre et les étiquettes d’axes. Pour la ligne de tendance : cliquez sur le graphique > Ajouter une ligne de tendance > Sélectionnez 'Linéaire'." %}

---

### **Exercice 4 : Recherche et Correspondance**

{% include question.html header="Exercice 4 - Recherche avec RECHERCHEV" text="Créez une cellule où l’utilisateur peut entrer un produit, et utilisez RECHERCHEV pour afficher son prix. Bonus : ajoutez une colonne avec le calcul Quantité × Prix, et calculez le total général." solution="Formule RECHERCHEV : `=RECHERCHEV(D1,A2:B10,2,FAUX)`. Calcul Quantité × Prix : `=A2*B2`. Total général : `=SOMME(C2:C10)`." %}

---

### **Exercice 5 : Tri et Filtrage**

{% include question.html header="Exercice 5 - Tri et Filtrage" text="Triez les données par note en ordre décroissant et filtrez les notes supérieures à 60. Bonus : ajoutez une liste déroulante pour filtrer par matière." solution="Triez par ordre décroissant en sélectionnant la colonne des notes. Appliquez un filtre avec critère '>60'. Pour la liste déroulante : Données > Validation de données > Liste, entrez les matières comme options." %}

---

### **Exercice 6 : Calculs avec des Dates**

{% include question.html header="Exercice 6 - Calculs avec des Dates" text="Ajoutez une colonne pour calculer la durée (en jours) entre la date de début et la date de fin. Calculez la moyenne des durées. Bonus : ajoutez une colonne indiquant si la durée est supérieure ou inférieure à 30 jours." solution="Durée : `=B2-A2`. Moyenne des durées : `=MOYENNE(D2:D10)`. Comparaison avec 30 jours : `=SI(D2>30,'Supérieur','Inférieur')`." %}

---

### **Exercice 7 : Consolidation des Données**

{% include question.html header="Exercice 7 - Consolidation avec SOMME.SI" text="Utilisez SOMME.SI pour calculer la somme des ventes pour chaque région dans une table récapitulative. Bonus : ajoutez un graphique circulaire des ventes par région." solution="Formule SOMME.SI : `=SOMME.SI(A2:A10,'Région1',B2:B10)`. Créez un graphique circulaire à partir des données consolidées des ventes par région." %}

---

### **Exercice 8 : Analyse de Sensibilité**

{% include question.html header="Exercice 8 - Analyse de Sensibilité" text="Ajoutez une cellule pour définir un paramètre de réduction (exemple : 10 %). Créez une colonne pour calculer le Total après Réduction, puis modifiez la valeur du paramètre pour observer les impacts." solution="Ajoutez une cellule (ex. `E1`) avec la réduction (ex. `0.1`). Formule pour le Total après Réduction : `=C2*(1-$E$1)`. Modifiez la valeur dans `E1` pour voir l’impact." %}
