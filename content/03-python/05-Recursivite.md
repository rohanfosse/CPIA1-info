---
section: Python
nav_order: 6
title: Récursivité
topics: Récursivité; Appels de fonction; Cas de base; Cas récursif
---

La récursivité est une technique de programmation où une fonction s'appelle elle-même pour résoudre un problème. Elle est particulièrement utile pour les problèmes répétitifs ou divisibles en sous-problèmes similaires.

## Qu'est-ce que la Récursivité ?

Une fonction récursive est une fonction qui s'appelle elle-même. Elle doit comporter deux éléments fondamentaux :

1. **Cas de base** : Une condition qui termine la récursion.
2. **Cas récursif** : L'appel de la fonction à elle-même avec un problème simplifié.

### Cas de Base

Le cas de base est la condition qui arrête la récursion. Sans lui, la fonction s'appellerait indéfiniment, provoquant une erreur de débordement de pile (`StackOverflowError`). Il est essentiel de définir un cas de base pour chaque fonction récursive.

### Cas Récursif

Le cas récursif est l'appel de la fonction à elle-même avec un problème plus petit ou plus simple. Chaque appel récursif doit progressivement se rapprocher du cas de base pour éviter une récursion infinie.

### Exemple : Calcul de Factorielle

Le calcul de la factorielle d’un nombre \( n \) (noté \( n! \)) est un exemple classique de récursivité.

```python
def factorielle(n):
    if n == 0:  # Cas de base
        return 1
    else:       # Cas récursif
        return n * factorielle(n - 1)

print(factorielle(5))  # Affiche 120
```

#### Exemple Détaillé : Factorielle de 5

Pour calculer `factorielle(5)`, la fonction suit cette séquence :

1. **Appel initial** :
   - `factorielle(5)` retourne `5 * factorielle(4)`.

2. **Développer `factorielle(4)`** :
    - `factorielle(4)` retourne `4 * factorielle(3)`.

3. **Développer `factorielle(3)`** :
    - `factorielle(3)` retourne `3 * factorielle(2)`.

4. **Développer `factorielle(2)`** :
    - `factorielle(2)` retourne `2 * factorielle(1)`.

5. **Développer `factorielle(1)`** :
    - `factorielle(1)` retourne `1 * factorielle(0)`.

6. **Atteindre le cas de base** :
    - `factorielle(0)` retourne `1`.

7. **Résolution en remontant** :
    - `factorielle(1)` retourne `1 * 1 = 1`.
    - `factorielle(2)` retourne `2 * 1 = 2`.
    - `factorielle(3)` retourne `3 * 2 = 6`.
    - `factorielle(4)` retourne `4 * 6 = 24`.
    - `factorielle(5)` retourne `5 * 24 = 120`.

Le tableau ci-dessous montre les appels imbriqués et leurs retours :

| Appel            | Résultat     |
|------------------|--------------|
| `factorielle(5)` | `5 * 24 = 120` |
| `factorielle(4)` | `4 * 6 = 24`   |
| `factorielle(3)` | `3 * 2 = 6`    |
| `factorielle(2)` | `2 * 1 = 2`    |
| `factorielle(1)` | `1 * 1 = 1`    |
| `factorielle(0)` | `1`            |

Ainsi, `factorielle(5)` retourne `120`.

---

## Calculer la Suite de Fibonacci

La suite de Fibonacci est définie ainsi :
- \( F(0) = 0 \)
- \( F(1) = 1 \)
- Pour \( n \geq 2 \), \( F(n) = F(n-1) + F(n-2) \).

Voici une fonction récursive pour calculer un terme de Fibonacci :

```python
def fibonacci(n):
    if n <= 1:  # Cas de base
        return n
    else:       # Cas récursif
        return fibonacci(n - 1) + fibonacci(n - 2)
```

---

### Exemple Détaillé : Fibonacci de 4

Pour calculer `fibonacci(4)`, la fonction suit cette séquence :

1. **Appel initial** :
   - `fibonacci(4)` retourne `fibonacci(3) + fibonacci(2)`.

2. **Développer `fibonacci(3)`** :
   - `fibonacci(3)` retourne `fibonacci(2) + fibonacci(1)`.

3. **Développer `fibonacci(2)`** :
   - `fibonacci(2)` retourne `fibonacci(1) + fibonacci(0)`.

4. **Atteindre les cas de base** :
   - `fibonacci(1)` retourne `1` (cas de base).
   - `fibonacci(0)` retourne `0` (cas de base).

5. **Résolution en remontant** :
   - `fibonacci(2)` retourne `1 + 0 = 1`.
   - `fibonacci(3)` retourne `1 + 1 = 2`.
   - `fibonacci(4)` retourne `2 + 1 = 3`.

Le tableau ci-dessous montre les appels imbriqués et leurs retours :

| Appel         | Résultat     |
|---------------|--------------|
| `fibonacci(4)` | `2 + 1 = 3` |
| `fibonacci(3)` | `1 + 1 = 2` |
| `fibonacci(2)` | `1 + 0 = 1` |
| `fibonacci(1)` | `1`          |
| `fibonacci(0)` | `0`          |

Ainsi, `fibonacci(4)` retourne `3`.

---

## Limites de la Récursivité

1. **Appels infinis** : Si le cas de base est mal défini ou absent, la récursion ne s'arrête jamais et provoque une erreur (`RecursionError`).
2. **Performance** : Les appels multiples imbriqués, comme dans Fibonacci, peuvent être coûteux en termes de temps et de mémoire.

---

## Exercices Pratiques

### Exercice 1 : Somme des Nombres

Créez une fonction récursive `somme(n)` qui retourne la somme des \( n \) premiers nombres.

---

### Exercice 2 : Compteur

Créez une fonction récursive `compter(n)` qui affiche tous les nombres de \( n \) à 0.

**Exemple** :

```python
compter(5)
# Affiche :
# 5
# 4
# 3
# 2
# 1
# 0
```

---

### Exercice 3 : Puissance

Implémentez une fonction récursive `puissance(x, n)` pour calculer \( x^n \) sans utiliser l’opérateur `**`.

**Exemple** :

```python
print(puissance(2, 3))  # Affiche 8
```

---