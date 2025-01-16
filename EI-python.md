# Cours : Réussir une épreuve de Python sur papier

---

## Objectifs du cours

- Comprendre les différences entre coder sur ordinateur et répondre à une épreuve de Python sur papier.
- Apprendre à structurer ses réponses et à vérifier son code sans exécution.
- Acquérir des astuces pratiques pour réussir.

---

## Partie 1 : Les particularités de coder sur papier

1. **Pas de test immédiat**

   - Sur ordinateur, l’interprète Python signale immédiatement les erreurs.
   - Sur papier, vous devez anticiper ces erreurs par une lecture attentive.

2. **Lire et écrire proprement**

   - Une écriture claire aide à vérifier le code et à éviter les erreurs.
   - Indentez correctement le code pour représenter les blocs logiques.

3. **Simuler l’exécution mentalement**
   - Suivez pas à pas l’exécution du code comme le ferait l’interprète Python.

---

## Partie 2 : Strucuture des réponses

1. **Respecter la syntaxe Python**

   - Utilisez des noms de variables explicites.
   - N’oubliez pas les deux-points (`:`) après les structures conditionnelles ou les boucles.
   - Indentez systématiquement après les deux-points.

   Exemple :

   ```python
   def addition(a, b):
       return a + b
   ```

2. **Commenter si demandé**

   - Ajoutez des commentaires pour expliquer vos choix ou clarifier des points complexes.
   - Exemple :

    ```python
    # Initialisation d'une liste vide
    ma_liste = []
    ```

3. **Diviser les problèmes**
   - Si l’exercice demande une solution complexe, commencez par décomposer le problème.
   - Notez les étapes clés sous forme de pseudo-code avant de coder en Python.

---

### Partie 3 : Décortiquer un énoncé d’exercice

1. **Lire attentivement l’énoncé**

   - Identifiez les mots-clés : « calculer », « afficher », « retourner ».
   - Recherchez les contraintes, par exemple : « utiliser une boucle » ou « limiter les opérations à des entiers positifs ».
   - Notez les exemples fournis pour comprendre les attentes.

    Prenons un exemple : « Ecrire une fonction qui calcule la somme des entiers de 1 à `n` ». Voici comment le décortiquer :

    - **Mots-clés :** « fonction », « calcule », « somme », « entiers », « 1 à `n` ».
    - **Contraintes :** Utiliser une fonction, calculer une somme, limiter les entiers à 1 à `n`.
    - **Exemple :** Pour `n = 5`, la somme doit être `1 + 2 + 3 + 4 + 5 = 15`.

2. **Repérer les entrées et sorties attendues**

   - Notez ce que le programme doit recevoir en entrée (par exemple, des paramètres ou des valeurs utilisateur).
   - Déterminez clairement ce qui doit être produit en sortie.

   Exemple :

    - **Entrée :** Un entier `n`.
    - **Sortie :** La somme des entiers de 1 à `n`.

3. **Décomposer en étapes claires**

   - Créez un pseudo-code pour énoncer les étapes clés. Par exemple :

    ```
    Pour chaque entier de 1 à n :
         Ajouter l’entier à la somme.
    Retourner la somme.
    ```

4. **Identifier les cas particuliers**

   - Prévoyez des tests pour les entrées atypiques, comme des valeurs nulles ou extrêmes.
   - Exemple : Que se passe-t-il si `n` est négatif ou nul ?

5. **Lister les outils Python pertinents**

   - Identifiez les structures ou fonctions qui peuvent simplifier le travail :
     - Boucles : `for`, `while`.
     - Conditions : `if`, `elif`, `else`.
     - Fonctions utiles : `len()`, `range()`, etc.

6. **Planifier l’organisation du code (optionnel)**
   - Si l’exercice est complexe, structurez le code en fonctions.
   - Exemple : Une fonction pour valider les entrées, une autre pour effectuer les calculs, une troisième pour afficher les résultats.

---

### Exemples de décorticage d’énoncé

#### Exemple 1 : Trouver les multiples d’un nombre

**Énoncé :** Ecrire un programme qui affiche tous les multiples de 3 entre 0 et un nombre entier donné `n`.

**Étapes :**

1. Identifier les entrées et sorties :
   - Entrée : un entier `n`
   - Sortie : une liste de multiples de 3.
2. Décomposer le problème :
   - Parcourir les nombres de 0 à `n`.
   - Tester si chaque nombre est un multiple de 3.
   - Si oui, l’ajouter à une liste.
3. Pseudo-code :
   ```
   Initialiser une liste vide.
   Pour chaque nombre de 0 à n :
       Si le nombre est divisible par 3 :
           L’ajouter à la liste.
   Afficher la liste.
   ```
4. Implémentation Python :
   ```python
   def multiples_de_trois(n):
       resultats = []
       for i in range(n + 1):
           if i % 3 == 0:
               resultats.append(i)
       print(resultats)
   ```

#### Exemple 2 : Calculer la factorielle

**Énoncé :** Ecrire une fonction qui calcule la factorielle d’un entier positif `n`.

**Étapes :**

1. Identifier les entrées et sorties :
   - Entrée : un entier `n`
   - Sortie : un entier représentant `n!`.
2. Décomposer le problème :
   - Initialiser un résultat à 1.
   - Multiplier successivement par chaque nombre de 1 à `n`.
3. Pseudo-code :
   ```
   Initialiser resultat à 1.
   Pour chaque nombre de 1 à n :
       Multiplier resultat par le nombre.
   Retourner resultat.
   ```
4. Implémentation Python :
   ```python
   def factorielle(n):
       resultat = 1
       for i in range(1, n + 1):
           resultat *= i
       return resultat
   ```

#### Exemple 3 : Identifier les voyelles dans une phrase

**Énoncé :** Ecrire un programme qui compte et affiche les voyelles dans une phrase donnée.

**Étapes :**

1. Identifier les entrées et sorties :
   - Entrée : une chaîne de caractères (phrase).
   - Sortie : le nombre et la liste des voyelles.
2. Décomposer le problème :
   - Initialiser une liste pour stocker les voyelles trouvées.
   - Parcourir chaque caractère de la phrase.
   - Si le caractère est une voyelle, l’ajouter à la liste.
3. Pseudo-code :
   ```
   Initialiser une liste vide pour les voyelles.
   Pour chaque caractère dans la phrase :
       Si le caractère est une voyelle :
           L’ajouter à la liste.
   Afficher la liste et sa longueur.
   ```
4. Implémentation Python :
   ```python
   def compter_voyelles(phrase):
       voyelles = []
       for char in phrase:
           if char.lower() in 'aeiou':
               voyelles.append(char)
       print(f"Voyelles : {voyelles}, Nombre : {len(voyelles)}")
   ```

---

### Partie 4 : Astuces pratiques

1. **Vérifier la syntaxe**

   - Connaître les erreurs courantes :
     - Oublier les deux-points (`:`).
     - Utiliser une indentation incohérente.
     - Confondre `=` et `==`.

2. **Simuler avec des exemples**

   - Prenez un exemple concret et suivez pas à pas l’exécution de votre code.
   - Exemple : Pour la fonction suivante :
     ```python
     def carre(x):
         return x * x
     ```
     Testez-la avec plusieurs valeurs :
     ```
     carre(2) → 4
     carre(-3) → 9
     ```

3. **Identifier les erreurs courantes**

   - Ne pas oublier les parenthèses dans les appels de fonction.
   - Éviter de redéfinir des mots-clés Python (ex. : `list`, `str`).
   - Vérifier les opérations mathématiques et les priorités d’opérateurs.

4. **Prendre soin de la présentation**
   - Encadrez vos réponses.
   - Si un exercice comporte plusieurs parties, numérotez clairement chaque sous-partie.

---

### Partie 5 : Exercices pratiques

1. **Correction d’erreurs syntaxiques**

   1. Repérez les erreurs et corrigez-les :

     ```python
     def calculer(x, y):
         si x > y
             retour x - y
     ```

   - Correction :
     ```python
     def calculer(x, y):
         if x > y:
             return x - y
     ```


   2. Repérez les erreurs et corrigez-les :

      ```python
      def compter_pairs(liste):
      count=0
      for i in liste
      if i%2=0:
      count+=1
      return count
      ```

      **Correction :**

      ```python
      def compter_pairs(liste):
          count = 0
          for i in liste:
              if i % 2 == 0:
                  count += 1
          return count
      ```

   3. Trouvez les erreurs dans ce code et corrigez-les :

      ```python
      def somme_intervalle(a b):
      sum =0
      for i in rangea+b:
      sum=s+i
      return sum
      ```

      **Correction :**

      ```python
      def somme_intervalle(a, b):
          sum = 0
          for i in range(a, b + 1):
              sum += i
          return sum
      ```

---

### Section : Fonctions Mystère

1. **Exercice 1 :** Expliquez ce que fait la fonction suivante et déterminez sa sortie pour `n = 5` :

   ```python
   def mystere_1(n):
       return [i * 2 for i in range(n)]
   ```
    - **Sortie :** `[0, 2, 4, 6, 8]`
    - **Explication :** La fonction crée une liste contenant les valeurs `i * 2` pour chaque `i` allant de 0 à `n - 1`.

2. **Exercice 2 :** Expliquez ce que fait la fonction suivante et déterminez sa sortie pour `s = " 1a2b3c4d5e "`:
   ```python
    def mystere_2(s):
        a = 1
         for c in s:
                if c.isdigit():
                    a += 1
        return a
    ```
    - **Sortie :** `6`
    - **Explication :** La fonction compte le nombre de caractères numériques dans la chaîne `s`. Dans notre cas, la chaîne contient les caractères `1`, `2`, `3`, `4` et `5`, donc la fonction retourne `6`.

3. **Exercice 3 :** Expliquez ce que fait la fonction suivante et déterminez sa sortie pour `a = 2`, `b = 5` et `l = [1, 3, 5]`. Donnez les différentes étapes de l'exécution.

    ```python
    def mystere_3(a,b,l):
        for i in range(a,b):
            if i in l:
                return True
        return False
    ```

    - **Sortie :** `True`
    - **Explication :** La fonction vérifie si un nombre entre `a` et `b - 1` est présent dans la liste `l`. Dans notre cas, avec `a = 2`, `b = 5` et `l = [1, 3, 5]`, le nombre `3` est présent dans la liste, donc la fonction retourne `True`.
    - **Étapes :**
      - `i = 2`, `2` n'est pas dans `l`.
      - `i = 3`, `3` est dans `l`, donc retourne `True`.

4. **Exercice 4 :** Expliquez ce que fait la fonction suivante et déterminez sa sortie pour `n = 5` :

    ```python
    def mystere_4(n):
         return sum([i for i in range(n) if i % 2 == 0])
    ```
    
     - **Sortie :** `6`
     - **Explication :** La fonction calcule la somme des nombres pairs de 0 à `n - 1`.
    
5. **Exercice 5 :** Expliquez ce que fait la fonction suivante et déterminez sa sortie pour `l1 = [1, 2, 3]` et `l2 = [1, 2, 4]` :

    ```python
    def mystere_5(l1, l2):
        s = 0
        for i in l1:
            for j in l2:
                if i == j:
                    s += 1
        return s
    ```

    - **Sortie :** `2`
    - **Explication :** La fonction compte le nombre d'éléments communs entre les listes `l1` et `l2`. Dans notre cas, les éléments `1` et `2` sont communs, donc la fonction retourne `2`.
    - **Étapes :**
      - `i = 1`, `j = 1`, `i == j`, `s = 1`.
      - `i = 1`, `j = 2`, `i != j`.
      - `i = 1`, `j = 4`, `i != j`.
      - `i = 2`, `j = 1`, `i != j`.
      - `i = 2`, `j = 2`, `i == j`, `s = 2`.
      - `i = 2`, `j = 4`, `i != j`.
      - `i = 3`, `j = 1`, `i != j`.
      - `i = 3`, `j = 2`, `i != j`.
      - `i = 3`, `j = 4`, `i != j`.

6. **Exercice 6 :** Expliquez ce que fait la fonction suivante et déterminez sa sortie pour `a = 10`, `b = 5` et `c = 2` :

    ```python
    def mystere_6(a, b, c):
        while a > b:
            a -= c
        return a
    ```

    - **Sortie :** `4`
    - **Explication :** La fonction soustrait `c` de `a` tant que `a` est supérieur à `b`. Dans notre cas, avec `a = 10`, `b = 5` et `c = 2`, les étapes sont les suivantes :
      - `a = 10`, `a > b`, `a = 8`.
      - `a = 8`, `a > b`, `a = 6`.
      - `a = 6`, `a > b`, `a = 4`.
      - `a = 4`, `a <= b`, retourne `4`.