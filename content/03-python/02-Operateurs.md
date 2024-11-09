---
section_id: Python
nav_order: 3
title: Opérateurs et Expressions
topics: Opérateurs; Calculs; Comparaisons; Expressions
---

Les opérateurs et expressions permettent de réaliser des calculs, des comparaisons, et bien d’autres opérations en Python. Ils constituent le cœur des programmes en manipulant les valeurs stockées dans les variables.

## Types d'Opérateurs en Python

Python propose plusieurs types d'opérateurs pour effectuer des opérations diverses :

### 1. Opérateurs Arithmétiques

Les opérateurs arithmétiques servent à réaliser des calculs mathématiques de base :

- **Addition** : `+`
- **Soustraction** : `-`
- **Multiplication** : `*`
- **Division** : `/`
- **Exponentiation** : `**`
- **Division entière** : `//`
- **Modulo** : `%` (reste de la division)

**Exemple** :

```python
a = 10
b = 3
print(a + b)   # Affiche 13
print(a ** b)  # Affiche 1000
print(a % b)   # Affiche 1
```

### 2. Opérateurs de Comparaison

Les opérateurs de comparaison permettent de comparer deux valeurs et de retourner un booléen (`True` ou `False`) :

- **Égal à** : `==`
- **Différent de** : `!=`
- **Plus grand que** : `>`
- **Plus petit que** : `<`
- **Plus grand ou égal à** : `>=`
- **Plus petit ou égal à** : `<=`

**Exemple** :

```python
x = 5
y = 10
print(x == y)   # Affiche False
print(x < y)    # Affiche True
```

### 3. Opérateurs Logiques

Les opérateurs logiques permettent de combiner des expressions booléennes :

- **ET** : `and`
- **OU** : `or`
- **NON** : `not`

**Exemple** :

```python
a = True
b = False
print(a and b)  # Affiche False
print(a or b)   # Affiche True
print(not a)    # Affiche False
```

### 4. Opérateurs d’Assignation

Les opérateurs d’assignation permettent de modifier et de mettre à jour les valeurs des variables :

- **Assignation simple** : `=`
- **Addition et assignation** : `+=`
- **Soustraction et assignation** : `-=`
- **Multiplication et assignation** : `*=`
- **Division et assignation** : `/=`

**Exemple** :

```python
nombre = 10
nombre += 5    # nombre vaut maintenant 15
print(nombre)
```

### 5. Opérateurs d'Appartenance

Les opérateurs d’appartenance servent à vérifier si un élément fait partie d’une collection comme une liste ou une chaîne de caractères :

- **Dans** : `in`
- **Pas dans** : `not in`

**Exemple** :

```python
fruits = ["pomme", "banane", "cerise"]
print("pomme" in fruits)       # Affiche True
print("orange" not in fruits)  # Affiche True
```

---

## Les Expressions en Python

Une expression est une combinaison de valeurs, de variables et d'opérateurs qui renvoie un résultat. Les expressions sont évaluées de gauche à droite, en respectant la priorité des opérateurs.

### Priorité des Opérateurs

La priorité des opérateurs détermine l’ordre dans lequel les parties d’une expression sont évaluées. Par exemple, la multiplication est prioritaire sur l’addition :

**Exemple** :

```python
resultat = 10 + 5 * 2  # Évalué comme 10 + (5 * 2) = 20
print(resultat)        # Affiche 20
```

Ordre de priorité en Python (de la plus haute à la plus basse) :
1. **Parenthèses** : `()`
2. **Exponentiation** : `**`
3. **Multiplication**, **Division**, **Modulo**, **Division entière** : `*`, `/`, `%`, `//`
4. **Addition** et **Soustraction** : `+`, `-`
5. **Opérateurs de Comparaison** : `==`, `!=`, `>`, `<`, `>=`, `<=`
6. **Opérateurs Logiques** : `not`, `and`, `or`

### Utiliser des Parenthèses pour Structurer les Expressions

Les parenthèses permettent de forcer l’ordre d’évaluation des opérations. En ajoutant des parenthèses, vous pouvez personnaliser la priorité pour structurer les calculs :

```python
resultat = (10 + 5) * 2  # Évalué comme (10 + 5) * 2 = 30
print(resultat)          # Affiche 30
```

---

## Exercices pratiques

### Exercice 1

Créez une expression pour vérifier si un nombre est supérieur à 10 et inférieur à 20. Utilisez les opérateurs de comparaison et logiques.

### Exercice 2

Écrivez une expression qui additionne deux variables `x` et `y`, puis multiplie le résultat par `z`. Utilisez des parenthèses pour contrôler l’ordre d’évaluation.

### Exercice 3

Utilisez l'opérateur `in` pour vérifier si un mot est contenu dans une phrase (variable `phrase`). Affichez `True` ou `False` selon le résultat.

---

## Résumé des commandes de base

| Opérateur             | Description                                    |
|-----------------------|------------------------------------------------|
| `+`, `-`, `*`, `/`   | Opérateurs mathématiques de base               |
| `**`, `//`, `%`      | Exponentiation, division entière, modulo       |
| `==`, `!=`, `>`, `<` | Opérateurs de comparaison                      |
| `and`, `or`, `not`   | Opérateurs logiques                            |
| `in`, `not in`       | Vérifie l’appartenance à une collection        |
| `+=`, `-=`, `*=`     | Opérateurs d’assignation combinée              |

Ce chapitre vous introduit aux opérateurs et expressions, vous permettant d’écrire des calculs et des comparaisons. Dans le prochain chapitre, nous verrons comment structurer un programme avec des **structures de contrôle de flux** pour créer des scripts interactifs.