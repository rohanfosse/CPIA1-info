---
section: BDD
nav_order: 2
title: Gestion de projet et structuration des données
topics: BDD; WBS; OBS; Dictionnaire de données; Dépendances fonctionnelles
---

## Objectifs pédagogiques

- Comprendre les notions de WBS et d’OBS dans un projet SI.
- Savoir définir, organiser et classer les données d’un système.
- Identifier les dépendances fonctionnelles.

---

## 1. Notions

### 1.1 Le WBS (Work Breakdown Structure)

La Work Breakdown Structure (WBS), ou structure de décomposition du travail, est une représentation hiérarchique d'un projet, où chaque niveau décompose les livrables ou activités du projet en sous-tâches.

Elle permet de structurer le projet, de mieux estimer les coûts, d’affecter les ressources et de planifier le travail.

> Par exemple, dans un projet de création d’un site web :
>
> - Niveau 1 : Projet site web
> - Niveau 2 : Rédaction contenu, développement, tests
> - Niveau 3 : Développement frontend, backend, base de données

### 1.2 L’OBS (Organizational Breakdown Structure)

L'Organizational Breakdown Structure (OBS) est une représentation hiérarchique de l'organisation humaine du projet. Elle permet de visualiser qui est responsable de quoi.

L’OBS est souvent croisée avec la WBS pour former une matrice de responsabilités (ex : matrice RACI).

> Elle répond aux questions : Qui fait quoi ? Qui supervise quoi ?

### 1.3 Le dictionnaire de données

Un dictionnaire de données est un document décrivant toutes les données manipulées dans un SI. Pour chaque donnée, on y précise :

- le nom de la donnée,
- son type (texte, numérique, date...),
- sa taille,
- sa signification,
- ses valeurs possibles,
- ses contraintes (unicitié, obligatoire...).

Cela permet une meilleure compréhension et une cohérence dans le traitement de l'information.

### 1.4 La catégorisation des données

Pour organiser les données, on les classe en catégories selon leur rôle :

- **Données de référence** : constantes, peu modifiées (ex : liste des pays).
- **Données transactionnelles** : issues d’actions (ex : achat, commande).
- **Méta-données** : informations sur les autres données (date de création, auteur, etc.).

Cette classification aide à définir les besoins de stockage, les droits d’accès et les règles de gestion.

### 1.5 Les dépendances fonctionnelles

Une dépendance fonctionnelle est une relation logique entre deux attributs d'une table : un attribut A détermine un attribut B si, pour chaque valeur de A, il existe une unique valeur de B.

Notation : A → B ("A détermine B")

> Exemple : si l’on connaît le numéro d’étudiant, on peut déterminer le nom. Donc : NumEtudiant → Nom.

Les dépendances fonctionnelles sont fondamentales pour la normalisation et la conception de bases de données cohérentes.
