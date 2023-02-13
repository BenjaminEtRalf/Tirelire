# -- Rapport de séance Benjamin Guillaumat - Séance 5 -- #

## 1 : Code des capteurs de pièces + essaie des branchements

J'ai terminé le code pour les 8 capteurs des 8 pièces. Les pièces glissent sur la glissière et tombent dans le trou correspondant à leur valeur. Juste en dessous de chaque trou se trouve un capteur spécifique à chaque trou permettant de détecter l'arrivé d'une pièce. Le capteur capte la pièce à courte distance. Le code différencie les différents capteurs et en fonction de celui qui s'active, incrémente au compteur totale la valeur de la pièce correspondante. Par exemple, le capteur numéro 3 est celui associé à la pièce de 5 centime. Lorsque qu'une pièce de 5 centimes tombe dans le trou correspondant, le capteur la capte et incrémente le total de 0.05 (0.05 euro ou 5 centimes).

Voici le code correspondant : <a href="../../Développement/Codes/Capteurs pour pièces.md"> Voir le code entier avec tous les détails </a>.



## 2 : Code de l'option de réinitialisation à l'aide d'un bouton

J'ai rajouté au code des capteurs la possibilité de réinitialiser le compteur de monnaie à l'aide d'un bouton. Il suffit de cliquer une fois dessus.
Voici la partie du code :

    const int bouton=13; 
    int val = 1;

    float tot; //Initialisation de la valeur totale mise dans la tirelire

    int etatprecedent_bouton = LOW; // initialisation de l'état précédent du bouton à LOW

    void setup() {
      pinMode(bouton,INPUT);
      tot = 0; // Le total est initialisé à 0

    }

    void loop() {
      etatprecedent_bouton = val; // valeur précédente de l'interface OUT (état) du bouton
      val = digitalRead(bouton); // Lecture de la valeur de l'interface OUT (état) du bouton


      //////////////////////////////// Réinitialisation du compteur de la tirelire avec un bouton ////////////////////////////////

      if (val == LOW && val != etatprecedent_bouton) {
        tot = 0.00;
      }

      if (val == HIGH && val != etatprecedent_bouton) {
        tot = 0.00;
      }

    }

