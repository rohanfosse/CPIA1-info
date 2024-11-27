---
section: Excel
nav_order: 3
title: Correction EI Blanc Excel
topics: Excel, Correction
---

## **Correction Épreuve Initiale Excel**

#### **Étape 1 : Fixer les paramètres dans des cellules**

**Question :**  
Placez les paramètres fournis (`C_0`, `P_base`, `P_moyen`, `k_T`, `k_A`, `Δt`) dans une zone dédiée de votre feuille Excel.

**Solution :**  
1. Créez une zone dédiée (par exemple, colonne H) pour les paramètres.
2. Remplissez les cellules comme suit :
   - `H1` : `C_0` avec la valeur `0`.
   - `H2` : `P_base` avec la valeur `200`.
   - `H3` : `P_moyen` avec la valeur `50`.
   - `H4` : `k_T` avec la valeur `5`.
   - `H5` : `k_A` avec la valeur `100`.
   - `H6` : `Δt` avec la valeur `1`.

---

#### **Étape 2 : Ajouter une colonne `C(t)`**

**Question :**  
Implémentez l’équation récurrente dans une colonne `C(t)` pour calculer la consommation horaire cumulée.

**Solution :**  
1. Dans l’onglet **Data**, ajoutez une colonne `C(t)` à côté des données `N(t)`, `T(t)` et `A(t)`.
2. Remplissez les valeurs selon l’équation récurrente :
   - En supposant que les données commencent en ligne 2 et que les paramètres sont dans la colonne H :
     - `C(t)` pour la ligne 2 (cellule `E2`) :  
       `= $H$1 + $H$6 * ($H$2 + B2 * $H$3 + C2 * $H$4 + D2 * $H$5)`
     - Pour les lignes suivantes (ex. ligne 3, cellule `E3`) :  
       `= E2 + $H$6 * ($H$2 + B3 * $H$3 + C3 * $H$4 + D3 * $H$5)`.
   - Faites glisser la formule vers le bas pour remplir toutes les lignes.

---

#### **Étape 3 : Vérification et Analyse**

**Question :**  
1. Calculez 50 % de la valeur maximale de `C(t)`.  
2. Ajoutez une colonne `Vérification` pour indiquer si `C(t)` dépasse cette valeur avec "Oui" ou "Non".

**Solution :**  
1. Pour calculer 50 % de la valeur maximale :
   - En dessous de la colonne `C(t)` (par ex. cellule `E50`) :  
     `=MAX(E2:E49) * 0.5`.

2. Créez une colonne `Vérification` et remplissez-la avec une formule conditionnelle :
   - Dans la colonne `F`, pour la ligne 2 (cellule `F2`) :  
     `=SI(E2 >= $E$50, "Oui", "Non")`.
   - Faites glisser la formule vers le bas pour toutes les lignes.

---

#### **Étape 4 : Visualisation Graphique et Analyse Supplémentaire**

**Question :**  
1. Tracez un graphique de `C(t)` en fonction du temps.  
2. Créez un graphique en barres basé sur la répartition des "Oui" et "Non".  
3. Affichez la proportion de "Oui" et déterminez si le bâtiment dépasse 50 % de sa consommation maximale sur plus de la moitié de la journée.

**Solution :**  
1. **Graphique de `C(t)`** :  
   - Sélectionnez la colonne des heures et `C(t)`, puis insérez un graphique de type courbe.

2. **Graphique en barres** :  
   - Comptez le nombre de "Oui" et "Non" :
     - `=NB.SI(F2:F49,"Oui")` pour "Oui".
     - `=NB.SI(F2:F49,"Non")` pour "Non".
   - Créez un graphique en barres à partir de ces données.

3. **Proportion de "Oui"** :  
   - Calculer le pourcentage :  
     `=NB.SI(F2:F49,"Oui") / NBVAL(F2:F49) * 100`.
   - Indiquez si le bâtiment dépasse 50 % de sa consommation maximale sur plus de la moitié de la journée :
     - Vérifiez si la proportion de "Oui" est supérieure à 50 %.