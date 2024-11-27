---
section: Excel
nav_order: 4
title: Exercices Supplémentaires
topics: Excel, Exercices
---


Voici une série d'exercices rapides pour améliorer vos compétences en Excel, couvrant différentes fonctionnalités comme les formules, les graphiques, et les analyses de données.

Vous pouvez télécharger le fichier de base pour les exercices : [Donnees_Exercices.xlsx](Exercices_Excel.xlsx)

---

### **Exercice 1 : Somme Automatique et Calculs de Base**

#### **Objectif :**  
Pratiquer les formules arithmétiques de base.

1. **Instructions :**
   - Créez une colonne C pour le calcul du **Total** (Quantité × Prix unitaire).
   - En dessous de la colonne C, calculez :
     - La **somme totale**.
     - La **valeur moyenne**.

2. **Bonus :**
   - Ajoutez une colonne D avec une réduction de 10 % sur chaque total.
   - Créez une colonne E pour le **Total après Réduction**.

---

### **Exercice 2 : Mise en Forme Conditionnelle**

#### **Objectif :**
Appliquer une mise en forme conditionnelle pour mettre en évidence certaines valeurs.

1. **Instructions :**
   - Appliquez une mise en forme conditionnelle pour :
     - Mettre les scores **supérieurs à 70** en vert.
     - Mettre les scores **inférieurs à 50** en rouge.

2. **Bonus :**
   - Ajoutez une colonne C avec des commentaires automatiques en utilisant la formule `SI` :
     - "Bon" si le score est supérieur ou égal à 70.
     - "À améliorer" sinon.

---

### **Exercice 3 : Création d’un Graphique Simple**

#### **Objectif :**
Créer un graphique pour visualiser des données.

1. **Instructions :**
   - Créez un graphique de type **Histogramme** pour représenter les ventes par mois.
   - Ajoutez un titre au graphique : **"Ventes Mensuelles"**.
   - Ajoutez des étiquettes sur les axes (Axe X : Mois, Axe Y : Ventes).

2. **Bonus :**
   - Ajoutez une ligne de tendance sur le graphique pour observer la progression des ventes.

---

### **Exercice 4 : Recherche et Correspondance**

#### **Objectif :**
Utiliser la fonction `RECHERCHEV` pour rechercher des données dans une table.

1. **Instructions :**
   - Créez une cellule où l’utilisateur peut entrer le nom d’un produit.
   - Utilisez `RECHERCHEV` pour afficher automatiquement le prix correspondant.

2. **Bonus :**
   - Ajoutez une colonne C avec un calcul automatique de la quantité × prix.
   - Calculez le total général des ventes.

---

### **Exercice 5 : Tri et Filtrage**

#### **Objectif :**
Utiliser les fonctionnalités de tri et de filtre dans Excel.

1. **Instructions :**
   - Triez les données par note (ordre décroissant).
   - Appliquez un filtre pour afficher uniquement les étudiants ayant une note supérieure à 60.

2. **Bonus :**
   - Créez une cellule avec une liste déroulante pour filtrer les données par matière.

---

### **Exercice 6 : Calculs avec des Dates**

#### **Objectif :**
Effectuer des calculs sur des dates.

1. **Instructions :**
   - Créez une colonne D pour calculer la durée (en jours) entre la date de début et la date de fin.
   - Calculez la moyenne des durées dans une cellule.

2. **Bonus :**
   - Ajoutez une colonne E pour afficher si la durée est supérieure ou inférieure à 30 jours (utilisez `SI`).

---

### **Exercice 7 : Consolidation des Données**

#### **Objectif :**
Utiliser la fonction `SOMME.SI` pour consolider des données.

1. **Instructions :**
   - Utilisez `SOMME.SI` pour calculer la somme des ventes pour chaque région dans une table récapitulative.

2. **Bonus :**
   - Ajoutez un graphique circulaire représentant les ventes par région.

---

### **Exercice 8 : Analyse de Sensibilité**

#### **Objectif :**
Observer l’impact de la variation d’un paramètre sur des calculs.

1. **Instructions :**
   - Ajoutez une cellule avec un paramètre de réduction (par exemple : 10 %).
   - Créez une colonne D pour calculer le **Total après Réduction**.
   - Modifiez la valeur de la réduction pour observer son impact.

---

## Correction des Exercices

Voici la réécriture complète des exercices et solutions avec le format demandé :

---

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
