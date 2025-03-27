---
section: BDD
nav_order: 6
title: Les arbres algébriques
topics: BDD; SQL; Algèbre relationnelle; Arbres algébriques
---

## Objectifs pédagogiques

- Comprendre le rôle de l'algèbre relationnelle dans la manipulation des données.
- Savoir lire et interpréter un arbre algébrique.
- Savoir écrire un arbre algébrique à partir d'une requête SQL.

## Algèbre relationnelle

L'algèbre relationnelle est un langage formel permettant de manipuler des données stockées dans des tables. Elle est utilisée dans les bases de données relationnelles pour effectuer des opérations de sélection, de projection, de jointure, etc.

### Opérations de base

Les opérations de base de l'algèbre relationnelle sont les suivantes :

- **Sélection** : $\sigma_{\text{condition}}(R)$
- **Projection** : $\pi_{\text{liste\_colonnes}}(R)$
- **Union** : $R \cup S$
- **Différence** : $R - S$
- **Produit cartésien** : $R \times S$
- **Jointure** : $R \bowtie S$
- **Division** : $R \div S$

### Sélection

La sélection permet de filtrer les lignes d'une table en fonction d'une condition. Par exemple, pour sélectionner les employés dont le salaire est supérieur à 2000€ :

$$
\sigma_{\text{salaire} > 2000}(\text{Employe})
$$

### Projection

La projection permet de sélectionner les colonnes d'une table. Par exemple, pour sélectionner les noms et prénoms des employés :

$$
\pi_{\text{nom, prenom}}(\text{Employe})
$$

### Union

L'union permet de combiner les lignes de deux tables. Les tables doivent avoir le même schéma. Par exemple, pour combiner les employés et les clients :

$$
\text{Employe} \cup \text{Client}
$$

### Différence

La différence permet de sélectionner les lignes d'une table qui ne sont pas présentes dans une autre table. Par exemple, pour sélectionner les employés qui ne sont pas clients :

$$
\text{Employe} - \text{Client}
$$

### Produit cartésien

Le produit cartésien permet de combiner les lignes de deux tables. Les tables n'ont pas besoin d'avoir le même schéma. Par exemple, pour combiner les employés et les projets :

$$
\text{Employe} \times \text{Projet}
$$

### Jointure

La jointure permet de combiner les lignes de deux tables en fonction d'une condition. Par exemple, pour combiner les employés et les projets sur la colonne `idProjet` :

$$
\text{Employe} \bowtie_{\text{Employe.idProjet = Projet.idProjet}} \text{Projet}
$$

### Division

La division permet de sélectionner les lignes d'une table qui ont une relation avec toutes les lignes d'une autre table. Par exemple, pour sélectionner les employés qui travaillent sur tous les projets :

$$
\text{Employe} \div \text{Projet}
$$

## Arbres algébriques

Un arbre algébrique est une représentation graphique d'une requête SQL en algèbre relationnelle. Il permet de visualiser les opérations effectuées sur les tables et les colonnes.

### Structure

Un arbre algébrique est composé de plusieurs éléments :

- **Opération** : la nature de l'opération effectuée (sélection, projection, jointure, etc.).
- **Table** : le nom de la table concernée.
- **Condition** : la condition de sélection ou de jointure.
- **Colonnes** : les colonnes sélectionnées ou projetées.

### Exemple simple

Considérons la table `Employe` suivante : idEmploye, nom, prenom, salaire.

Nous souhaitons sélectionner les noms et prénoms des employés dont le salaire est supérieur à 2000€. Voici la requête SQL correspondante :

```sql
SELECT nom, prenom
FROM Employe
WHERE salaire > 2000;
```

Cette requête peut être représentée par l'arbre algébrique suivant :

```plaintext
π_{nom, prenom}(
    σ_{salaire > 2000}(
        Employe
    )
)
```

En effet, pour obtenir les noms et prénoms des employés dont le salaire est supérieur à 2000€, nous devons :

1. Sélectionner les lignes pour lesquelles le salaire est supérieur à 2000€.
2. Projeter les colonnes `nom` et `prenom`.

### Deuxième exemple

Considérons les tables suivantes :

- `Employe` : idEmploye, nom, prenom, idProjet
- `Projet` : idProjet, nomProjet, dateDebut, dateFin

Nous souhaitons sélectionner les noms et prénoms des employés travaillant sur le projet "Projet1". Voici la requête SQL correspondante :

```sql
SELECT nom, prenom
FROM Employe
WHERE idProjet = (SELECT idProjet FROM Projet WHERE nomProjet = 'Projet1');
```

Cette requête peut être représentée par l'arbre algébrique suivant :

```plaintext
π_{nom, prenom}(
    σ_{idProjet = idProjetProjet1}(
        Employe ⨝_{idProjet = idProjetProjet1} Projet
    )
)
```

En effet, pour obtenir les noms et prénoms des employés travaillant sur le projet "Projet1", nous devons :

1. Joindre les tables `Employe` et `Projet` sur la colonne `idProjet`.
2. Sélectionner les lignes pour lesquelles le nom du projet est "Projet1".
3. Projeter les colonnes `nom` et `prenom`.


### Troisième exemple

Considérons les tables suivantes :

- `Employe` : idEmploye, nom, prenom, idProjet
- `Projet` : idProjet, nomProjet, dateDebut, dateFin
- `Client` : idClient, nomClient, adresse
- `ProjetClient` : idProjet, idClient

Nous souhaitons sélectionner les noms et prénoms des employés travaillant sur les projets des clients dont l'adresse est "Paris". Voici la requête SQL correspondante :

```sql
SELECT nom, prenom
FROM Employe
WHERE idProjet IN (SELECT idProjet FROM ProjetClient WHERE idClient IN (SELECT idClient FROM Client WHERE adresse = 'Paris'));
```

Cette requête peut être représentée par l'arbre algébrique suivant :

```plaintext
π_{nom, prenom}(
    σ_{idProjet IN (π_{idProjet}(
        σ_{idClient IN (π_{idClient}(
            σ_{adresse = 'Paris'}(
                Client
            )
        ))}(
            ProjetClient
        )
    )}(
        Employe
    )
)
```

En effet, pour obtenir les noms et prénoms des employés travaillant sur les projets des clients dont l'adresse est "Paris", nous devons :

1. Sélectionner les lignes pour lesquelles l'adresse du client est "Paris".
2. Projeter les colonnes `idClient`.
3. Sélectionner les lignes pour lesquelles l'id du client est dans la liste des id obtenus précédemment.
4. Projeter les colonnes `idProjet`.
5. Sélectionner les lignes pour lesquelles l'id du projet est dans la liste des id obtenus précédemment.
6. Projeter les colonnes `nom` et `prenom`.

## Exercices Corrigés

### Exercice 1

Considérons la table `Employe` suivante : idEmploye, nom, prenom, salaire.

1. Sélectionner les noms et prénoms des employés dont le nom commence par "D".
2. Sélectionner les noms des employés dont le prénom est "Jean".
3. Sélectionner les noms et prénoms des employés dont le salaire est compris entre 2000€ et 3000€.

#### Solution

1. Sélectionner les noms et prénoms des employés dont le nom commence par "D" :

```plaintext
π_{nom, prenom}(
    σ_{nom LIKE 'D%'}(
        Employe
    )
)
```

Explication :

- $\sigma_{nom LIKE 'D%}$ : sélection des lignes pour lesquelles le nom commence par "D".
- $\pi_{nom, prenom}$ : projection des colonnes `nom` et `prenom`.

2. Sélectionner les noms des employés dont le prénom est "Jean" :

```plaintext
π_{nom}(
    σ_{prenom = 'Jean'}(
        Employe
    )
)
```

Explication :

- $\sigma_{prenom = 'Jean'}$ : sélection des lignes pour lesquelles le prénom est "Jean".
- $\pi_{nom}$ : projection de la colonne `nom`.

3. Sélectionner les noms et prénoms des employés dont le salaire est compris entre 2000€ et 3000€ :

```plaintext
π_{nom, prenom}(
    σ_{salaire >= 2000 AND salaire <= 3000}(
        Employe
    )
)
```

Explication :

- $\sigma_{salaire >= 2000 AND salaire <= 3000}$ : sélection des lignes pour lesquelles le salaire est compris entre 2000€ et 3000€.
- $\pi_{nom, prenom}$ : projection des colonnes `nom` et `prenom`.

---

### Exercice 2

Considérons les tables suivantes :

- `Eleve` : idEleve, nom, prenom, dateNaissance
- `Note` : idNote, idEleve, idMatiere, valeur
- `Matiere` : idMatiere, nomMatiere

1. Sélectionner les noms et prénoms des élèves nés après le 1er janvier 2001.
2. Sélectionner les noms des élèves ayant une note supérieure à 10 en mathématiques.
3. Calculer la moyenne des notes des élèves pour chaque matière.

#### Solution

1. Sélectionner les noms et prénoms des élèves nés après le 1er janvier 2001 :

```plaintext
π_{nom, prenom}(
    σ_{dateNaissance > '2001-01-01'}(
        Eleve
    )
)
```

Explication :

- $\sigma_{dateNaissance > '2001-01-01'}$ : sélection des lignes pour lesquelles la date de naissance est après le 1er janvier 2001.
- $\pi_{nom, prenom}$ : projection des colonnes `nom` et `prenom`.

2. Sélectionner les noms des élèves ayant une note supérieure à 10 en mathématiques :

```plaintext
π_{nom}(
    σ_{valeur > 10 AND nomMatiere = 'Mathématiques'}(
        Eleve ⨝_{idEleve = idEleveNote} Note ⨝_{idMatiere = idMatiereMatiere} Matiere
    )
)
```

Explication :

- $\sigma_{valeur > 10 AND nomMatiere = 'Mathématiques'}$ : sélection des lignes pour lesquelles la valeur de la note est supérieure à 10 et le nom de la matière est "Mathématiques".
- $\pi_{nom}$ : projection de la colonne `nom`.

3. Calculer la moyenne des notes des élèves pour chaque matière :

```plaintext
π_{nomMatiere, AVG(valeur)}(
    Eleve ⨝_{idEleve = idEleveNote} Note ⨝_{idMatiere = idMatiereMatiere} Matiere
)
```

Explication :

- $\pi_{nomMatiere, AVG(valeur)}$ : projection des colonnes `nomMatiere` et moyenne de la colonne `valeur`.
- `AVG(valeur)` : calcul de la moyenne des valeurs de la colonne `valeur`.
- `Eleve ⨝_{idEleve = idEleveNote} Note ⨝_{idMatiere = idMatiereMatiere} Matiere` : jointure des tables `Eleve`, `Note` et `Matiere`. La jointure est nécessaire puisque les données sont réparties sur plusieurs tables. La condition de jointure est donnée par les colonnes `idEleve = idEleveNote` et `idMatiere = idMatiereMatiere`.

---
