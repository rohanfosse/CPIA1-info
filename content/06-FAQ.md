---
section_id: Pour aller plus loin
nav_order: 6
title: Foire Aux Questions
topics: FAQ; Questions; Réponses
---

<style>
/* Style de la section FAQ */
.faq-container {
  max-width: 800px;
  margin: 0 auto;
  padding: 20px;
  font-family: 'Roboto', sans-serif;
}

.faq-title {
  font-size: 32px;
  color: #2a9df4;
  text-align: center;
  margin-bottom: 20px;
}

.faq-item {
  margin-bottom: 15px;
  border-radius: 8px;
  background: #f9f9f9;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  overflow: hidden;
  transition: all 0.3s ease;
}

.faq-item:hover {
  box-shadow: 0 6px 12px rgba(0, 0, 0, 0.15);
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

  <div class="faq-item">
    <div class="faq-question">Q : Comment installer Python sur mon ordinateur ?</div>
    <div class="faq-answer">
      R : Téléchargez Python depuis le <a href="https://www.python.org/">site officiel</a>. Pendant l’installation, cochez l’option "Add Python to PATH".
    </div>
  </div>

  <div class="faq-item">
    <div class="faq-question">Q : Qu'est-ce que Flowgorithm ?</div>
    <div class="faq-answer">
      R : Flowgorithm est un outil de création de diagrammes pour apprendre à programmer. Il permet de concevoir et d’exécuter visuellement des algorithmes.
    </div>
  </div>

  <div class="faq-item">
    <div class="faq-question">Q : Comment connecter un Arduino à mon ordinateur ?</div>
    <div class="faq-answer">
      R : Utilisez un câble USB fourni avec la carte Arduino. Ouvrez l’IDE Arduino et sélectionnez le port COM dans "Outils > Port".
    </div>
  </div>

  <div class="faq-item">
    <div class="faq-question">Q : Pourquoi mon code ne fonctionne-t-il pas en Python ?</div>
    <div class="faq-answer">
      R : Vérifiez attentivement le message d’erreur dans la console. Il indique généralement l'endroit exact du problème. Assurez-vous que la syntaxe est correcte.
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
