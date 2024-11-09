---
section_id: Python
nav_order: 4
title: Conditions et Boucles
topics: Conditions; Boucles; Instructions conditionnelles; Boucles `for` et `while`
---

Les structures de contrôle de flux permettent de guider l'exécution du programme en fonction de certaines conditions ou de répéter des actions. Ces structures constituent un des aspects essentiels de la programmation pour créer des programmes dynamiques.

## Les Instructions Conditionnelles

Les instructions conditionnelles permettent de contrôler l’exécution du code en fonction de certaines conditions. En Python, on utilise les mots-clés `if`, `elif`, et `else`.

### Syntaxe

```python
if condition:
    # Code exécuté si la condition est vraie
elif autre_condition:
    # Code exécuté si l'autre condition est vraie
else:
    # Code exécuté si aucune des conditions n'est vraie
```

**Exemple** :

```python
age = 18
if age >= 18:
    print("Vous êtes majeur.")
else:
    print("Vous êtes mineur.")
```

---

## Les Boucles

Les boucles permettent de répéter une action tant qu’une condition est vérifiée, ou pour chaque élément d’une collection.

### Boucle `while`

La boucle `while` exécute une action tant qu'une condition reste vraie. Elle est souvent utilisée lorsque le nombre d'itérations n'est pas défini à l’avance.

**Syntaxe** :

```python
while condition:
    # Code à exécuter tant que la condition est vraie
```

**Exemple** :

```python
compteur = 0
while compteur < 5:
    print(compteur)
    compteur += 1  # Incrémente le compteur de 1 à chaque itération
```

### Boucle `for`

La boucle `for` permet d’itérer sur une collection (liste, chaîne de caractères, etc.) ou sur une plage de nombres définie avec `range()`.

**Syntaxe** :

```python
for element in collection:
    # Code à exécuter pour chaque élément de la collection
```

**Exemple** :

```python
fruits = ["pomme", "banane", "cerise"]
for fruit in fruits:
    print(fruit)
```

#### Utiliser `range()` avec `for`

La fonction `range()` génère une séquence de nombres. Elle est souvent utilisée pour créer une boucle `for` avec un nombre d’itérations défini.

**Exemple** :

```python
for i in range(5):
    print(i)  # Affiche les nombres de 0 à 4
```

---

## Les Instructions de Contrôle des Boucles

Python propose des instructions pour contrôler l’exécution des boucles de manière plus spécifique.

### `break`

L'instruction `break` permet d'interrompre une boucle immédiatement, quel que soit l'état de la condition.

**Exemple** :

```python
for nombre in range(10):
    if nombre == 5:
        break  # Interrompt la boucle si nombre vaut 5
    print(nombre)
```

### `continue`

L'instruction `continue` saute à l'itération suivante de la boucle, sans terminer complètement la boucle.

**Exemple** :

```python
for nombre in range(5):
    if nombre == 3:
        continue  # Passe à l'itération suivante si nombre vaut 3
    print(nombre)
```

---

## Les Expressions Conditionnelles (Opérateur Ternaire)

Python permet d’écrire des conditions simples en une seule ligne grâce à l'opérateur ternaire.

**Syntaxe** :

```python
variable = valeur_si_vrai if condition else valeur_si_faux
```

**Exemple** :

```python
age = 20
statut = "majeur" if age >= 18 else "mineur"
print(statut)  # Affiche "majeur"
```

---

## Exercices Pratiques

### Exercice 1

Écrivez un programme qui demande un nombre à l’utilisateur et affiche s’il est pair ou impair. Utilisez une instruction `if` pour vérifier la condition.

### Exercice 2

Créez une boucle `for` qui affiche les nombres de 1 à 10. Ajoutez une condition pour interrompre la boucle si le nombre est supérieur à 7.

### Exercice 3

Écrivez un programme qui utilise une boucle `while` pour afficher les nombres de 1 à 5. Utilisez `continue` pour ne pas afficher le nombre 3.

---

## Résumé des Commandes de Base

| Structure               | Description                                    |
|-------------------------|------------------------------------------------|
| `if`, `elif`, `else`    | Instructions conditionnelles                   |
| `while`                 | Boucle avec condition                          |
| `for`                   | Boucle pour itérer sur une collection          |
| `break`                 | Interrompt immédiatement la boucle             |
| `continue`              | Passe à l'itération suivante                   |
| Opérateur ternaire      | Écriture condensée de conditions simples       |

Ce chapitre vous introduit aux structures de contrôle de flux, vous permettant de gérer les conditions et répétitions. Dans le prochain chapitre, nous explorerons les **fonctions** pour organiser votre code et créer des modules réutilisables.