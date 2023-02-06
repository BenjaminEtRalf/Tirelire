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
