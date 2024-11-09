---
section: Python
nav_order: 5
title: Fonctions
topics: Fonctions; Arguments; Valeurs de retour; Portée des variables
---

Les fonctions permettent de structurer et de réutiliser le code, en définissant des blocs d’instructions qui peuvent être appelés à plusieurs endroits dans le programme. Elles facilitent la gestion de programmes plus longs et organisent le code en modules.

## Qu'est-ce qu'une Fonction ?

Une fonction est un bloc de code qui exécute une tâche spécifique. Les fonctions peuvent recevoir des **arguments** en entrée et retourner une **valeur** en sortie. En Python, les fonctions sont définies avec le mot-clé `def`.

### Syntaxe de Base

```python
def nom_de_la_fonction(parametre1, parametre2):
    # Instructions de la fonction
    return valeur_de_retour
```

**Exemple** :

```python
def saluer(nom):
    return "Bonjour, " + nom

print(saluer("Alice"))  # Affiche "Bonjour, Alice"
```

---

## Les Paramètres et Arguments

Les **paramètres** sont des variables définies dans la déclaration de la fonction, tandis que les **arguments** sont les valeurs passées à la fonction lors de son appel.

### Paramètres par Défaut

Vous pouvez définir des valeurs par défaut pour les paramètres, qui seront utilisées si aucun argument n’est fourni lors de l’appel de la fonction.

**Exemple** :

```python
def saluer(nom="inconnu"):
    return "Bonjour, " + nom

print(saluer())          # Affiche "Bonjour, inconnu"
print(saluer("Alice"))   # Affiche "Bonjour, Alice"
```

### Paramètres Positionnels et Només

Les arguments peuvent être passés selon leur position ou de manière explicite en nommant les paramètres.

**Exemple** :

```python
def decrire_personne(nom, age):
    print(f"{nom} a {age} ans.")

decrire_personne("Alice", 30)       # Utilisation positionnelle
decrire_personne(age=30, nom="Bob") # Utilisation nommée
```

---

## Valeurs de Retour

La valeur de retour est la donnée qu’une fonction renvoie une fois qu’elle a terminé son exécution. Pour renvoyer une valeur, on utilise le mot-clé `return`.

**Exemple** :

```python
def addition(a, b):
    return a + b

resultat = addition(5, 3)
print(resultat)  # Affiche 8
```

---

## Portée des Variables

Les variables définies à l'intérieur d'une fonction ont une **portée locale**, ce qui signifie qu'elles ne sont accessibles qu'à l'intérieur de la fonction. Les variables définies en dehors de toute fonction ont une **portée globale**.

**Exemple** :

```python
x = 10  # Variable globale

def ma_fonction():
    x = 5  # Variable locale
    print("Valeur de x dans la fonction:", x)

ma_fonction()  
print("Valeur de x en dehors de la fonction:", x)
```

Cela affiche :
```
Valeur de x dans la fonction: 5
Valeur de x en dehors de la fonction: 10
```

### Utiliser `global`

Pour modifier une variable globale à l'intérieur d'une fonction, on peut utiliser le mot-clé `global`.

**Exemple** :

```python
x = 10

def modifier_x():
    global x
    x = 5

modifier_x()
print(x)  # Affiche 5
```

---

## Fonctions Lambda

Les fonctions lambda sont des fonctions anonymes, utilisées pour des opérations simples et définies en une ligne. Elles sont souvent utilisées avec des fonctions comme `map()`, `filter()` et `sorted()`.

**Syntaxe** :

```python
lambda parametre1, parametre2: expression
```

**Exemple** :

```python
addition = lambda x, y: x + y
print(addition(5, 3))  # Affiche 8
```

---

## Exercices Pratiques

### Exercice 1

Écrivez une fonction `carre(nombre)` qui retourne le carré d'un nombre. Appelez cette fonction avec différents arguments et affichez les résultats.

### Exercice 2

Créez une fonction `aire_rectangle(longueur, largeur)` qui calcule l’aire d’un rectangle. Donnez une valeur par défaut à `largeur` et appelez la fonction sans ce paramètre.

### Exercice 3

Écrivez une fonction lambda qui prend un nombre en paramètre et retourne `True` s'il est pair, sinon `False`.

---

## Résumé des Commandes de Base

| Structure               | Description                                    |
|-------------------------|------------------------------------------------|
| `def`                   | Définit une fonction                           |
| `return`                | Retourne une valeur                            |
| `parametre=valeur`      | Définit un paramètre avec valeur par défaut    |
| `lambda`                | Déclare une fonction anonyme                   |
| `global`                | Modifie une variable globale dans une fonction |

Ce chapitre sur les fonctions vous aide à organiser votre code en modules réutilisables et à mieux structurer vos programmes. Dans le prochain chapitre, nous découvrirons les **collections de données** et comment les manipuler en Python.