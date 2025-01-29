---
title: "Examen Blanc EI Python"
layout: lesson-content
permalink: /ExamBlanc-EI.html
---

### **Examen de Programmation en Python**

**Durée :** 1h  
**Barème total :** 20 points  
**Documents autorisés :** Aucune aide extérieure sauf un mémento Python fourni en annexe.  
**Instructions :** Vous devez **écrire** votre code **sur papier** en respectant la syntaxe de Python. Aucune exécution sur ordinateur ne sera réalisée, mais le code doit être **valide et lisible**.

---

## **Contexte : Analyse des Notes des Élèves**

Un professeur souhaite analyser les performances de ses élèves sur plusieurs devoirs afin d’identifier les matières où ils ont le plus de difficultés. Vous devez écrire un programme permettant de **calculer certaines statistiques** et de préparer des instructions pour afficher les résultats sous forme de tableau et de graphique.

Le tableau ci-dessous représente les **notes (sur 20)** obtenues par **5 élèves** sur **3 matières différentes**.

| Élève   | Mécanique | Electronique | Informatique |
| ------- | ------------- | -------- | ------------ |
| Élève 1 | 15            | 12       | 18           |
| Élève 2 | 10            | 14       | 16           |
| Élève 3 | 8             | 9        | 14           |
| Élève 4 | 17            | 18       | 19           |
| Élève 5 | 13            | 11       | 15           |

---

### **Partie 1 – Traitement des données (12 points)**

1. **(2 points)**

   - À partir du tableau ci-dessus, **écrivez une liste de listes Python** qui représente les notes de chaque élève.
   - Assurez-vous que la structure respecte l’organisation du tableau.

2. **(5 points)**

   - Écrivez une fonction `calculer_moyenne_eleve(notes, eleve_index)` qui prend en paramètres :
     - `notes` : la liste de listes contenant toutes les notes
     - `eleve_index` : l’index de l’élève dans la liste
   - Cette fonction doit retourner la **moyenne des notes** de l’élève donné en paramètre.

3. **(5 points)**
   - Écrivez une fonction `calculer_moyenne_matiere(notes, matiere_index)` qui prend en paramètres :
     - `notes` : la liste de listes contenant toutes les notes
     - `matiere_index` : l’index de la matière dans la liste
   - Cette fonction doit retourner la **moyenne des notes** pour la matière donnée en paramètre.

---

### **Partie 2 – Manipulation et transformation des données (8 points)**

4. **(3 points)**

   - Écrivez une fonction `meilleur_eleve(notes)` qui retourne le **numéro de l’élève** ayant obtenu la meilleure moyenne sur l’ensemble des matières.
   - Indiquez clairement le résultat attendu en appliquant cette fonction aux données fournies.

5. **(3 points)**

   - Écrivez une fonction `matiere_plus_difficile(notes)` qui retourne le **nom de la matière** où la moyenne des élèves est la plus basse.
   - Indiquez clairement le résultat attendu en appliquant cette fonction aux données fournies.

6. **(2 points)**
   - **Décrivez, sous forme de texte, comment représenter les notes sur un graphique** :
     - Quels axes choisir ?
     - Comment distinguer les **3 matières** ?
     - Comment organiser la légende du graphique ?

---

### **Bonus (2 points)**

Si votre programme est bien structuré avec des **commentaires clairs** expliquant le rôle de chaque fonction et que la présentation est **soignée**, vous pourrez obtenir **2 points supplémentaires**.
