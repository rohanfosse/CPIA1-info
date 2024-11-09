---
section_id: Python
nav_order: 2
title: Types de Données et Variables
topics: Variables; Types de données; Opérations; Conversion de types
---

Dans ce chapitre, nous allons explorer les concepts de base autour des types de données et des variables en Python. Comprendre comment utiliser et manipuler les données est essentiel pour tout programme Python.

## Qu'est-ce qu'une Variable ?

Une variable est un espace de stockage pour une valeur en Python. Elle permet de donner un nom à une donnée, facilitant la réutilisation et la manipulation de celle-ci dans le code. Contrairement à d'autres langages, vous n'avez pas besoin de déclarer explicitement le type d'une variable en Python. La syntaxe est simple :

```python
nom_de_variable = valeur
```

**Exemple** :

```python
age = 25
nom = "Alice"
est_membre = True
```

---

## Types de Données en Python

Python utilise plusieurs types de données courants. Voici les principaux :

### 1. Entiers (int)

Les entiers représentent des nombres sans décimales :

```python
nombre = 42
```

### 2. Flottants (float)

Les flottants sont des nombres décimaux, utiles pour les calculs plus précis :

```python
pi = 3.14159
```

### 3. Chaînes de caractères (str)

Les chaînes de caractères permettent de stocker du texte et sont placées entre guillemets simples ou doubles :

```python
texte = "Bonjour, Python!"
```

### 4. Booléens (bool)

Les valeurs booléennes sont `True` ou `False` et sont souvent utilisées dans les conditions et comparaisons :

```python
est_actif = True
```

### 5. Listes

Les listes sont des collections ordonnées d'éléments, comme une liste de courses :

```python
fruits = ["pomme", "banane", "cerise"]
```

### 6. Dictionnaires

Les dictionnaires sont des collections de paires clé-valeur, utiles pour représenter des données associatives :

```python
personne = {"nom": "Alice", "age": 30}
```

---

## Manipulation des Variables

Les variables peuvent être modifiées, réutilisées et combinées avec d'autres pour réaliser des calculs ou des opérations.

### Opérateurs de base

Python permet d'effectuer des opérations mathématiques de base :

- Addition : `+`
- Soustraction : `-`
- Multiplication : `*`
- Division : `/`
- Exponentiation : `**`
- Division entière : `//`
- Modulo (reste) : `%`

**Exemple** :

```python
a = 10
b = 3
print(a + b)  # Affiche 13
print(a ** b) # Affiche 1000
```

### Concaténation de Chaînes

Les chaînes de caractères peuvent être combinées avec `+` :

```python
prenom = "Alice"
salutation = "Bonjour, " + prenom
print(salutation)  # Affiche "Bonjour, Alice"
```

---

## Conversion de Types

Python permet de convertir des variables d'un type à un autre, ce qui est utile lors de l'interaction avec des données de types différents.

### Fonctions de conversion

- **int()** : Convertit en entier
- **float()** : Convertit en flottant
- **str()** : Convertit en chaîne de caractères
- **bool()** : Convertit en booléen

**Exemple** :

```python
nombre = "10"
resultat = int(nombre) + 5  # Convertit la chaîne en entier et ajoute 5
print(resultat)  # Affiche 15
```

---

## Bonnes pratiques pour nommer les variables

1. **Utiliser des noms explicites** : Choisissez des noms clairs et compréhensibles (ex. : `age`, `nombre_utilisateurs`).
2. **Suivre la convention snake_case** : Les noms de variables sont en minuscules, avec des underscores pour séparer les mots (ex. : `nom_de_variable`).
3. **Éviter les noms réservés** : Python dispose de mots réservés qu'on ne peut pas utiliser pour nommer une variable (ex. : `class`, `for`, `if`).

---

## Exercices pratiques

### Exercice 1

Créez une variable `age` et assignez-lui une valeur entière. Ajoutez ensuite 5 à cette valeur et affichez le résultat.

### Exercice 2

Créez une variable `nom` contenant votre prénom et une variable `salutation` combinant la chaîne `"Bonjour, "` et votre prénom. Affichez `salutation`.

### Exercice 3

Convertissez une variable contenant `"20"` (sous forme de chaîne) en un entier, ajoutez-y 10, et affichez le résultat.

---

## Résumé des commandes de base

| Commande               | Description                                    |
|------------------------|------------------------------------------------|
| `type(variable)`       | Affiche le type de la variable                 |
| `str(variable)`        | Convertit en chaîne de caractères              |
| `int(variable)`        | Convertit en entier                            |
| `float(variable)`      | Convertit en flottant                          |
| `+`, `-`, `*`, `/`    | Opérateurs mathématiques de base               |
| `**`, `//`, `%`       | Exponentiation, division entière, modulo       |

Ce chapitre sur les types de données et les variables constitue la base de la programmation Python. Dans le prochain chapitre, nous explorerons les opérateurs et les expressions pour effectuer des calculs plus complexes.