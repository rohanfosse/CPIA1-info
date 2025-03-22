---
section: BDD
nav_order: 3
title: Modèle Conceptuel des Données (MCD)
topics: BDD; MCD; MLD; Merise; Normalisation
---

## Objectifs pédagogiques

Ce module a pour objectif de fournir les bases nécessaires à la compréhension, à la conception et à la manipulation de bases de données relationnelles. À l’issue de ce module, l’apprenant sera capable de :

- Comprendre les concepts fondamentaux d’une base de données relationnelle, notamment les notions de table, enregistrement, clé primaire, clé étrangère et relation.
- Identifier les propriétés d’intégrité des données (intégrité d’entité, référentielle, de domaine) pour assurer la cohérence et la fiabilité des informations.
- Comprendre l’origine de la méthode Merise et son intérêt dans la modélisation conceptuelle des données et des traitements.
- Construire un Modèle Conceptuel des Données (MCD) clair et structuré, puis le traduire en Modèle Logique des Données (MLD) adapté à un système de gestion de base de données relationnelle.
- Appliquer les règles de normalisation afin de limiter la redondance, éviter les anomalies de mise à jour et garantir une structure logique optimisée des tables.

---

## 1. Notions : MCD

### 1.1 Origine et intérêt de Merise

Merise est une méthode d’analyse, de conception et de modélisation des systèmes d’information, développée en France dans les années 1980. Elle est encore largement utilisée dans les projets informatiques structurés autour de bases de données.

Cette méthode repose sur une séparation claire entre deux axes :

- Les **données** : ce que le système doit enregistrer, organiser et structurer.
- Les **traitements** : les opérations, actions ou règles que le système doit appliquer aux données.

Merise s’appuie sur trois niveaux de modélisation :

| Niveau                  | Objectif                                                        | Représentation                       |
| ----------------------- | --------------------------------------------------------------- | ------------------------------------ |
| MCD (Modèle Conceptuel) | Représenter les données de manière indépendante de la technique | Entités, associations, attributs     |
| MLD (Modèle Logique)    | Adapter les entités et associations au modèle relationnel       | Tables, clés primaires et étrangères |
| MPD (Modèle Physique)   | Implémenter les structures dans un SGBD concret                 | Types SQL, index, contraintes        |

Les avantages de Merise sont nombreux :

- Elle permet de structurer la modélisation avant toute phase de développement.
- Elle est indépendante des technologies utilisées (SGBD, langages).
- Elle facilite la communication entre les profils techniques et les utilisateurs métiers.

### 1.2 Le Modèle Conceptuel des Données (MCD)

Le MCD est un schéma graphique qui représente les entités à stocker, leurs attributs, et les relations (associations) entre elles. C’est une étape essentielle dans la modélisation des systèmes d’information.

#### Représentation des éléments du MCD

- **Entités** : représentées par des rectangles. Elles possèdent un identifiant (clé) et des attributs.
  - Exemple : `Client(idClient, nom, prénom)`
- **Attributs** : propriétés d’une entité (nom, date, email, etc.). Chaque attribut est propre à une entité donnée.
- **Associations** : représentées par des losanges. Elles relient deux ou plusieurs entités.
  - Exemple : `Passe` entre `Client` et `Commande`.
- **Cardinalités** : elles indiquent combien de fois une entité peut apparaître dans une association. Exemples : (1,1), (0,n), (1,n).

#### Exemple de MCD en notation ASCII

```
[Client]--------<Passe>--------[Commande]
 idClient                        idCommande
 nom                            dateCommande
 prenom
```

Ce diagramme signifie :

- Un `Client` peut passer plusieurs `Commandes`.
- Une `Commande` est liée à un seul `Client`.

---

### Exemple complet de construction de MCD

#### Énoncé

Une école gère ses enseignants, ses étudiants, et les cours proposés.
Chaque étudiant peut s’inscrire à plusieurs cours.
Chaque cours est dispensé par un seul enseignant, mais un enseignant peut enseigner plusieurs cours.
Chaque inscription d’un étudiant à un cours donne lieu à une note.

#### Étape 1 : Identifier les entités

Les entités correspondent aux objets principaux manipulés dans l’énoncé :

- `Etudiant`
- `Cours`
- `Enseignant`

Ce sont des entités fortes : elles existent indépendamment dans le système.

#### Étape 2 : Identifier les associations

Les associations décrivent les liens entre entités :

- `Inscription` entre `Etudiant` et `Cours`, avec un attribut `note`. (relation N,N)
- `Dispense` entre `Enseignant` et `Cours`. (relation 1,N)

#### Étape 3 : Identifier les attributs

Chaque entité possède des informations propres :

- `Etudiant` : `idEtudiant`, `nom`, `prenom`
- `Enseignant` : `idEnseignant`, `nom`, `specialite`
- `Cours` : `idCours`, `intitule`, `volumeHoraire`
- `Inscription` (association) : `note`

Règle générale : un attribut est une information spécifique à une seule entité. Si une information dépend de deux entités, elle appartient probablement à une association.

#### Étape 4 : Déterminer les cardinalités

Les cardinalités précisent combien d’occurrences d’une entité peuvent être liées à une autre.

Méthode :

- Lire attentivement les expressions : « un étudiant peut… », « chaque cours est… »
- Se poser la double question :
  - Un étudiant est lié à combien de cours ?
  - Un cours est lié à combien d’étudiants ?

On obtient :

- `Etudiant` —< `Inscription` >— `Cours` : (0,n) — (0,n)
- `Enseignant` —< `Dispense` >— `Cours` : (1,n) — (1,1)

#### MCD (notation ASCII)

```
[Etudiant]--------<Inscription>--------[Cours]--------<Dispense>--------[Enseignant]
 idEtudiant                          idCours                            idEnseignant
 nom                                intitule                           nom
 prenom                             volumeHoraire                      specialite
                                    note
```

#### Résumé

| Étape | Objectif                        | Résultat                                         |
| ----- | ------------------------------- | ------------------------------------------------ |
| 1     | Repérer les objets              | `Etudiant`, `Cours`, `Enseignant`                |
| 2     | Identifier les actions/liaisons | `Inscription`, `Dispense`                        |
| 3     | Lister les attributs            | Informations propres à chaque entité ou relation |
| 4     | Évaluer les quantités           | Cardinalités : 1,1 ; 0,n ; 1,n, etc.             |

---

