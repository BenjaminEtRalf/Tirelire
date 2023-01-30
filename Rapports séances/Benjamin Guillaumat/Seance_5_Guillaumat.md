# -- Rapport de séance Benjamin Guillaumat - Séance 5 -- #

## 1 : Code des capteurs de pièces + essaie des branchements

J'ai terminé le code pour les 8 capteurs des 8 pièces. Les pièces glissent sur la glissière et tombent dans le trou correspondant à leur valeur. Juste en dessous de chaque trou se trouve un capteur spécifique à chaque trou permettant de détecter l'arrivé d'une pièce. Le capteur capte la pièce à courte distance. Le code différencie les différents capteurs et en fonction de celui qui s'active, incrémente au compteur totale la valeur de la pièce correspondante. Par exemple, le capteur numéro 3 est celui associé à la pièce de 5 centime. Lorsque qu'une pièce de 5 centimes tombe dans le trou correspondant, le capteur la capte et incrémente le total de 0.05 (0.05 euro ou 5 centimes).

Voici le code correspondant : <a href="../../Développement/Codes/Capteurs pour pièces.md"> lien vers le fichier correspond à ce code </a>.



## 2 : Code de l'option de réinitialisation à l'aide d'un bouton



