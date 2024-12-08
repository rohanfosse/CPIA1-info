---
section: Flowgorithm
nav_order: 2
title: Exercices Corrigés
topics: Flowgorithm; Algorithmique; Commandes
---

### **Exercice : Jeu du Plus ou Moins**

### **Énoncé de l'exercice :**
Vous devez créer un programme en Flowgorithm pour un jeu du **"Plus ou Moins"** où l'utilisateur doit deviner un nombre secret. Voici les consignes :

1. **Définir un nombre secret** : Utilisez une fonction qui génère un nombre aléatoire entre 1 et 100.  
2. **Saisie de l'utilisateur** : Demandez à l'utilisateur d'entrer un nombre compris entre 1 et 100.  
3. **Comparer la saisie au nombre secret** :  
   - Si la saisie est supérieure au nombre secret, affichez :  
     ```
     "Le nombre est trop grand !"
     ```
   - Si la saisie est inférieure au nombre secret, affichez :  
     ```
     "Le nombre est trop petit !"
     ```
4. **Répétez jusqu'à trouver** : Tant que l'utilisateur ne devine pas le bon nombre, continuez à lui demander une nouvelle tentative.  
5. **Victoire** : Une fois que l'utilisateur trouve le bon nombre, affichez un message :  
   ```
   Bravo ! Vous avez trouvé le nombre secret !
   ```

---

### **Critères de réussite :**
- Le programme doit utiliser une **boucle** pour répéter la saisie tant que le nombre n’est pas trouvé.  
- Les **conditions** doivent permettre de comparer la saisie avec le nombre secret.  
- Un message doit être affiché pour guider l’utilisateur (trop grand, trop petit, ou correct).

---

### **Extension facultative :**
Ajoutez un compteur pour afficher le nombre de tentatives effectuées par l’utilisateur à la fin du jeu.  
Exemple de sortie :
```
Bravo ! Vous avez trouvé le nombre secret en 5 tentatives !
```

---

<div class="faq-container">
  <div class="faq-section flowgorithm">
    <div class="faq-section-title">
      Correction : Jeu du Plus ou Moins
      <span class="arrow">▼</span>
    </div>
    <div class="faq-content">
      <p>
        Voici un exemple de correction pour cet exercice en Flowgorithm :
      </p>
      <img src="image/02-ExercicesCorriges/1733675607594.png" alt="Diagramme de solution : Jeu du Plus ou Moins" />
      <p>
        Le diagramme utilise une boucle pour répéter la saisie, avec des conditions permettant d’afficher si le nombre est trop grand ou trop petit, et un message de victoire une fois le nombre trouvé.
      </p>
    </div>
  </div>
</div>

<script>
document.addEventListener("DOMContentLoaded", function () {
  const sectionTitles = document.querySelectorAll(".faq-section-title");

  sectionTitles.forEach((title) => {
    title.addEventListener("click", function () {
      const section = this.parentElement;
      const content = section.querySelector(".faq-content");

      if (section.classList.contains("open")) {
        // Fermer la section
        section.classList.remove("open");
        content.style.maxHeight = "0"; // Réduit la hauteur
        content.style.padding = "0 20px"; // Réduit le padding
      } else {
        // Ouvrir la section
        section.classList.add("open");
        content.style.maxHeight = `${content.scrollHeight}px`; // Hauteur du contenu
        content.style.padding = "20px"; // Ajoute le padding
      }
    });
  });
});
</script>

