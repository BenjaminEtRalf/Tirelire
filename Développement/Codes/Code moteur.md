    #include <Servo.h> // on inclut la bibliothèque servo

    Servo servoMoteur; // on crée un objet servo appelé servoMoteur

    int val = 1;

    int detection_principal = LOW; // Initialisation de l'état du capteur principal
    int etatprecedent_principal = LOW; // initialisation de l'état précédent du capteur pricipal
    const int capteur_principal=11; //Capteur principal

    void setup() {
      // put your setup code here, to run once:
      pinMode(capteur_principal, INPUT);
  
      servoMoteur.attach(12); // on associe le servo à la broche 12 d'Arduino
      servoMoteur.write(0); // On met le moteur en position 0 degrès

    }

    void loop() {

        etatprecedent_principal = detection_principal; // valeur précédente de l'interface OUT (état) du capteur 8

        detection_principal = digitalRead(capteur_principal); // Lecture de la valeur de l'interface OUT (état) du capteur principal

        if (detection_principal == LOW && val != etatprecedent_principal) {
        int n = 0;
    
        while (n < 5) {
      
          for (int i = 0; i <= 100; i++) {  // boucle pour faire tourner le servo de 0 à 180 degrés
            servoMoteur.write(i);  // écriture de la position actuelle du servo
            delay(8);
          }

          for (int i = 100; i >= 0; i--) {  // boucle pour faire tourner le servo de 180 à 0 degrés
            servoMoteur.write(i);  // écriture de la position actuelle du servo
            delay(8);
          }

          n = n+1;


        }
        n = 0;  
      }
    }
