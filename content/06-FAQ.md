---
section_id: FAQ
nav_order: 6
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
      <div class="faq-question">Q : Comment copier une formule sans modifier les références de cellule ?</div>
      <div class="faq-answer">
        R : Ajoutez des signes dollar ($) dans la référence de cellule pour la rendre absolue, par exemple : $A$1. Ainsi, la référence reste fixe lors de la copie.
      </div>
    </div>
    <div class="faq-item">
      <div class="faq-question">Q : Comment ajouter un graphique dans Excel ?</div>
      <div class="faq-answer">
        R : Sélectionnez vos données, allez dans l'onglet Insertion, puis choisissez le type de graphique souhaité, comme un histogramme ou un graphique en ligne.
      </div>
    </div>
  </div>

  <!-- Section Flowgorithm -->
  <div class="faq-section flowgorithm">
    <h2>Flowgorithm</h2>
    <div class="faq-item">
      <div class="faq-question">Q : Comment enregistrer un organigramme ?</div>
      <div class="faq-answer">
        R : Allez dans le menu Fichier, puis cliquez sur Enregistrer ou Enregistrer sous pour sauvegarder votre organigramme au format .fprg.
      </div>
    </div>
    <div class="faq-item">
      <div class="faq-question">Q : Puis-je exporter un organigramme en PDF ?</div>
      <div class="faq-answer">
        R : Oui, utilisez l'option Exporter comme PDF dans le menu Fichier pour générer une version imprimable de votre organigramme.
      </div>
    </div>
  </div>

  <!-- Section Arduino -->
  <div class="faq-section arduino">
    <h2>Arduino</h2>
    <div class="faq-item">
      <div class="faq-question">Q : Comment vérifier si mon code Arduino contient des erreurs ?</div>
      <div class="faq-answer">
        R : Dans l'IDE Arduino, cliquez sur le bouton Vérifier (icône en forme de coche) pour compiler votre code et détecter d'éventuelles erreurs.
      </div>
    </div>
    <div class="faq-item">
      <div class="faq-question">Q : Comment utiliser un capteur de température avec Arduino ?</div>
      <div class="faq-answer">
        R : Connectez le capteur à la carte Arduino selon le schéma indiqué dans la documentation, puis utilisez une bibliothèque comme DHT pour lire les données.
      </div>
    </div>
  </div>

  <!-- Section Python -->
  <div class="faq-section python">
    <h2>Python</h2>
    <div class="faq-item">
      <div class="faq-question">Q : Comment lire un fichier texte en Python ?</div>
      <div class="faq-answer">
        R : Utilisez la fonction open pour ouvrir le fichier et la méthode read pour lire son contenu, comme suit : <code>with open('fichier.txt') as f: contenu = f.read()</code>.
      </div>
    </div>
    <div class="faq-item">
      <div class="faq-question">Q : Quelle est la différence entre une liste et un tuple en Python ?</div>
      <div class="faq-answer">
        R : Les listes sont modifiables (mutables), alors que les tuples ne le sont pas (immutables). Les tuples sont aussi légèrement plus rapides à utiliser.
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
