# Code Écran

<p> Ce code permet l'affichage en temps réel de la valeur des pièces insérées dans la tirelire. Si une pièce est ajouté, l'affichage s'actualise en temps réel et de même si on clique sur le bouton de réinitialisation du compteur. </p>

## Voici le code commenté :

    #include <Wire.h> 
    #include <LiquidCrystal_I2C.h>

    LiquidCrystal_I2C lcd(0x27,20,4);  // On défini la taille et le nombre de pixel de notre écran LCD

    float tot; //Initialisation de la valeur totale mise dans la tirelire

    void setup() {

      lcd.init();   // Initialisation de l'écran LCD
      lcd.backlight();

      tot = 0; // Le total est initialisé à 0

    }

    void loop() {
        //////////////////////////////// Écran LCD qui affiche le montant de la tirelire ////////////////////////////////


      lcd.setCursor(2,0); // On place le cursor sur l'écran lcd
      lcd.print(tot);

      if (tot<2) {
        lcd.setCursor(9,0);
        lcd.print("euro"); }

      else { 
        lcd.setCursor(9,0);
        lcd.print("euros"); }

    }
