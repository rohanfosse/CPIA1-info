---
section: Python
nav_order: 8
title: Bibliothèques    
topics: Bibliothèques; Modules; Importation; Fonctions; Exemples
---

Les bibliothèques Python sont des modules qui contiennent des fonctions et classes prédéfinies pour des tâches spécifiques. Elles permettent d'étendre les fonctionnalités de base de Python en ajoutant des outils pour des opérations avancées. Python propose une large gamme de bibliothèques pour divers domaines, tels que les mathématiques, les statistiques, le traitement de données, la visualisation, l'apprentissage automatique, etc.

## Importation de Bibliothèques

Pour utiliser une bibliothèque dans un script Python, vous devez l'importer en utilisant l'instruction `import`. Voici quelques exemples d'importation de bibliothèques courantes :

```python
import math  # Importe la bibliothèque math
import random  # Importe la bibliothèque random
import numpy as np  # Importe la bibliothèque numpy avec un alias np
import pandas as pd  # Importe la bibliothèque pandas avec un alias pd
```

le mot-clé `import` est suivi du nom de la bibliothèque à importer. Vous pouvez également utiliser un alias pour raccourcir le nom de la bibliothèque lors de son utilisation. Par exemple, `import numpy as np` permet d'utiliser `np` au lieu de `numpy` pour accéder aux fonctions de la bibliothèque.

par exemple, pour importer la bibliothèque `math` et utiliser la fonction `sqrt` pour calculer la racine carrée d'un nombre :

```python
import math

x = 16
racine = math.sqrt(x)

print(racine)  # Affiche 4.0
```

### Utilisation de from ... import

Vous pouvez également importer des fonctions spécifiques d'une bibliothèque en utilisant l'instruction `from ... import`. Cela vous permet d'accéder directement à ces fonctions sans utiliser le nom de la bibliothèque. Cela permet aussi de ne pas importer toutes les fonctions de la bibliothèque, ce qui peut économiser de la mémoire.

**Exemple** :

```python
from math import sqrt

x = 16
racine = sqrt(x)

print(racine)  # Affiche 4.0
```

## Bibliothèques Courantes

Voici quelques-unes des bibliothèques Python les plus couramment utilisées :

- **math** : Fonctions mathématiques (racine carrée, trigonométrie, logarithmes, etc.)
- **random** : Génération de nombres aléatoires
- **numpy** : Calcul numérique et manipulation de tableaux multidimensionnels
- **pandas** : Analyse de données et manipulation de données en tableaux
- **matplotlib** : Visualisation de données sous forme de graphiques et de diagrammes
- **scikit-learn** : Bibliothèque d'apprentissage automatique pour la classification, la régression, le clustering, etc.
- **tensorflow** : Bibliothèque d'apprentissage automatique développée par Google

Ces bibliothèques offrent des fonctionnalités avancées pour des tâches spécifiques et sont largement utilisées dans le développement de logiciels, la science des données, l'apprentissage automatique et d'autres domaines connexes.

### Connaître les Fonctions Disponibles

Pour connaître les fonctions disponibles dans une bibliothèque, vous pouvez utiliser la fonction `dir()` pour lister les noms des fonctions et des classes définies dans la bibliothèque. Par exemple, pour afficher les fonctions disponibles dans la bibliothèque `math` :

```python
import math

print(dir(math))
```

Cela affichera une liste des fonctions et des classes disponibles dans la bibliothèque `math`.

Vous pouvez également consulter la documentation officielle de chaque bibliothèque pour obtenir des informations détaillées sur les fonctions, les classes et les méthodes disponibles, ainsi que des exemples d'utilisation.

## Exemples d'Utilisation

Voici quelques exemples d'utilisation de bibliothèques courantes en Python :

- Utilisation de la bibliothèque `math` pour calculer la factorielle d'un nombre :

```python
import math

n = 5
factorielle = math.factorial(n)

print(factorielle)  # Affiche 120
```

- Utilisation de la bibliothèque `random` pour générer un nombre aléatoire entre 1 et 100 :

```python
import random

nombre = random.randint(1, 100)

print(nombre)  # Affiche un nombre aléatoire entre 1 et 100
```

- Utilisation de la bibliothèque `numpy` pour créer un tableau de valeurs et calculer leur somme :

```python
import numpy as np

valeurs = np.array([1, 2, 3, 4, 5]) # Crée un tableau numpy contenant les valeurs 1 à 5

somme = np.sum(valeurs)

print(somme)  # Affiche 15
```

## Exercices

### Exercice 1

Écrivez un programme Python qui utilise la bibliothèque `math` pour calculer la racine cubique d'un nombre donné.

### Exercice 2

Écrivez un programme Python qui utilise la bibliothèque `random` pour générer un nombre aléatoire entre 50 et 100.

### Exercice 3

Écrivez un programme Python qui utilise la bibliothèque `numpy` pour créer un tableau de 10 valeurs aléatoires entre 1 et 100 et affiche la moyenne de ces valeurs.

---