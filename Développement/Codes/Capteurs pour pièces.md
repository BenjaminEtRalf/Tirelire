# Code Capteurs pour les pièces

<p> Ce code permet de définir tous les capteurs associés a chaqu'une des 8 pièces. Lorsqu'une pièce tombe dans le trou qui lui correspond, le capteur correspondant la detecte. Le compteur totale de la tirelire est donc incrémenté de la valeur de la pièce en question.  </p>

## Voici le code commenté :


    #include <Wire.h> 

    int detection1 = LOW; // Initialisation des états des 8 capteurs à LOW
    int detection2 = LOW;
    int detection3 = LOW;
    int detection4 = LOW;
    int detection5 = LOW;
    int detection6 = LOW;
    int detection7 = LOW;
    int detection8 = LOW;

    int etatprecedent1 = LOW; // initialisation des états précédents des 8 capteurset du bouton à LOW
    int etatprecedent2 = LOW;
    int etatprecedent3 = LOW;
    int etatprecedent4 = LOW;
    int etatprecedent5 = LOW;
    int etatprecedent6 = LOW;
    int etatprecedent7 = LOW;
    int etatprecedent8 = LOW;

    const int capteur1=9; //Capteur pour pièce de 1 centime.
    const int capteur2=2; //Capteur pour pièce de 2 centimes.
    const int capteur3=3; //Capteur pour pièce de 5 centimes.
    const int capteur4=4; //Capteur pour pièce de 10 centimes.
    const int capteur5=5; //Capteur pour pièce de 20 centimes.
    const int capteur6=6; //Capteur pour pièce de 50 centimes.
    const int capteur7=7; //Capteur pour pièce de 1 euro.
    const int capteur8=8; //Capteur pour pièce de 2 euros.

    const int capteur_principal=11; //Capteur principal

    float tot; //Initialisation de la valeur totale mise dans la tirelire

    void setup() {

      pinMode(capteur1, INPUT); // Les capteurs et le bouton sont définis en entrée
      pinMode(capteur2, INPUT);
      pinMode(capteur3, INPUT);
      pinMode(capteur4, INPUT);
      pinMode(capteur5, INPUT);
      pinMode(capteur6, INPUT);
      pinMode(capteur7, INPUT);
      pinMode(capteur8, INPUT);

      tot = 0; // Le total est initialisé à 0
    }


    void loop() {

      etatprecedent1 = detection1; // valeur précédente de l'interface OUT (état) du capteur 1
      etatprecedent2 = detection2; // valeur précédente de l'interface OUT (état) du capteur 2
      etatprecedent3 = detection3; // valeur précédente de l'interface OUT (état) du capteur 3
      etatprecedent4 = detection4; // valeur précédente de l'interface OUT (état) du capteur 4
      etatprecedent5 = detection5; // valeur précédente de l'interface OUT (état) du capteur 5
      etatprecedent6 = detection6; // valeur précédente de l'interface OUT (état) du capteur 6
      etatprecedent7 = detection7; // valeur précédente de l'interface OUT (état) du capteur 7
      etatprecedent8 = detection8; // valeur précédente de l'interface OUT (état) du capteur 8

      detection1 = digitalRead(capteur1); // Lecture de la valeur de l'interface OUT (état) du capteur 1
      detection2 = digitalRead(capteur2); // Lecture de la valeur de l'interface OUT (état) du capteur 2
      detection3 = digitalRead(capteur3); // Lecture de la valeur de l'interface OUT (état) du capteur 3
      detection4 = digitalRead(capteur4); // Lecture de la valeur de l'interface OUT (état) du capteur 4
      detection5 = digitalRead(capteur5); // Lecture de la valeur de l'interface OUT (état) du capteur 5
      detection6 = digitalRead(capteur6); // Lecture de la valeur de l'interface OUT (état) du capteur 6
      detection7 = digitalRead(capteur7); // Lecture de la valeur de l'interface OUT (état) du capteur 7
      detection8 = digitalRead(capteur8); // Lecture de la valeur de l'interface OUT (état) du capteur 8


      //////////////////////////////// Détection 1 centime ////////////////////////////////

      if (detection1 == LOW && detection1 != etatprecedent1) { // on vérifie pour chaque capteur que son état est différent de son état précédent.
        tot = tot + 0.01;
      }

      //////////////////////////////// Détection 2 centime ////////////////////////////////

      if (detection2 == LOW && detection2 != etatprecedent2) {
        tot = tot + 0.02;
      }

      //////////////////////////////// Détection 5 centime ////////////////////////////////

      if (detection3 == LOW && detection3 != etatprecedent3) {
        tot = tot + 0.05;
      }

      //////////////////////////////// Détection 10 centime ////////////////////////////////

      if (detection4 == LOW && detection4 != etatprecedent4) {
        tot = tot + 0.10;
      }

      //////////////////////////////// Détection 20 centime ////////////////////////////////

      if (detection5 == LOW && detection5 != etatprecedent5) {
        tot = tot + 0.20;
      }

      //////////////////////////////// Détection 50 centime ////////////////////////////////

      if (detection6 == LOW && detection6 != etatprecedent6) {
        tot = tot + 0.50;
      }

      //////////////////////////////// Détection 1 euro ////////////////////////////////

      if (detection7 == LOW && detection7 != etatprecedent7) {
        tot = tot + 1.00;
      }

      //////////////////////////////// Détection 2 euro ////////////////////////////////

      if (detection8 == LOW && detection8 != etatprecedent8) {
        tot = tot + 2.00;
      }

    }
