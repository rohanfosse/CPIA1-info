---
section: BDD
nav_order: 5
title: Introduction à SQL
topics: BDD; SQL; SGBD; Requêtes; Données
---

## Objectifs pédagogiques

- Comprendre le rôle du langage SQL dans la gestion des bases de données relationnelles.
- Créer une base de données et des tables avec des contraintes simples.
- Manipuler les données avec les instructions `SELECT`, `INSERT`, `UPDATE` et `DELETE`.
- Interroger les données avec des filtres, des tris, des jointures simples.

---

## 1. À quoi sert SQL dans l’ingénierie ?

SQL est omniprésent dans tous les domaines d’ingénierie dès lors que des **données structurées** doivent être stockées, interrogées, croisées ou analysées.

### Exemples par domaine :

- **Informatique** : base de données d’utilisateurs, de commandes, de logs, d’applications web, etc.
- **BTP (Bâtiment et Travaux Publics)** :
  - gestion des chantiers, matériaux, fournisseurs ;
  - suivi des interventions, des plans, des équipes techniques ;
  - historique des incidents et maintenances ;
- **Génie industriel** : traçabilité des produits, gestion d'entrepôts, production, qualité.
- **Énergie** : gestion des capteurs, consommation, anomalies, historiques de mesures.
- **Transport / logistique** : itinéraires, flotte, clients, expéditions, temps de trajet.

---

## Qu’est-ce que SQL ?

SQL (Structured Query Language) est le **langage standard** utilisé pour gérer les bases de données relationnelles. Il permet :

- De **définir** les structures de stockage (tables, colonnes, clés, contraintes),
- De **manipuler** les données (insertion, modification, suppression, lecture),
- De **contrôler** les droits d’accès ou de faire des calculs/statistiques simples.

➡️ SQL est **déclaratif** : on décrit **ce que l’on veut**, pas comment le faire.

---

## Les types de données en SQL

SQL propose plusieurs types de données pour stocker des informations :

- **Entiers** : `INT`, `BIGINT`, `SMALLINT`, `TINYINT`.
- **Décimaux** : `DECIMAL(precision, scale)`, `NUMERIC(precision, scale)`, `FLOAT`, `REAL`.
- **Chaînes de caractères** : `CHAR(n)`, `VARCHAR(n)`, `TEXT`.
- **Dates et heures** : `DATE`, `TIME`, `DATETIME`, `TIMESTAMP`.
- **Booléens** : `BOOLEAN`, `BIT`.

---

## 3. Les instructions SQL de base

Les instructions SQL sont divisées en plusieurs catégories :

- **DDL** (Data Definition Language) : pour créer, modifier ou supprimer des structures (tables, index, etc.). Ex. : `CREATE TABLE`.
- **DML** (Data Manipulation Language) : pour insérer, lire, mettre à jour ou supprimer des données. Ex. : `SELECT`, `INSERT`, `UPDATE`, `DELETE`.
- **DCL** (Data Control Language) : pour gérer les droits d’accès aux données. Ex. : `GRANT`, `REVOKE`.
- **DQL** (Data Query Language) : pour interroger les données. Ex. : `SELECT`.

---

## 4. Les étapes pour manipuler des données en SQL

Pour manipuler des données en SQL, on suit généralement ces étapes :

1. **Créer une base de données** : `CREATE DATABASE`.
2. **Sélectionner la base de données** : `USE`.
3. **Créer une table** : `CREATE TABLE ...`.
4. **Insérer des données** : `INSERT INTO ...`.
5. **Lire les données** : `SELECT ...`.
6. **Mettre à jour ou supprimer des données** : `UPDATE`, `DELETE`.
7. **Gérer plusieurs tables** : les jointures.
8. **Calculer et regrouper** : fonctions d’agrégation.

---

### Créer une base de données : `CREATE DATABASE`

La première étape consiste à **créer une base de données** pour stocker les informations.

```sql
CREATE DATABASE NomBase;
```

#### Exemple

```sql
CREATE DATABASE Ecole;
```

#### Explication

Cela crée une base de données nommée `Ecole` pour stocker les informations sur les étudiants, les cours, les enseignants, etc.

---

### Sélectionner une base de données : `USE`

Une fois la base créée, on la **sélectionne** pour y travailler.

```sql
USE NomBase;
```

#### Exemple

```sql
USE Ecole;
```

### Créer une table : `CREATE TABLE`

Créer une table est une étape fondamentale. Elle permet de **structurer les données** et de définir les **relations** entre elles.

```sql
CREATE TABLE NomTable (
    nomColonne1 Type1,
    nomColonne2 Type2,
    ...
);
```

#### Exemple

```sql
CREATE TABLE Etudiant (
    idEtudiant INT PRIMARY KEY,
    nom VARCHAR(50),
    prenom VARCHAR(50),
    dateNaissance DATE
);
```

#### Explication

- `idEtudiant` : identifiant unique (clé primaire).
- `VARCHAR(50)` : chaîne de caractères (max. 50).
- `DATE` : champ de type date.

---

### Insérer des données : `INSERT INTO`

Une fois les structures définies, on peut **ajouter des données**.

```sql
INSERT INTO Etudiant (idEtudiant, nom, prenom, dateNaissance)
VALUES (1, 'Durand', 'Claire', '2001-03-25');
```

Il est possible d’insérer plusieurs lignes en une seule instruction.

```sql
INSERT INTO Etudiant (idEtudiant, nom, prenom, dateNaissance)
VALUES (2, 'Dupont', 'Pierre', '2000-05-12'),
       (3, 'Martin', 'Sophie', '2002-07-18');
```

Il est aussi possible de ne pas préciser les colonnes si on insère toutes les valeurs.

```sql
INSERT INTO Etudiant
VALUES (4, 'Lefevre', 'Luc', '2001-11-30');
```

Enfin, le numéro d’identifiant peut être généré automatiquement.

```sql
INSERT INTO Etudiant (nom, prenom, dateNaissance)
VALUES ('Leroy', 'Marie', '2000-09-22');
```

---

### Lire les données : `SELECT`

Pour lire les données, on utilise l’instruction `SELECT`.

```sql
SELECT colonne1, colonne2, ...
FROM table
WHERE condition
ORDER BY colonne ASC|DESC;
```

Les attributs `WHERE` et `ORDER BY` sont optionnels. `ASC` signifie **ascendant** (dans l’ordre croissant, par défaut) et `DESC` **descendant**.

#### Exemples

```sql
SELECT nom, prenom
FROM Etudiant
WHERE dateNaissance > '2001-01-01'
ORDER BY nom ASC;
```

Cette requête sélectionne les noms et prénoms des étudiants nés après le 1er janvier 2001, triés par ordre alphabétique des noms.

```sql
SELECT *
FROM Etudiant;
```

Cette requête sélectionne toutes les colonnes de la table `Etudiant`.

```sql
SELECT prenom
FROM Etudiant
WHERE nom = 'Dupont';
```

Cette requête sélectionne les prénoms des étudiants dont le nom est `Dupont`.

---

### Mettre à jour des données : `UPDATE`

Pour modifier des données, on utilise l’instruction `UPDATE`.

```sql
UPDATE table
SET colonne1 = valeur1, colonne2 = valeur2, ...
WHERE condition;
```

La condition est importante pour ne pas modifier toutes les lignes de la table, elle n'est cependant pas obligatoire.

#### Exemple

```sql
UPDATE Etudiant
SET nom = 'Dupond'
WHERE nom = 'Dupont';
```

Cette requête met à jour le nom des étudiants `Dupont` en `Dupond`.

---

### Supprimer des données : `DELETE`

Pour supprimer des données, on utilise l’instruction `DELETE`.

```sql
DELETE FROM table
WHERE condition;
```

#### Exemples

```sql
DELETE FROM Etudiant
WHERE nom = 'Lefevre';
```

Cette requête supprime l’étudiant `Lefevre`.

```sql
DELETE FROM Etudiant;
```

Cette requête supprime tous les étudiants de la table. Attention à son utilisation !

