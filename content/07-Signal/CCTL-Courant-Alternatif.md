---
section_id: Signal
nav_order: 7
title: CCTL - Courant Alternatif
topics: Courant; Alternatif; Impédance; Diagrammes de Fresnel; Filtres électroniques
---

<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/katex/dist/katex.min.css">
<script defer src="https://cdn.jsdelivr.net/npm/katex/dist/katex.min.js"></script>
<script defer src="https://cdn.jsdelivr.net/npm/katex/dist/contrib/auto-render.min.js"
    onload="renderMathInElement(document.body);"></script>

## Rappels des Acquis d'Apprentissages Visés (AAV)

Les AAVs correspondent ici aux attendus des prosits 2 et 3 du projet signal. Ils sont détaillés ci-dessous :

- [2] Expliquer le comportement d'un condensateur et d'une bobine dans un circuit
- [2] Décrire les caractéristiques physiques d'un circuit et de ses composants soumis à un courant alternatif (inductance, capacité, impédance, phase)
- [2] Expliquer le comportement des différents filtres : RL, RC
- [3] Représenter et manipuler les grandeurs électriques au travers de leur modèle mathématique (représentation de Fresnel, nombres complexes)
- [3] Etablir la fonction de transfert d'un circuit électronique de base
- [3] Établir la fonction de transfert d’un filtre
- [3] Appliquer le théorème de Millmann
- [3] Utiliser les nombres complexes pour calculer une impédance complexe
- [2] Expliquer le comportement d'un circuit RLC
- [3] Produire un diagramme de Bode
- [2] Interpréter une courbe de réponse fréquentielle
- [2] Reconnaître les filtres passe-bas/haut/bande

<!-- TOC -->

---

## Table des matières

1. [Rappels des Acquis d'Apprentissages Visés AAV](#rappels-des-acquis-dapprentissages-vis%C3%A9s-aav)
2. [Microphones : Fonctionnement et classification](#microphones--fonctionnement-et-classification)
3. [Traitement des signaux sonores](#traitement-des-signaux-sonores)
4. [Introduction aux diagrammes de Fresnel](#introduction-aux-diagrammes-de-fresnel)
5. [Étude pratique : Filtrage de voix humaines](#%C3%A9tude-pratique--filtrage-de-voix-humaines)
6. [Courant alternatif CA](#courant-alternatif-ca)
7. [Grandeurs caractéristiques du courant alternatif](#grandeurs-caract%C3%A9ristiques-du-courant-alternatif)
8. [Grandeurs sinusoïdales](#grandeurs-sinuso%C3%AFdales)
9. [Différence entre composants actifs et passifs](#diff%C3%A9rence-entre-composants-actifs-et-passifs)
10. [Les filtres électroniques](#les-filtres-%C3%A9lectroniques)
11. [Application pratique : Théorème de Millman](#application-pratique--th%C3%A9or%C3%A8me-de-millman)

---

### Introduction aux composants électroniques

#### Définition et rôle des composants

Les composants électroniques sont les éléments de base des circuits électriques et jouent des rôles spécifiques dans le fonctionnement des dispositifs électroniques. Voici les définitions des principaux composants que nous allons aborder :

- **Interphone** : Dispositif de communication équipé d’un microphone et d’un haut-parleur, utilisé pour transmettre la voix sur une courte distance.
- **Microphone** : Capteur qui convertit les sons en signaux électriques. Il constitue un élément essentiel des systèmes de captation sonore.
- **Haut-parleur** : Dispositif qui transforme les signaux électriques en sons audibles, permettant la restitution sonore.
- **Inductance** : Composant qui génère un flux magnétique lorsqu’il est traversé par un courant. Utilisée dans les filtres pour bloquer ou permettre le passage de certaines fréquences.
- **Condensateur** : Élément capable de stocker de l’énergie électrique. Fondamental dans les circuits de filtrage et de régulation de tension.
- **Impédance** : Caractéristique d’opposition d’un circuit au passage du courant, exprimée en ohms (Ω). Elle intègre des résistances, inductances et capacités dans un circuit.

#### Comportement des composants dans un circuit

Chaque composant a un rôle précis dans le traitement des signaux électriques :

- **Inductance** : Utilisée pour filtrer ou lisser les variations de courant dans un circuit.
- **Condensateur** : Employé pour bloquer les courants continus tout en laissant passer les courants alternatifs (fonction de filtrage).
- **Impédance** : Analyse essentielle dans la conception de circuits en régime alternatif (AC). Elle détermine la répartition des tensions et courants dans un circuit.

#### Exemple pratique : Les composants d’un interphone

Un interphone typique inclut :

- Un microphone pour capturer la voix.
- Un amplificateur pour augmenter le signal.
- Un haut-parleur pour restituer la voix à l’autre extrémité.

---

### Microphones : Fonctionnement et classification

#### Les microphones comme générateurs

Un microphone est un dispositif électroacoustique qui transforme les ondes sonores en signaux électriques. Cette transformation repose sur des principes physiques et peut être modélisée mathématiquement.

- **Modèle de Thévenin** :
  Un microphone peut être représenté comme un générateur de tension alternative accompagné de sa résistance interne. Lorsque le microphone capte un **son pur** (onde sinusoïdale de fréquence unique), il produit un signal électrique périodique et sinusoïdal ayant la même fréquence que la source sonore.

- **Lien avec les séries de Fourier** :
  Les sons complexes, comme la voix humaine ou un morceau de musique, peuvent être décomposés en une somme de signaux sinusoïdaux grâce aux séries de Fourier. Cette décomposition est essentielle pour analyser et traiter les signaux sonores.

---

#### Classification des microphones

Les microphones se distinguent par leur principe de fonctionnement, leur mode d’action et leur directivité.

##### Par principe de transduction

La conversion des ondes sonores en signaux électriques repose sur différents phénomènes physiques :

- **Effets magnétiques (microphones électrodynamiques)** :
  - À bobine mobile : Utilisés pour leur robustesse et leur capacité à capter des sons forts.
  - À ruban : Sensibles, souvent utilisés en studio.
- **Effets électrostatiques (microphones électrostatiques)** :
  - À membrane polarisée (condensateurs) : Offrent une grande précision sonore.
  - À membrane pré-polarisée (électrets) : Compactes et largement répandus.
- **Effets piézo-électriques (microphones piézoélectriques)** :
  - À cristaux (quartz) : Utilisés pour leur sensibilité élevée.
  - À céramiques et polymères : Adaptés aux applications spécifiques nécessitant une réponse rapide.

##### Par mode d’action du diaphragme

- En pression : Sensibles aux variations de pression sonore.
- En gradient de pression : Captent les différences de pression entre deux faces du diaphragme.
- Mixte : Combinaison des deux modes.

##### Par directivité

La directivité détermine la manière dont le microphone capte les sons en fonction de leur provenance :

- Omnidirectionnelle : Capte les sons de toutes les directions.
- Bidirectionnelle : Capte les sons provenant de deux directions opposées.
- Unidirectionnelle : Conçue pour capter principalement les sons provenant d’une direction spécifique (exemples : microphones cardioïdes, supercardioïdes, hypercardioïdes).

---

#### Choix d’un microphone en fonction des besoins

Les différents types de microphones sont adaptés à des usages spécifiques :

- Un microphone cardioïde est idéal pour enregistrer une voix tout en isolant les bruits ambiants.
- Un microphone omnidirectionnel est préférable pour capturer les sons ambiants lors d’une conférence.
- Un microphone piézoélectrique est adapté aux environnements nécessitant une grande robustesse.

---

### Traitement des signaux sonores

#### Notions fondamentales

Le traitement des signaux sonores consiste à modifier ou analyser les signaux électriques générés par des dispositifs comme les microphones, afin de répondre à des besoins spécifiques tels que le filtrage des bruits, l’amplification ou l’analyse spectrale.

##### Fonction de transfert d’un filtre

Un filtre est un dispositif qui modifie un signal sonore en fonction de sa fréquence. La **fonction de transfert** d’un filtre est une représentation mathématique qui relie l’entrée (signal brut) à la sortie (signal filtré). Elle détermine le comportement du filtre en fonction de la fréquence.

- Exemple : Un filtre passe-haut laisse passer les fréquences supérieures à une certaine valeur appelée fréquence de coupure et atténue les fréquences inférieures.

##### Gain d’un filtre

Le gain mesure l’efficacité du filtre à amplifier ou atténuer un signal sonore à différentes fréquences. Il est exprimé en **décibels (dB)** et calculé comme suit :

$$
Gain \, (dB) = 20 \cdot \log\_{10}(H(f))
$$

où $$H(f)$$ est le module de la fonction de transfert à une fréquence donnée $$f$$

- Exemple : Si $$H(f) = 10$$ à une fréquence donnée, alors le gain est :

$$
20 \cdot \log_{10}(10) = 20 dB
$$

---

#### Filtrage des sons

Le filtrage consiste à isoler ou atténuer certaines fréquences dans un signal sonore. Il existe différents types de filtres :

- **Passe-bas** : Laisse passer les fréquences inférieures à une fréquence de coupure.
- **Passe-haut** : Laisse passer les fréquences supérieures à une fréquence de coupure.
- **Passe-bande** : Laisse passer les fréquences comprises dans une plage donnée.
- **Coupe-bande** : Atténue les fréquences comprises dans une plage donnée.

##### Exemple de cas pratique : Filtrage d’une voix humaine

Problème : Vous souhaitez filtrer les basses fréquences générées par une machine (inférieures à 60 Hz) et conserver uniquement la voix humaine.
Solution : Utilisez un filtre **passe-haut** avec une fréquence de coupure de 60 Hz. Un circuit RC (résistance et condensateur) ou RL (résistance et inductance) peut être utilisé.

---

#### Étude des sons graves et leur filtrage

- **Sons graves** : Correspondent à des fréquences basses (<100 Hz). Ces sons sont souvent associés à des bruits ambiants ou des vibrations mécaniques indésirables.
- Importance du filtrage : Dans les applications de captation sonore (comme un interphone), le filtrage des sons graves est essentiel pour améliorer l’intelligibilité de la voix.

---

### Introduction aux diagrammes de Fresnel

#### Notions de base : Lois de Kirchhoff et impédance complexe

Les diagrammes de Fresnel permettent de représenter graphiquement des grandeurs électriques en régime sinusoïdal à l’aide de nombres complexes. Ces outils visuels sont essentiels pour analyser les relations entre tension, courant et impédance dans un circuit.

##### Lois de Kirchhoff

- **Loi des nœuds** : La somme des courants entrants dans un nœud est égale à la somme des courants sortants.
- **Loi des mailles** : Dans une maille fermée, la somme algébrique des tensions est nulle.
  Ces lois sont la base des calculs de tensions et de courants dans les circuits.

##### Impédance complexe

En régime sinusoïdal, les impédances des composants électriques sont définies par :

- **Résistance ($$R$$)** : Opposition au courant, indépendante de la fréquence.
- **Inductance ($$L$$)** : Impédance $$j\omega L$$, proportionnelle à la fréquence.
- **Capacité ($$C$$)** : Impédance $$-j/( \omega C)$$, inversement proportionnelle à la fréquence.

Relation tension-courant :

$$
V = Z \cdot I
$$

où $$V$$ est la tension, $$I$$ le courant, et $$Z$$ l’impédance complexe.

---

#### Étapes pour tracer un diagramme de Fresnel

Les diagrammes de Fresnel permettent de représenter les grandeurs en amplitude et en phase. Voici les étapes pour les construire :

1. **Établir la loi électrique** :

   - Identifier la relation entre les tensions et les courants (loi des nœuds ou des mailles).
   - Exemple : Dans un circuit RLC série, la tension totale est la somme des tensions aux bornes de $$R$$, $$L$$, et $$C$$.

2. **Choisir la grandeur de référence** :

   - Déterminer si la référence est une tension ou un courant, en fonction du circuit analysé.
   - Exemple : Dans un circuit série, la référence est souvent le courant total.

3. **Comparer les grandeurs** :

   - Représenter chaque grandeur par un vecteur dans le plan complexe, en tenant compte de son amplitude et de sa phase par rapport à la référence.

4. **Tracer le diagramme** :
   - Placer la grandeur de référence sur l’axe des abscisses.
   - Ajouter les autres vecteurs en respectant leurs amplitudes et déphasages.

---

#### Exemple guidé : Circuit RLC série

Considérons un circuit série contenant une résistance ($$R$$), une inductance ($$L$$), et une capacité ($$C$$) :

1. **Tensions individuelles** :

   - $$V_R = I \cdot R$$ (en phase avec le courant).
   - $$V_L = j\omega L \cdot I$$ (déphasée de $$+90^\circ$$ ).
   - $$V_C = -j/( \omega C) \cdot I$$ (déphasée de $$-90^\circ$$ ).

2. **Tension totale** :
    $$
   V\_{total} = V_R + V_L + V_C
   $$

3. **Tracé du diagramme** :

   - Représentez $$V_R$$ sur l’axe réel.
   - Ajoutez $$V_L$$ perpendiculairement à $$V_R$$.
   - Ajoutez $$V_C$$ dans la direction opposée à $$V_L$$.
   - Le vecteur résultant donne $$V\_{total}$$.

---

#### Application des diagrammes de Fresnel\*\*\*\*\*

Les diagrammes de Fresnel sont particulièrement utiles pour analyser des circuits en régime alternatif :

- **Analyse des déphasages** : Identifier si un circuit est principalement inductif (déphasage positif) ou capacitif (déphasage négatif).
- **Optimisation des circuits** : Adapter les composants pour réduire les pertes d’énergie.

---

### Étude pratique : Filtrage de voix humaines

#### Problème posé : Filtrer les basses fréquences

Lors de la captation sonore, les basses fréquences (<60 Hz), souvent générées par des machines ou des vibrations, peuvent masquer ou altérer les sons utiles, comme une voix humaine. L’objectif est de supprimer ces basses fréquences tout en préservant la clarté du signal vocal.

---

#### Solution technique : Utilisation d’un filtre passe-haut

Un **filtre passe-haut** est conçu pour laisser passer les fréquences supérieures à une certaine valeur appelée fréquence de coupure ($$f_c$$) et atténuer les fréquences inférieures.

##### Choix de la fréquence de coupure

Pour filtrer efficacement les basses fréquences tout en préservant la voix humaine :

- La fréquence de coupure est fixée à $$f_c = 60 \, \text{Hz}$$, car elle correspond à la limite inférieure des fréquences vocales humaines.

##### Conception d’un filtre passe-haut d’ordre 1

Un filtre passe-haut d’ordre 1 peut être conçu à l’aide :

- D’un circuit **RC** (résistance + condensateur).
- D’un circuit **RL** (résistance + inductance).

Formule pour la fréquence de coupure :

$$
f_c = \frac{1}{2 \pi R C} \quad \text{(pour un filtre RC)}
$$

ou

$$
f_c = \frac{R}{2 \pi L} \quad \text{(pour un filtre RL)}.
$$

##### Exemple : Conception d’un filtre RC

- Résistance $$R = 1 \, \text{k}\Omega$$.
- Capacité $$C$$ calculée pour $$f_c = 60 \, \text{Hz}$$ :

  $$
  C = \frac{1}{2 \pi R f_c} = \frac{1}{2 \pi \cdot 1000 \cdot 60} \approx 2.65 \, \mu\text{F}.
  $$

##### Courbe de réponse fréquentielle

La réponse fréquentielle du filtre montre que :

- Les fréquences supérieures à 60 Hz passent avec un gain proche de 1.
- Les fréquences inférieures à 60 Hz sont fortement atténuées.

---

#### Analyse des résultats

- **Signal filtré** : Une fois appliqué, le filtre réduit significativement le bruit basse fréquence tout en conservant la voix humaine.
- **Impact sur la qualité audio** : L’amélioration est particulièrement perceptible dans les environnements bruyants (usines, bureaux).

**Exemple d’application** :

- Interphone ou microphone dans une salle avec des vibrations mécaniques.

---

### Courant alternatif (CA)

#### Définition

Le courant alternatif (CA) est un type de courant électrique où la tension et l’intensité varient périodiquement dans le temps. Contrairement au courant continu (CC), où les électrons se déplacent toujours dans le même sens, le courant alternatif alterne régulièrement entre des directions opposées.

- **Caractéristiques principales** :
  - **Périodicité** : Le signal CA se répète à intervalles réguliers, ce qui en fait une fonction périodique.
  - **Formes courantes** : Signal sinusoïdal (le plus fréquent), carré, ou triangulaire.

---

### Grandeurs caractéristiques du courant alternatif

#### Valeur instantanée

La valeur instantanée ($$v(t)$$, $$i(t)$$) est la mesure de la tension ou du courant à un moment précis. Elle est exprimée comme une fonction du temps.

#### Amplitude ou valeur crête

La valeur maximale atteinte par un signal CA est appelée amplitude ($$V_m$$, $$I_m$$).

#### Période $$T$$)

La période correspond au temps nécessaire pour compléter un cycle complet du signal. Elle est mesurée entre deux points identiques de la courbe.

#### Fréquence $$f$$)

La fréquence représente le nombre de cycles complets qui se produisent par seconde. Elle est exprimée en hertz (Hz). La relation entre fréquence et période est donnée par :

$$
f = \frac{1}{T}, \quad T = \frac{1}{f}
$$

#### Alternance

Une alternance désigne une demi-période du signal, soit positive, soit négative.

#### Valeur efficace

La valeur efficace ($$V\_{eff}$$) est une mesure représentative de l’énergie moyenne du signal. Elle correspond à la valeur de tension ou de courant continu qui produirait le même échauffement dans une résistance :

$$
V_{eff} = \frac{V_m}{\sqrt{2}}
$$

---

### Grandeurs sinusoïdales

#### Forme mathématique d’un signal sinusoïdal

Un signal sinusoïdal peut être décrit par :

$$
v(t) = V_m \cdot \sin(\omega t + \alpha)
$$

où :

- $$V_m$$ : Amplitude (valeur crête).
- $$\omega$$ : Pulsation en radians par seconde ($$\omega = 2\pi f$$).
- $$t$$ : Temps.
- $$\alpha$$ : Phase initiale.

#### Relations fondamentales

- Relation entre pulsation et période :

  $$
  \omega = \frac{2\pi}{T}
  $$

- Relation entre pulsation et fréquence :

  $$
  \omega = 2\pi f
  $$

---

### Différence entre composants actifs et passifs

#### Composants actifs

Un composant actif est un dispositif électronique capable d'amplifier un signal en utilisant une source d'énergie externe. Exemples :

- Transistors.
- Circuits intégrés.

#### Composants passifs

Un composant passif ne fournit pas d’énergie supplémentaire au signal et obéit à la loi d’Ohm généralisée. Exemples :

- Résistances.
- Condensateurs.
- Bobines.

---

### Les filtres électroniques

#### Définition

Un filtre est un circuit électronique conçu pour modifier le spectre fréquentiel d’un signal. Il peut :

- **Atténuer ou éliminer des fréquences indésirables**.
- **Isoler une plage de fréquences utile**.

#### Types de filtres

1. **Filtre passe-haut** :

   - Laisse passer les fréquences supérieures à une fréquence de coupure ($$f_c$$).
   - Exemple : Atténuation des graves dans un système audio.

2. **Filtre passe-bas** :

   - Laisse passer les fréquences inférieures à $$f_c$$.
   - Exemple : Réduction des aigus dans un signal bruité.

3. **Filtre passe-bande** :

   - Ne laisse passer qu’une plage spécifique de fréquences.
   - Exemple : Isolation d’une station radio.

4. **Filtre coupe-bande (réjecteur)** :
   - Atténue une plage spécifique de fréquences.
   - Exemple : Suppression des parasites à 50 Hz des alimentations électriques.

---

### Application pratique : Théorème de Millman

#### Définition

Le théorème de Millman est une méthode utilisée pour calculer la tension au nœud d’un circuit où plusieurs branches sont connectées en parallèle. C’est un outil puissant pour analyser les circuits complexes.

#### Formule du théorème de Millman

La tension au nœud est donnée par :

$$
V_n = \frac{\sum_{i=1}^{n} G_i \cdot V_i}{\sum_{i=1}^{n} G_i}
$$

où :

- $$V_n$$ : Tension au nœud.
- $$G_i = \frac{1}{R_i}$$ : Conductance de chaque branche ($$R_i$$ étant la résistance).
- $$V_i$$ : Tension appliquée dans chaque branche.

#### Exemple d’application

Considérons un circuit avec trois branches :

- Branches avec résistances $$R_1 = 1 \, \text{k}\Omega$$, $$R_2 = 2 \, \text{k}\Omega$$, et $$R_3 = 3 \, \text{k}\Omega$$.
- Tensions $$V_1 = 10 \, \text{V}$$, $$V_2 = 5 \, \text{V}$$, $$V_3 = 2 \, \text{V}$$.

**Étapes** :

1. Calculer les conductances $$G_1$$, $$G_2$$, et $$G_3$$.

   $$
   G_1 = \frac{1}{R_1} = \frac{1}{1000} = 0.001 \, \text{S}
   $$

   $$
   G_2 = \frac{1}{R_2} = \frac{1}{2000} = 0.0005 \, \text{S}
   $$

   $$
   G_3 = \frac{1}{R_3} = \frac{1}{3000} \approx 0.00033 \, \text{S}
   $$

2. Calculer le numérateur :

   $$
   \text{Numérateur} = G_1 \cdot V_1 + G_2 \cdot V_2 + G_3 \cdot V_3
   $$

   $$
   \text{Numérateur} = (0.001 \cdot 10) + (0.0005 \cdot 5) + (0.00033 \cdot 2) = 0.010 + 0.0025 + 0.00066 = 0.01316
   $$

3. Calculer le dénominateur :

   $$
   \text{Dénominateur} = G_1 + G_2 + G_3 = 0.001 + 0.0005 + 0.00033 = 0.00183
   $$

4. Calculer $V_n$ :

   $$
   V_n = \frac{\text{Numérateur}}{\text{Dénominateur}} = \frac{0.01316}{0.00183} \approx 7.19 \, \text{V}
   $$
