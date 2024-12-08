---
section: Flowgorithm
nav_order: 2
title: Cheat Sheet Flowgorithm
topics: Flowgorithm; Algorithmique; Commandes
---

### **Éléments de base**

#### **Formes du diagramme**
1. **Ovale (Start/End)** : Représente le début ou la fin d'un programme.
2. **Parallélogramme (Input/Output)** : Permet d'afficher ou de saisir des données.
3. **Rectangle (Process)** : Représente une opération ou un calcul.
4. **Losange (Decision)** : Représente une condition ou un test logique.
5. **Flèche** : Indique le flux de contrôle.

---

### **Syntaxe des instructions**

#### **Déclaration de variables**
- Syntaxe : `NomDeVariable : Type`
- Types possibles :
  - `Integer` : Entiers.
  - `Real` : Nombres à virgule.
  - `String` : Chaînes de caractères.
  - `Boolean` : Valeurs logiques (`True` ou `False`).

#### **Saisie utilisateur**
- Exemple : `Input nombre`
- Permet de demander une valeur que l’utilisateur entre.

#### **Affichage de données**
- Exemple : `Output "Bonjour, le résultat est : "`
- Combine du texte et des valeurs à afficher.

#### **Affectation de variables**
- Exemple : `somme = a + b`
- Permet de calculer et de stocker un résultat.

---

### **Opérations courantes**

#### **Opérations arithmétiques**
| Opération    | Symbole |
|--------------|---------|
| Addition     | `+`     |
| Soustraction | `-`     |
| Multiplication | `*`   |
| Division     | `/`     |
| Modulo       | `%`     |

#### **Opérations logiques**
| Opération     | Symbole |
|---------------|---------|
| ET logique    | `AND`   |
| OU logique    | `OR`    |
| NON logique   | `NOT`   |

#### **Opérations de comparaison**
| Opération           | Symbole |
|---------------------|---------|
| Égalité            | `=`     |
| Différent           | `≠`     |
| Plus grand que      | `>`     |
| Plus petit que      | `<`     |
| Plus grand ou égal  | `≥`     |
| Plus petit ou égal  | `≤`     |

---

### **Structures de contrôle**

#### **Condition (Decision)**
- Permet de tester une condition et d’exécuter des blocs différents selon le résultat.
- Exemple :
  ```plaintext
  If a > b Then
      Output "A est plus grand"
  Else
      Output "B est plus grand"
  End If
  ```

#### **Boucles**
1. **Pour (For Loop)** :
   - Exemple :
     ```plaintext
     For i = 1 To 10
         Output i
     End For
     ```

2. **Tant que (While Loop)** :
   - Exemple :
     ```plaintext
     While compteur < 10
         compteur = compteur + 1
     End While
     ```

3. **Faire...Tant que (Do While Loop)** :
   - Exemple :
     ```plaintext
     Do
         compteur = compteur + 1
     While compteur < 10
     ```

---

### **Fonctions et Procédures**

#### **Définir une fonction**
- Une fonction retourne une valeur.
- Exemple :
  ```plaintext
  Function CalculerSomme(a : Integer, b : Integer) : Integer
      Return a + b
  End Function
  ```

#### **Définir une procédure**
- Une procédure ne retourne pas de valeur.
- Exemple :
  ```plaintext
  Procedure AfficherMessage(message : String)
      Output message
  End Procedure
  ```

#### **Appel de fonction/procédure**
- Fonction : `resultat = CalculerSomme(3, 5)`
- Procédure : `AfficherMessage("Bonjour")`

---

### **Bonnes pratiques**
1. **Nommez vos variables clairement** : Utilisez des noms explicites (`age`, `somme`, `nomClient`).
2. **Commenter le diagramme** : Ajoutez des commentaires pour expliquer les étapes clés.
3. **Testez avec différentes entrées** : Simulez plusieurs cas pour valider votre algorithme.

---

### **Exemple complet : Jeu du Plus ou Moins**

```plaintext
Start
secret = Random(1, 100)
tentative = 0
Do
    Input "Entrez un nombre entre 1 et 100 :", saisie
    tentative = tentative + 1
    If saisie < secret Then
        Output "Trop petit !"
    Else If saisie > secret Then
        Output "Trop grand !"
    End If
While saisie ≠ secret
Output "Bravo, vous avez trouvé en ", tentative, " tentatives !"
End
```

--- 

### **Liens utiles**
- **[Site officiel Flowgorithm](http://www.flowgorithm.org/)**
- **[Guide d'utilisation](http://www.flowgorithm.org/documentation.html)**

--- 

Avec ce cheatsheet, vous avez un guide rapide pour maîtriser Flowgorithm et créer vos propres algorithmes. Bonne programmation ! 🎉