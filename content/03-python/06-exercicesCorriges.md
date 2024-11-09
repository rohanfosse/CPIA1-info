---
section: Python
nav_order: 7
title: Exercices Corrigés
topics: Exercices; Solutions; Variables; Conditions; Boucles; Fonctions; Collections de données
---

Ce chapitre propose des exercices pratiques couvrant les notions de base, des variables et types de données aux structures de contrôle, conditions, fonctions et collections de données. Chaque solution inclut des étapes détaillées et des fonctions qui retournent des valeurs.

---

## Exercice 1 : Bonjour, le Monde !

Écrivez une fonction `saluer` qui retourne la chaîne "Bonjour, le monde !".

**Solution :**

```python
def saluer():
    # Étape 1 : Retourner un message de bienvenue
    return "Bonjour, le monde!"

# Appel de la fonction et affichage du résultat
message = saluer()
print(message)  # Affiche "Bonjour, le monde!"
```

---

## Exercice 2 : Calcul de l'aire d'un rectangle

Créez une fonction `aire_rectangle` qui prend deux paramètres `longueur` et `largeur` et retourne l'aire du rectangle (longueur * largeur).

**Solution :**

```python
def aire_rectangle(longueur, largeur):
    # Étape 1 : Calculer l'aire en multipliant longueur par largeur
    aire = longueur * largeur
    # Étape 2 : Retourner le résultat
    return aire

# Appel de la fonction avec des exemples
resultat = aire_rectangle(5, 3)
print(resultat)  # Affiche 15
```

---

## Exercice 3 : Pair ou Impair

Écrivez une fonction `est_pair` qui prend un nombre en paramètre et retourne `True` si le nombre est pair, sinon `False`.

**Solution :**

```python
def est_pair(nombre):
    # Étape 1 : Vérifier si le nombre est divisible par 2
    if nombre % 2 == 0:
        # Étape 2 : Retourner True si la condition est vraie
        return True
    else:
        # Étape 3 : Retourner False si la condition est fausse
        return False

# Test de la fonction avec quelques nombres
print(est_pair(4))  # Affiche True
print(est_pair(7))  # Affiche False
```

---

## Exercice 4 : Compter les voyelles

Créez une fonction `compter_voyelles` qui prend une chaîne de caractères en paramètre et retourne le nombre de voyelles (`a`, `e`, `i`, `o`, `u`) dans cette chaîne.

**Solution :**

```python
def compter_voyelles(texte):
    # Étape 1 : Définir les voyelles et initialiser un compteur
    voyelles = "aeiou"
    compteur = 0
    
    # Étape 2 : Parcourir chaque lettre dans le texte
    for lettre in texte.lower():
        # Étape 3 : Vérifier si la lettre est une voyelle
        if lettre in voyelles:
            # Étape 4 : Incrémenter le compteur si c'est une voyelle
            compteur += 1
    
    # Étape 5 : Retourner le nombre de voyelles
    return compteur

# Appel de la fonction et affichage du résultat
print(compter_voyelles("Bonjour"))  # Affiche 3
```

---

## Exercice 5 : Liste des carrés

Écrivez une fonction `liste_carrés` qui prend un nombre `n` et retourne une liste contenant les carrés de 1 à `n` (inclus).

**Solution :**

```python
def liste_carrés(n):
    # Étape 1 : Créer une liste vide pour stocker les carrés
    carres = []
    
    # Étape 2 : Parcourir les nombres de 1 à n
    for i in range(1, n + 1):
        # Étape 3 : Calculer le carré du nombre et l'ajouter à la liste
        carres.append(i ** 2)
    
    # Étape 4 : Retourner la liste des carrés
    return carres

# Appel de la fonction et affichage du résultat
print(liste_carrés(5))  # Affiche [1, 4, 9, 16, 25]
```

---

## Exercice 6 : Dictionnaire des carrés

Créez une fonction `dictionnaire_carrés` qui prend un nombre `n` et retourne un dictionnaire où les clés sont les nombres de 1 à `n` et les valeurs sont leurs carrés.

**Solution :**

```python
def dictionnaire_carrés(n):
    # Étape 1 : Créer un dictionnaire vide
    carres = {}
    
    # Étape 2 : Parcourir les nombres de 1 à n
    for i in range(1, n + 1):
        # Étape 3 : Ajouter le nombre et son carré au dictionnaire
        carres[i] = i ** 2
    
    # Étape 4 : Retourner le dictionnaire des carrés
    return carres

# Appel de la fonction et affichage du résultat
print(dictionnaire_carrés(5))  # Affiche {1: 1, 2: 4, 3: 9, 4: 16, 5: 25}
```

---

## Exercice 7 : Filtrer les nombres pairs

Écrivez une fonction `filtrer_pairs` qui prend une liste de nombres et retourne une nouvelle liste contenant uniquement les nombres pairs.

**Solution :**

```python
def filtrer_pairs(liste):
    # Étape 1 : Créer une liste vide pour stocker les nombres pairs
    pairs = []
    
    # Étape 2 : Parcourir chaque nombre dans la liste
    for nombre in liste:
        # Étape 3 : Vérifier si le nombre est pair
        if nombre % 2 == 0:
            # Étape 4 : Ajouter le nombre pair à la liste
            pairs.append(nombre)
    
    # Étape 5 : Retourner la liste des nombres pairs
    return pairs

# Appel de la fonction et affichage du résultat
print(filtrer_pairs([1, 2, 3, 4, 5, 6]))  # Affiche [2, 4, 6]
```

---

## Exercice 8 : Intersection de listes

Écrivez une fonction `intersection` qui prend deux listes et retourne une liste contenant les éléments communs aux deux listes, sans doublons.

**Solution :**

```python
def intersection(liste1, liste2):
    # Étape 1 : Convertir les listes en ensembles
    ensemble1 = set(liste1)
    ensemble2 = set(liste2)
    
    # Étape 2 : Trouver l'intersection des deux ensembles
    communs = ensemble1 & ensemble2
    
    # Étape 3 : Convertir l'intersection en liste
    resultats = list(communs)
    
    # Étape 4 : Retourner les éléments communs
    return resultats

# Appel de la fonction et affichage du résultat
print(intersection([1, 2, 3, 4], [3, 4, 5, 6]))  # Affiche [3, 4]
```

---

## Exercice 9 : Nombre de mots dans une phrase

Écrivez une fonction `compter_mots` qui prend une chaîne de caractères et retourne le nombre de mots dans la chaîne.

**Solution :**

```python
def compter_mots(phrase):
    # Étape 1 : Diviser la phrase en mots
    mots = phrase.split()
    
    # Étape 2 : Compter le nombre de mots
    nombre_mots = len(mots)
    
    # Étape 3 : Retourner le nombre de mots
    return nombre_mots

# Appel de la fonction et affichage du résultat
print(compter_mots("Bonjour tout le monde"))  # Affiche 3
```

---

## Exercice 10 : Fusionner des dictionnaires

Écrivez une fonction `fusionner_dictionnaires` qui prend deux dictionnaires et retourne un nouveau dictionnaire contenant les paires clé-valeur des deux dictionnaires. En cas de clé en double, la valeur du deuxième dictionnaire est utilisée.

**Solution :**

```python
def fusionner_dictionnaires(dico1, dico2):
    # Étape 1 : Créer une copie du premier dictionnaire
    dico_fusion = dico1.copy()
    
    # Étape 2 : Ajouter ou mettre à jour les valeurs du deuxième dictionnaire
    dico_fusion.update(dico2)
    
    # Étape 3 : Retourner le dictionnaire fusionné
    return dico_fusion

# Appel de la fonction et affichage du résultat
dico1 = {"a": 1, "b": 2}
dico2 = {"b": 3, "c": 4}
print(fusionner_dictionnaires(dico1, dico2))  # Affiche {'a': 1, 'b': 3, 'c': 4}
```
