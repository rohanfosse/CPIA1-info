
# Etude de Cas : Excel - Mars 2025
**Classe : CPIA1 - CESI Montpellier**  
**Année : 2024-2025**

**Durée : 30 mins**  
**Documents autorisés :** Aucun document autorisé, hormis le fichier Excel fourni.  

## Modalités de l'Examen

- Complétez le fichier Excel reçu par mail (**Examen_CPIA1.xlsx**) en suivant les consignes ci-dessous.
- Une fois terminé, renommez votre fichier Excel sous la forme : **NOM-PRENOM-CPIA1.xlsx**.
- Déposez votre fichier dans le dépot Moodle "Examen Excel 2" avant la fin de la séance.

---

**Rappel important sur les conditions d'examen :**

- Dès que vous avez téléchargé le fichier Excel, il est **strictement interdit** d'ouvrir ou de consulter toute autre page ou application que celle de l'examen.
- Toute navigation vers une autre page web ou utilisation d'une ressource externe après l'ouverture du fichier Excel sera considérée comme une tentative de fraude.
- Tout manquement à cette règle entraînera automatiquement une note de **0** et pourra faire l'objet d'une procédure disciplinaire.

Merci de respecter ces consignes afin d'assurer l'équité entre tous les étudiants.

## Contexte

Une école d'ingénieurs souhaite analyser la consommation énergétique de ses bâtiments académiques en tenant compte des contraintes liées à la résistance des matériaux (RDM) afin d’optimiser la gestion énergétique et la durabilité des structures.

L'objectif est d'évaluer la consommation énergétique en fonction de plusieurs paramètres physiques des bâtiments (température, activité, matériaux de construction) et de proposer des solutions d’optimisation.

Le fichier Excel fourni contient les données dans l'onglet **"Data"** avec les colonnes suivantes :

- Bâtiment
- Température (°C)
- Consommation énergétique (kWh)
- Activité
- Matériau
- Coefficient de Transmission Thermique (W/m²K)

## Objectifs et Travaux Demandés

### Structuration des Données (3 points)

- Créez un onglet nommé **"Paramètres"**.
- Dans cet onglet, créez un tableau contenant exactement les paramètres suivants (sans unité dans les cellules des valeurs) :

| Paramètre (Unité)                              | Valeur |
| ---------------------------------------------- | ------ |
| Seuil de consommation critique (kWh)           | 500    |
| Coût moyen de l'électricité (€/kWh)            | 0.15   |
| Température de référence (°C)                  | 18     |
| Seuil de performance thermique optimal (W/m²K) | 1.8    |

### Calculs de Base et Conditions Simples (5 points)

Dans l'onglet **"Data"**, après la colonne "Coefficient de Transmission Thermique (W/m²K)", ajoutez les nouvelles colonnes suivantes et utilisez les valeurs des paramètres de l’onglet **"Paramètres"** :

- **Coût de Consommation (€)** : Calculée en multipliant la consommation énergétique par le coût moyen de l'électricité.

- **Consommation Théorique (kWh)** : Calculée à l'aide de la formule suivante :

  $$
  \text{Consommation Théorique} = \text{Coefficient de Transmission Thermique} $$
  $$
  \times ( \text{Température de référence} - \text{Température mesurée} ) \times 10
  $$

  **Exemple** : Si la température d’un bâtiment est **16 °C** et son coefficient de transmission thermique est de **2.5 W/m²K**, alors la consommation théorique est :

  $$ 2.5 \times (18 - 16) \times 10 = 50 \text{ kWh} $$

### Analyse des Données et Statistiques (6 points)

Dans l'onglet **"Data"**, ajoutez une colonne **"Alerte"** indiquant :

- **1** si la consommation réelle est supérieure au seuil critique (500 kWh),
- **0** sinon.

Effectuez ensuite les calculs suivants clairement dans cet onglet :

- Calculez en bas du tableau le nombre total de situations critiques (nombre de "Alerte = 1").
- Calculez la consommation totale par bâtiment dans une zone clairement identifiée sous les données.

### Création et Analyse Graphique (4 points)

Réalisez les graphiques suivants dans un nouvel onglet nommé **"Graphiques"** :

- Un **histogramme** comparant la consommation totale des bâtiments.
- Un **nuage de points** représentant la relation entre consommation (axe vertical) et coefficient de transmission thermique (axe horizontal).

### Question de synthèse (2 points)

Dans l'onglet **"Data"**, sous les statistiques, répondez brièvement à la question suivante :

> **Selon vos analyses, quels bâtiments méritent une attention particulière pour une amélioration énergétique, et pourquoi ?** (2 à 3 phrases maximum)

