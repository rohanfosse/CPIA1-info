# Etude de Cas : Excel - Avril 2025

**Classe : CPIA1 - CESI Montpellier**  
**Année : 2024-2025**

**Durée : 30 mins**  
**Documents autorisés :** Aucun document autorisé, hormis le fichier Excel fourni.

## Modalités de l'Examen

- Complétez le fichier Excel reçu par mail (**Examen_CPIA1.xlsx**) selon les consignes ci-dessous.
- Renommez votre fichier Excel sous la forme : **NOM-PRENOM-CPIA1.xlsx**.
- Envoyer le fichier par mail à l'adresse suivante : **rfosse@cesi.fr** avant la fin de la séance.

---

## Contexte

Une entreprise de logistique souhaite optimiser la gestion de ses stocks pour améliorer son efficacité opérationnelle et éviter les ruptures ou les surplus.

L'objectif est d'analyser la performance de gestion des stocks de divers produits en tenant compte des délais de livraison, des ventes et des niveaux actuels de stock pour recommander des actions d'amélioration.

Le fichier Excel fourni contient les données dans l'onglet **"Stocks"** avec les colonnes suivantes :

- Produit
- Stock Actuel
- Ventes Hebdomadaires
- Délai de Livraison (jours)
- Stock Minimum Requis
- Fournisseur

## Objectifs et Travaux Demandés

### Structuration des Données (4 points)

Dans l'onglet **"Stocks"**, appliquez les modifications suivantes :

- Mettez en place un filtre automatique sur l'ensemble du tableau de données.
- Ajoutez une coloration conditionnelle sur la colonne "Stock Actuel" permettant de faire apparaître en rouge les produits dont le stock actuel est inférieur au "Stock Minimum Requis" et en vert ceux qui sont au-dessus ou égaux.

### Calculs de Base et Conditions Simples (6 points)

Dans l'onglet **"Stocks"**, ajoutez les nouvelles colonnes suivantes :

- **Coût de Stockage (€)** : Calculé en multipliant le stock actuel par 0.25 € (coût moyen de stockage).

- **Stock Théorique Nécessaire** : Calculé selon la formule suivante :

  $$
  \text{Stock Théorique} = \text{Ventes Hebdomadaires} \times \frac{\text{Délai de Livraison}}{7}
  $$

  **Exemple** : Si les ventes hebdomadaires sont **200 unités** et le délai de livraison **14 jours**, alors :

  $$ 200 \times \frac{14}{7} = 400 \text{ unités} $$

### Analyse des Données et Statistiques (6 points)

Dans l'onglet **"Stocks"**, ajoutez les colonnes suivantes :

- **Alerte Stock** :
  - **2** si le stock actuel est inférieur au stock minimum requis ET le délai de livraison supérieur à 10 jours.
  - **1** si uniquement le stock actuel est inférieur au stock minimum requis.
  - **0** sinon.

Effectuez les calculs suivants sous le tableau :

- Le nombre total de produits par niveau d'alerte (nombre de produits en alerte "1" et en alerte critique "2").
- Le coût total actuel de stockage.
- Identifiez clairement le fournisseur associé au plus grand nombre de produits en alerte critique (niveau 2).

### Création et Analyse Graphique (4 points)

Réalisez dans un nouvel onglet nommé **"Graphiques"** :

- Un **graphique en barres** comparant les stocks actuels et les stocks théoriques nécessaires par produit.
- Un **graphique circulaire** illustrant la répartition des coûts de stockage par produit.
