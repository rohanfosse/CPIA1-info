---
title: "Renforcement EI Python - Correction"
layout: lesson-content
permalink: /Renforcement-corrige.html
---

## **Correction – Partie 1 : Traitement des données**

### **1. Création des listes (2 points)**

#### **Correction attendue :**

```python
# Liste des ventes pour chaque jour
ventes_jour1 = [12, 25, 18, 30, 22]
ventes_jour2 = [14, 28, 21, 27, 20]
ventes_jour3 = [10, 22, 20, 25, 18]
```

#### **Explication :**

- **Écrire chaque liste séparément** avec les **crochets** `[]` et les **valeurs séparées par des virgules**.
- **Ne pas utiliser une seule liste** contenant toutes les valeurs mélangées.

---

### **2. Calcul du total des ventes par jour (5 points)**

#### **Correction attendue :**

```python
# Fonction pour calculer le total des ventes d'un jour
def calculer_total_ventes(ventes_jour):
    total = 0  # Initialisation du total à 0
    for vente in ventes_jour:  # Parcourir chaque vente dans la liste
        total = total + vente  # Ajouter la vente au total
    return total  # Retourner le total
```

#### **Explication :**

1. **Déclaration de la fonction** `calculer_total_ventes()`.
2. **Création d'une variable `total` initialisée à 0**.
3. **Boucle `for` pour additionner chaque élément de la liste** ().
4. **Retour du total**.

Exemple d’appel :

```python
total_jour1 = calculer_total_ventes(ventes_jour1)  # Calcul du total pour le jour 1
```

Si vous calculez **sur papier** :

- Jour 1 : 12 + 25 + 18 + 30 + 22 = **107**
- Jour 2 : 14 + 28 + 21 + 27 + 20 = **110**
- Jour 3 : 10 + 22 + 20 + 25 + 18 = **95**

---

### **3. Calcul de la moyenne des ventes par produit (5 points)**

#### **Correction attendue :**

```python
# Fonction pour calculer la moyenne des ventes par produit sur 3 jours
def calculer_moyenne_ventes(ventes_jour1, ventes_jour2, ventes_jour3):
    moyenne = [0, 0, 0, 0, 0]  # Initialisation de la liste des moyennes
    for i in range(5):  # Parcourir les indices des produits (0 à 4)
        total = ventes_jour1[i] + ventes_jour2[i] + ventes_jour3[i]  # Additionner les ventes des 3 jours
        moyenne[i] = total / 3  # Calcul de la moyenne et affectation dans la liste
    return moyenne
```

#### **Explication :**

1. **Initialisation d’une liste `moyenne` avec des zéros** (une case par produit).
2. **Boucle `for` qui parcourt les indices des produits (0 à 4)**.
3. **Calcul du total des ventes sur 3 jours** (sans `sum()`).
4. **Division par 3** pour obtenir la moyenne.

Si vous calculez **sur papier** :

- Produit 1 : (12 + 14 + 10) / 3 = **12.0**
- Produit 2 : (25 + 28 + 22) / 3 = **25.0**
- Produit 3 : (18 + 21 + 20) / 3 = **19.67**
- Produit 4 : (30 + 27 + 25) / 3 = **27.33**
- Produit 5 : (22 + 20 + 18) / 3 = **20.0**

---

## **Correction – Partie 2 : Analyse des ventes et affichage**

### **4. Trouver le produit le plus vendu (3 points)**

#### **Correction attendue :**

```python
# Fonction pour trouver le produit avec la plus grande moyenne de ventes
def produit_plus_vendu(ventes_jour1, ventes_jour2, ventes_jour3):
    moyennes = calculer_moyenne_ventes(ventes_jour1, ventes_jour2, ventes_jour3)

    max_moyenne = moyennes[0]  # Initialisation avec la première valeur
    produit_max = 1  # Produit correspondant

    for i in range(1, 5):  # Parcourir les indices de 1 à 4
        if moyennes[i] > max_moyenne:  # Comparer avec la valeur maximale actuelle
            max_moyenne = moyennes[i]  # Mettre à jour la valeur max
            produit_max = i + 1  # Mettre à jour le produit correspondant

    return produit_max  # Retourner le produit le plus vendu
```

#### **Explication :**

1. **Calcul de la moyenne des ventes avec `calculer_moyenne_ventes()`**.
2. **Initialisation de `max_moyenne` avec la première valeur** et `produit_max` à 1.
3. **Boucle `for` qui compare chaque moyenne et met à jour la valeur la plus grande**.
4. **Retourne le numéro du produit le plus vendu**.

---

### **5. Trouver le jour avec le plus de ventes (3 points)**

#### **Correction attendue :**

```python
# Fonction pour trouver le jour avec le plus de ventes
def jour_plus_vendu(ventes_jour1, ventes_jour2, ventes_jour3):
    total1 = calculer_total_ventes(ventes_jour1)
    total2 = calculer_total_ventes(ventes_jour2)
    total3 = calculer_total_ventes(ventes_jour3)

    if total1 > total2 and total1 > total3:
        return 1
    elif total2 > total1 and total2 > total3:
        return 2
    else:
        return 3
```

#### **Explication :**

1. **Calcul du total des ventes pour chaque jour** avec `calculer_total_ventes()`.
2. **Utilisation de `if / elif / else` pour comparer les totaux** et retourner le jour avec le plus de ventes.

---

### **6. Décrire le graphique attendu (2 points)**

- **Type de graphique :** Un graphique **en courbes**.
- **Axes :**
  - **Axe X (horizontal)** : Produits (**numérotés de 1 à 5**).
  - **Axe Y (vertical)** : Nombre de ventes.
- **Légende :**
  - Une couleur différente pour **chaque jour**.
- **Interprétation :**
  - Ce graphique permet de comparer les **évolutions des ventes** sur 3 jours.

---
