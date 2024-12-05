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
      <div class="faq-question">Q : Où télécharger Excel et comment l’installer ?</div>
      <div class="faq-answer">
        R : Vous pouvez télécharger Excel depuis le site officiel de Microsoft ou via votre compte Office 365. Suivez les instructions d'installation après l'achat ou la connexion à votre compte.
      </div>
    </div>
    <div class="faq-item">
      <div class="faq-question">Q : Que faire si Excel ne démarre pas ou plante au lancement ?</div>
      <div class="faq-answer">
        R : Essayez de réparer l’installation via le panneau de configuration de Windows ou mettez à jour le logiciel. Assurez-vous également que votre système d’exploitation est à jour.
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
      <div class="faq-question">Q : Où télécharger Flowgorithm et comment l’installer ?</div>
      <div class="faq-answer">
        R : Flowgorithm est téléchargeable gratuitement sur le site officiel flowgorithm.org. Après le téléchargement, double-cliquez sur le fichier d’installation et suivez les instructions.
      </div>
    </div>
    <div class="faq-item">
      <div class="faq-question">Q : Pourquoi Flowgorithm ne s'ouvre pas ?</div>
      <div class="faq-answer">
        R : Assurez-vous que Java est installé sur votre système. Flowgorithm nécessite Java pour fonctionner correctement. Mettez également à jour votre système.
      </div>
    </div>
    <div class="faq-item">
      <div class="faq-question">Q : Comment exécuter un organigramme dans Flowgorithm ?</div>
      <div class="faq-answer">
        R : Cliquez sur le bouton Exécuter (l'icône en forme de triangle vert). Suivez les étapes dans la fenêtre qui s'ouvre pour voir votre algorithme fonctionner.
      </div>
    </div>
  </div>

  <!-- Section Arduino -->
  <div class="faq-section arduino">
    <h2>Arduino</h2>
    <div class="faq-item">
      <div class="faq-question">Q : Où télécharger l’IDE Arduino et comment l’installer ?</div>
      <div class="faq-answer">
        R : Téléchargez l’IDE Arduino depuis le site officiel arduino.cc. Installez-le en suivant les instructions fournies après le téléchargement.
      </div>
    </div>
    <div class="faq-item">
      <div class="faq-question">Q : Pourquoi l’IDE Arduino ne détecte-t-il pas ma carte ?</div>
      <div class="faq-answer">
        R : Assurez-vous que la carte est correctement connectée avec un câble USB fonctionnel. Vérifiez aussi que le bon port COM est sélectionné dans le menu Outils > Port.
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
      <div class="faq-question">Q : Où télécharger Python et comment l’installer ?</div>
      <div class="faq-answer">
        R : Téléchargez Python depuis le site officiel python.org. Pendant l'installation, cochez l'option Add Python to PATH pour faciliter son utilisation dans la ligne de commande.
      </div>
    </div>
    <div class="faq-item">
      <div class="faq-question">Q : Que faire si Python ne fonctionne pas après l'installation ?</div>
      <div class="faq-answer">
        R : Vérifiez que Python est ajouté au PATH. Si ce n’est pas le cas, réinstallez Python et cochez l’option Add to PATH dans l’assistant d’installation.
      </div>
    </div>
    <div class="faq-item">
      <div class="faq-question">Q : Comment lire un fichier texte en Python ?</div>
      <div class="faq-answer">
        R : Utilisez la fonction open pour ouvrir le fichier et la méthode read pour lire son contenu : with open('fichier.txt') as f: contenu = f.read().
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
