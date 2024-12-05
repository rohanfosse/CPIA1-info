---
section_id: Pour aller plus loin
nav_order: 6
title: Foire Aux Questions
topics: FAQ; Questions; Réponses
---

<style>
/* Style général de la FAQ */
.faq-container {
  max-width: 900px;
  margin: 0 auto;
  padding: 20px;
  font-family: 'Roboto', sans-serif;
}

.faq-title {
  font-size: 32px;
  color: #2a9df4;
  text-align: center;
  margin-bottom: 40px;
}

/* Style des sections */
.faq-section {
  margin-bottom: 40px;
  padding: 20px;
  border-radius: 8px;
  background-color: #f9f9f9;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
}

/* Thèmes */
.faq-section.excel {
  border-left: 5px solid #1d6f42; /* Vert pour Excel */
}
.faq-section.flowgorithm {
  border-left: 5px solid #ff8c42; /* Orange pour Flowgorithm */
}
.faq-section.arduino {
  border-left: 5px solid #0072ce; /* Bleu pour Arduino */
}
.faq-section.python {
  border-left: 5px solid #f4c542; /* Jaune pour Python */
}

/* Questions et réponses */
.faq-item {
  margin-bottom: 15px;
  border-radius: 8px;
  overflow: hidden;
  transition: all 0.3s ease;
}

.faq-question {
  font-size: 18px;
  color: #333;
  padding: 15px 20px;
  cursor: pointer;
  background: #ffffff;
  border-bottom: 1px solid #ddd;
  transition: background-color 0.3s ease;
}

.faq-question:hover {
  background-color: #f0f8ff;
}

.faq-answer {
  padding: 15px 20px;
  font-size: 16px;
  color: #555;
  line-height: 1.6;
  background: #fff;
  display: none; /* Masquer par défaut */
}

.faq-answer.active {
  display: block; /* Afficher la réponse si active */
}

/* Animation pour l'ouverture des réponses */
.faq-answer {
  animation: slideDown 0.3s ease;
}

@keyframes slideDown {
  from {
    max-height: 0;
    opacity: 0;
  }
  to {
    max-height: 200px;
    opacity: 1;
  }
}

/* Responsive Design */
@media (max-width: 768px) {
  .faq-title {
    font-size: 24px;
  }

  .faq-question {
    font-size: 16px;
  }

  .faq-answer {
    font-size: 14px;
  }
}
</style>

<div class="faq-container">
  <h1 class="faq-title">FAQ - Questions Fréquentes</h1>

  <!-- Section Excel -->
  <div class="faq-section excel">
    <h2>Excel</h2>
    <div class="faq-item">
      <div class="faq-question">Q : Comment créer une formule simple dans Excel ?</div>
      <div class="faq-answer">
        R : Sélectionnez une cellule, tapez `=` suivi de votre calcul (ex. : `=A1+B1`), puis appuyez sur Entrée. Excel affichera le résultat.
      </div>
    </div>
    <div class="faq-item">
      <div class="faq-question">Q : Comment figer une ligne ou une colonne dans Excel ?</div>
      <div class="faq-answer">
        R : Allez dans le menu **Affichage**, puis cliquez sur **Figer les volets**. Choisissez l'option appropriée pour figer la première ligne ou colonne.
      </div>
    </div>
  </div>

  <!-- Section Flowgorithm -->
  <div class="faq-section flowgorithm">
    <h2>Flowgorithm</h2>
    <div class="faq-item">
      <div class="faq-question">Q : Comment commencer un nouvel algorithme dans Flowgorithm ?</div>
      <div class="faq-answer">
        R : Ouvrez Flowgorithm, sélectionnez **Fichier > Nouveau**. Vous pouvez ensuite ajouter des symboles pour construire votre algorithme.
      </div>
    </div>
    <div class="faq-item">
      <div class="faq-question">Q : Comment exécuter un organigramme dans Flowgorithm ?</div>
      <div class="faq-answer">
        R : Cliquez sur le bouton **Exécuter** (l'icône en forme de triangle vert). Suivez les étapes dans la fenêtre qui s'ouvre pour voir votre algorithme fonctionner.
      </div>
    </div>
  </div>

  <!-- Section Arduino -->
  <div class="faq-section arduino">
    <h2>Arduino</h2>
    <div class="faq-item">
      <div class="faq-question">Q : Quels composants sont nécessaires pour commencer avec Arduino ?</div>
      <div class="faq-answer">
        R : Un kit de base Arduino (incluant une carte Arduino Uno, des câbles, résistances, LED et une breadboard) est recommandé pour débuter.
      </div>
    </div>
    <div class="faq-item">
      <div class="faq-question">Q : Comment uploader un code sur ma carte Arduino ?</div>
      <div class="faq-answer">
        R : Connectez votre carte Arduino à votre ordinateur avec un câble USB, puis cliquez sur le bouton **Téléverser** dans l'IDE Arduino.
      </div>
    </div>
  </div>

  <!-- Section Python -->
  <div class="faq-section python">
    <h2>Python</h2>
    <div class="faq-item">
      <div class="faq-question">Q : Comment installer une bibliothèque Python avec pip ?</div>
      <div class="faq-answer">
        R : Ouvrez un terminal ou une console et tapez `pip install nom_de_la_bibliotheque`. Par exemple, `pip install numpy`.
      </div>
    </div>
    <div class="faq-item">
      <div class="faq-question">Q : Que faire si j’ai une erreur “Module not found” en Python ?</div>
      <div class="faq-answer">
        R : Cela signifie que la bibliothèque n’est pas installée. Utilisez la commande `pip install nom_du_module` pour l’installer.
      </div>
    </div>
  </div>
</div>

<script>
document.addEventListener("DOMContentLoaded", function () {
  const questions = document.querySelectorAll(".faq-question");

  questions.forEach((question) => {
    question.addEventListener("click", function () {
      const answer = this.nextElementSibling;

      // Fermer toutes les autres réponses ouvertes
      document.querySelectorAll(".faq-answer.active").forEach((openAnswer) => {
        if (openAnswer !== answer) {
          openAnswer.classList.remove("active");
        }
      });

      // Bascule la réponse correspondante
      answer.classList.toggle("active");
    });
  });
});
</script>
