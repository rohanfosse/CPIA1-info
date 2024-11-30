---
section: Python
nav_order: 7
title: Structures de Données
topics: Listes; Tuples; Dictionnaires; Ensembles; Manipulation de données
---

Les collections de données permettent de stocker et manipuler plusieurs valeurs dans une seule variable. Python propose plusieurs types de collections pour différents usages : les listes, tuples, dictionnaires, et ensembles.

## Les Listes

Les **listes** sont des collections ordonnées et modifiables. Elles peuvent contenir des éléments de types différents et permettent d'ajouter, supprimer ou modifier des éléments.

### Créer et Manipuler des Listes

**Exemples** :

```python
# Création d'une liste
fruits = ["pomme", "banane", "cerise"]

# Ajouter un élément
fruits.append("orange")

# Insérer un élément à un indice spécifique
fruits.insert(1, "mangue")

# Supprimer un élément
fruits.remove("banane")

# Accéder à un élément par son indice
print(fruits[0])  # Affiche "pomme"
```

### Fonctions Utiles

| Fonction           | Description                                  |
|--------------------|----------------------------------------------|
| `append(element)`  | Ajoute un élément à la fin de la liste       |
| `insert(index, element)` | Insère un élément à un indice donné    |
| `remove(element)` | Supprime le premier élément correspondant     |
| `pop(index)`      | Supprime l’élément à l’indice donné et le retourne |
| `sort()`          | Trie la liste                                |
| `reverse()`       | Inverse l’ordre des éléments                 |

---

## Les Tuples

Les **tuples** sont similaires aux listes, mais ils sont **immuables** : une fois créés, leurs éléments ne peuvent pas être modifiés. Les tuples sont souvent utilisés pour des données qui ne doivent pas changer.

### Créer et Utiliser des Tuples

**Exemple** :

```python
coordonnees = (10, 20)
print(coordonnees[0])  # Accède au premier élément

# Déballer un tuple
x, y = coordonnees
print(x)  # Affiche 10
print(y)  # Affiche 20
```

Les tuples sont utiles pour retourner plusieurs valeurs depuis une fonction ou pour regrouper des informations non modifiables.

---

## Les Dictionnaires

Les **dictionnaires** sont des collections non ordonnées de paires clé-valeur, permettant un accès rapide aux valeurs en utilisant des clés.

### Créer et Manipuler des Dictionnaires

**Exemple** :

```python
# Création d'un dictionnaire
etudiant = {
    "nom": "Alice",
    "age": 22,
    "ville": "Paris"
}

# Accéder à une valeur
print(etudiant["nom"])  # Affiche "Alice"

# Ajouter ou modifier une clé
etudiant["age"] = 23

# Supprimer une clé
del etudiant["ville"]
```

### Méthodes Utiles

| Méthode              | Description                                     |
|----------------------|-------------------------------------------------|
| `get(clé)`          | Récupère la valeur associée à la clé            |
| `keys()`            | Retourne une liste de toutes les clés           |
| `values()`          | Retourne une liste de toutes les valeurs        |
| `items()`           | Retourne une liste de paires clé-valeur         |
| `pop(clé)`          | Supprime la clé spécifiée et retourne sa valeur |

---

## Les Ensembles

Les **ensembles** sont des collections non ordonnées et sans doublons. Ils sont utiles pour vérifier l’appartenance d’un élément ou pour des opérations d’ensemble comme l'union et l'intersection.

### Créer et Utiliser des Ensembles

**Exemple** :

```python
# Création d'un ensemble
nombres = {1, 2, 3, 4}

# Ajouter un élément
nombres.add(5)

# Supprimer un élément
nombres.discard(3)
```

### Opérations sur les Ensembles

| Opération            | Description                                     |
|----------------------|-------------------------------------------------|
| `union()`            | Union de deux ensembles                         |
| `intersection()`     | Intersection de deux ensembles                  |
| `difference()`       | Différence entre deux ensembles                 |
| `issubset()`         | Vérifie si un ensemble est un sous-ensemble     |

**Exemple d'union et d'intersection** :

```python
A = {1, 2, 3}
B = {3, 4, 5}
print(A.union(B))         # Affiche {1, 2, 3, 4, 5}
print(A.intersection(B))  # Affiche {3}
```

---

## Choisir la Bonne Collection

| Type       | Ordonné | Modifiable | Clé-accès    | Usage principal                        |
|------------|---------|------------|--------------|----------------------------------------|
| Liste      | Oui     | Oui        | Indices      | Collection ordonnée et modifiable      |
| Tuple      | Oui     | Non        | Indices      | Données non modifiables                |
| Dictionnaire | Non  | Oui        | Clés         | Association clé-valeur                 |
| Ensemble   | Non     | Oui        | Non applicable | Collection sans doublons              |

---

## Exercices Pratiques

### Exercice 1

Créez une liste de trois prénoms et ajoutez-en un quatrième. Affichez la liste triée dans l’ordre alphabétique.

### Exercice 2

Créez un dictionnaire représentant une personne avec les clés `nom`, `age`, et `ville`. Modifiez l’âge et affichez le dictionnaire mis à jour.

### Exercice 3

Créez deux ensembles `A` et `B` avec des éléments communs. Affichez l’union et l’intersection de ces ensembles.

---

## Résumé des Commandes de Base

| Structure             | Description                                    |
|-----------------------|------------------------------------------------|
| `append()`, `insert()` | Ajouter des éléments à une liste              |
| `sort()`, `reverse()` | Trier et inverser une liste                    |
| `get()`, `keys()`, `values()` | Accéder aux clés et valeurs d'un dictionnaire |
| `union()`, `intersection()` | Opérations d'ensemble                    |

Ce chapitre vous introduit aux collections de données en Python, offrant différentes structures pour stocker et manipuler des données. Dans le prochain chapitre, nous explorerons des techniques pour travailler avec ces collections et écrire des programmes plus avancés.