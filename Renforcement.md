---
title: "Renforcement EI Python"
layout: lesson-content
permalink: /Renforcement.html
---

## **Contexte : Analyse des Ventes d’un Magasin**

Un magasin souhaite analyser les ventes de ses produits sur plusieurs jours afin d’optimiser ses stocks. Vous devez écrire un programme permettant de **calculer certaines statistiques** sur ces ventes et de préparer des instructions pour afficher les résultats sous forme de tableau et de graphique.

Le tableau ci-dessous représente le nombre d’unités vendues pour **5 produits** sur une période de **3 jours**.

| Produit   | Jour 1 | Jour 2 | Jour 3 |
| --------- | ------ | ------ | ------ |
| Produit 1 | 12     | 14     | 10     |
| Produit 2 | 25     | 28     | 22     |
| Produit 3 | 18     | 21     | 20     |
| Produit 4 | 30     | 27     | 25     |
| Produit 5 | 22     | 20     | 18     |

---

### **Partie 1 – Traitement des données (12 points)**

1. **(2 points)**

   - À partir du tableau ci-dessus, **écrivez trois listes Python** qui représentent les ventes pour **chaque jour**.
   - Assurez-vous que chaque liste contienne uniquement les **nombres des ventes** pour les **5 produits** du jour correspondant.

2. **(5 points)**

   - **Écrivez une fonction Python** `calculer_total_ventes(ventes_jour)` qui prend une **liste** représentant les ventes d’un jour et retourne le **total des ventes** de la journée.
   - **Écrivez les appels à cette fonction** pour les trois jours en utilisant les listes créées précédemment.

3. **(5 points)**
   - **Écrivez une fonction Python** `calculer_moyenne_ventes(ventes)` qui prend en paramètre une **liste de listes** contenant les ventes et retourne une **nouvelle liste** contenant la **moyenne des ventes par produit** sur les trois jours.
   - **Écrivez l’appel à cette fonction** et **indiquez ce que doit afficher le programme**.

---

### **Partie 2 – Analyse des ventes et instructions d'affichage (8 points)**

4. **(3 points)**

   - **Écrivez une fonction Python** `produit_plus_vendu(ventes)` qui retourne **le numéro du produit** ayant eu le plus de ventes en moyenne sur les 3 jours.
   - **Indiquez clairement le résultat attendu** en appliquant cette fonction aux données fournies.

5. **(3 points)**

   - **Écrivez une fonction Python** `jour_plus_vendu(ventes)` qui retourne le **jour où le total des ventes a été le plus élevé**.
   - **Expliquez comment votre fonction doit être utilisée** et indiquez le résultat attendu pour les données fournies.

6. **(2 points)**
   - **Décrivez, sous forme de texte, comment représenter les ventes sur un graphique** :
     - Quels axes choisir ?
     - Comment distinguer les **3 jours** ?
     - Comment organiser la légende du graphique ?

---

### **Bonus (2 points)**

Si votre programme est bien structuré avec des **commentaires clairs** expliquant le rôle de chaque fonction et que la présentation est **soignée**, vous pourrez obtenir **2 points supplémentaires**.
