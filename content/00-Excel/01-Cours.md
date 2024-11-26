---
section_id: Excel
nav_order: 1
title: Cours Excel
topics: Excel, Étude de Cas
---

Ce cours est conçu pour vous apprendre les bases nécessaires pour structurer, analyser et modéliser des données efficacement dans Excel. Nous couvrirons :

1. Organisation et structuration des données.
2. Utilisation de formules simples et avancées.
3. Calculs conditionnels et statistiques.
4. Création de graphiques pour représenter et analyser les données.

---

### **1. Organisation et Structuration des Données**

#### **Objectif**

Organiser vos données de manière claire et exploitable pour faciliter les calculs et les analyses.

#### **Principes**

1. **Structurer vos données :**

   - Chaque colonne représente une variable unique (par exemple : `Temps`, `Valeur Mesurée`, `Paramètre`).
   - Utilisez des titres explicites pour vos colonnes.

2. **Créer une zone de paramètres :**

   - Réservez une zone spécifique pour les constantes ou paramètres utilisés dans vos calculs (par exemple, `Paramètres`).
   - Exemple :

     | **Paramètre** | **Valeur** |
     |---------------|------------|
     | Constante A | 100 |
     | Constante B | 50 |

3. **Ne pas mélanger les données et les calculs :**
   - Placez vos données brutes dans une section dédiée.
   - Placez les calculs dans des colonnes séparées.

#### **Outils Utiles**

- **Format en tableau** : sélectionnez vos données et appliquez un style via **Accueil > Mettre sous forme de tableau**.
- **Filtres** : utilisez **Données > Filtrer** pour afficher uniquement certaines valeurs.

---

### **2. Utilisation des Formules**

#### **Objectif**

Automatiser les calculs avec des formules adaptées.

---

#### **Commandes Clés**

1. **Références Relatives et Absolues :**

##### **Explications :**

- **Référence Relative** (`A1`) :

  - Change automatiquement lorsque la formule est copiée vers une autre cellule.
  - Exemple : Si vous copiez la formule `=A1 + B1` de la cellule **C1** à **C2**, elle devient `=A2 + B2`.

- **Référence Absolue** (`$A$1`) :
  - Reste fixe, même si la formule est copiée.
  - Exemple : Si vous copiez la formule `=$A$1 + B1` de la cellule **C1** à **C2**, elle reste `=$A$1 + B2`.

##### **Exemple Pratique :**

- Supposons que vous ayez une constante dans la cellule **D1**, et que vous souhaitiez l’ajouter à toutes les valeurs de la colonne A :
  - Placez la formule `=A1 + $D$1` dans **B1**.
  - Copiez la formule vers le bas. La référence à **$D$1** reste fixe, mais la référence à **A1** devient relative et s’ajuste automatiquement (A2, A3, ...).

2. **Opérations de Base :**

   - Addition : `=A1 + B1`
   - Soustraction : `=A1 - B1`
   - Multiplication : `=A1 * B1`
   - Division : `=A1 / B1`
   - Exemple : Calculez la somme des colonnes A et B, ligne par ligne :

     ```excel
     =A1 + B1
     ```

3. **Utiliser des Plages de Données :**

   - Exemple : Additionner toutes les valeurs de la colonne A :

     ```excel
     =SUM(A:A)
     ```

4. **Formules Avancées :**

   - **PUISSANCE :**
     - Pour élever une valeur à une puissance donnée.

     ```excel
     =POWER(A1, 2)  // Équivaut à A1^2
     ```

   - **RACINE :**

     - Pour calculer la racine carrée d'une valeur.

     ```excel
     =SQRT(A1)
     ```

   - **TRONQUER :**
     - Pour arrondir une valeur en supprimant les décimales.

     ```excel
     =TRUNC(A1)
     ```

5. **Formules Conditionnelles :**

   - **SI :**
     - Exemple : Vérifier si une valeur est supérieure à 100.

       ```excel
       =IF(A1 > 100, "Oui", "Non")
       ```

   - **ET :**
     - Exemple : Vérifier si une valeur est supérieure à 100 et inférieure à 200.

       ```excel
       =IF(AND(A1 > 100, A1 < 200), "Valide", "Invalide")
       ```

   - **OU :**
     - Exemple : Vérifier si une valeur est supérieure à 100 ou égale à 50.

       ```excel
       =IF(OR(A1 > 100, A1 = 50), "Valide", "Invalide")
       ```

6. **Éviter les erreurs avec `IFERROR` :**

   - Si une division retourne une erreur (par exemple, division par zéro), affichez une valeur par défaut.

     ```excel
     =IFERROR(A1 / B1, "Erreur")
     ```

---

### **3. Calculs Statistiques**

#### **Objectif**

Analyser les données en calculant des indicateurs statistiques.

#### **Commandes**

1. **Maximum et Minimum :**

   - Trouver la valeur maximale :

     ```excel
     =MAX(A:A)
     ```

   - Trouver la valeur minimale :

     ```excel
     =MIN(A:A)
     ```

2. **Moyenne :**

   - Calculer la moyenne des données :

     ```excel
     =AVERAGE(A:A)
     ```

3. **Somme :**

   - Additionner toutes les valeurs d’une colonne :

     ```excel
     =SUM(A:A)
     ```

4. **Compter des valeurs spécifiques :**

   - Compter combien de fois une valeur apparaît :

     ```excel
     =COUNTIF(A:A, "Oui")
     ```

---

### **4. Création de Graphiques**

#### **Objectif**

Visualiser les données pour en extraire des informations pertinentes.

#### **Étapes pour Créer un Graphique**

1. Sélectionnez les colonnes contenant les données à représenter.
2. Allez dans **Insertion > Graphiques**.
3. Choisissez le type de graphique adapté :
   - **Courbe** : pour suivre une tendance dans le temps.
   - **Histogramme** : pour comparer des valeurs discrètes.
   - **Graphique en barres** : pour afficher une répartition (ex. : "Oui" vs "Non").

#### **Personnalisation**

- Ajoutez des titres :
  - Titre principal : décrit le graphique.
  - Titres des axes : précisent les données représentées.
- Ajoutez une légende pour identifier les séries.

---

### **5. Trucs et Astuces**

#### **Automatisation**

1. **Étendre des formules :**

   - Saisissez une formule dans une cellule, puis étendez-la vers le bas en double-cliquant sur le coin inférieur droit de la cellule.

2. **Références Dynamiques :**
   - Donnez un nom à une plage (ex. `Données`) via **Formules > Définir un nom** pour éviter de référencer directement des plages comme `A1:A10`.

#### **Manipulation des Données**

1. **Tri :**

   - Classez les données dans un ordre croissant ou décroissant via **Données > Trier**.

2. **Filtrage :**
   - Affichez uniquement certaines lignes en fonction de critères via **Données > Filtrer**.

#### **Validation**

1. **Mettre en évidence des erreurs :**

   - Utilisez **Formules > Vérification des erreurs** pour détecter les erreurs dans vos calculs.

2. **Mise en forme conditionnelle :**
   - Mettez en évidence des valeurs spécifiques avec **Accueil > Mise en forme conditionnelle**.
