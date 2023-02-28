# Rapport de Projet - SmartPiggyBank - La tirelire intelligente #
<p> Benjamin Guillaumat - Ralph Mansour </p>

—------------------------------------------------------------------------
1) Il doit faire au grand maximum 10 pages (donc 5 feuilles) tout compris, mais 5 pages devraient suffire. Il devra être mis sur votre Github au plus tard à 22h une semaine après votre oral (-1pt/10 par minute de retard)

2) Le rapport final est une synthèse de votre projet, il doit pouvoir servir de notice d’utilisation. DONC : ce n'est pas un copié/collé des rapports de séance.

—------------------------------------------------------------------------


## 1 - introduction : objectif (cahier des charges): ## // Benji



## 2 - Schéma électrique du projet. ## // Benji

<img src="Images/schema_projet_tirelire_1.png" alt="schema_projet_tirelire" height="500"/>

<p> Dans un premier temps, la carte arduino alimente en 5V et relie la masse à la platine de cablage. Ensuite, chaque capteur est relié en alimentation, à la masse et sur leurs sorties respectives. De même pour le bouton et le moteur. Quand à l'écran LCD, il est aussi alimenté et relié à la masse et est relié par deux autre cables. L'un relie le port SDA à la sortie A4 et l'autre relie le port SCL à la sortie A5 de la carte Arduino. </p>

## 3 - Algorithme de fonctionnement : on doit pouvoir comprendre le fonctionnement global du projet ## //Ralph



## 4 - Le coût du projet : matériel (estimation en utilisant amazon par exemple) + coût ingénieur en partant (pour faire simple) d’un salaire brut annuel de 38 keuros pour 1600h de travail. Il faudra estimer le temps que vous avez passé en cours + en dehors des cours. ## //Ralph



## 5 - Les plannings (initial et final) et commenter les différences ## //Benji



## 6 -  S’il y a eu des problèmes dire comment vous les avez surmonté ## // Benji

Voici les problèmes que nous avons rencontrés ainsi que les solutions pour y remédier :

Les problèmes rencontrés :

- 1) Lors de l'instalation pour essayer nos capteurs de pièces, nous nous sommes apercus qu'ils captés en permanence quelque chose, qu'il y est un obstacle ou non devant.

- 2) Difficulté pour faire apparaitre un message sur l'écran.

- 3) Lors des tests de la glissière, les pièces ne glissaient pas totalement sur celle-ci. Les pièces accrochaient légérement ce qui empéchait le bon fonctionnement de la glissière.

-4) Après fixation de la glissière terminé dans la tirelire, certaines pièce comme celle de 20 centimes et celle de 1 euro notemment, ne tombaient plus dans leurs trou respectifs.
Malgrès un précision de mesure au dixième de millimètre près, certaines pièces avaient du mal à tomber dans leurs trou car elles restaient légérement bloqué.

Les solutions pour y remédier :

- 1) Chaque capteur est équipé d'un petit module de réglage. En tournant le module, cela augmente ou diminue la sensibilité et la portée du capteur. 
Pour remédier au problème, il a fallu dans un premier temps modifier correctement ce réglage en fonction de la distance entre le capteur et la paroi la plus proche.
De plus, les parois intérieurs du coffrage étant de couleur clair (couleur du bois) les reflets sur les paroi sont conséquents. 
Nous avons donc peint les parois intérieur intégralement en noir pour que les capteurs détectent uniquement les pièces et aucun autre élément.

- 2) Le problème que l'on avait avec l'écran provenait de deux choses. L'une était un problème d'importation du module <liquidCrystal_I2C> permettant de faire le code associé à l'écran.
Plusieurs module de ce type existe et tous sont très similaires. Il a donc fallu en essayer plusieurs afin de trouver celui qui nous convenait.
L'autre était un problème de contraste de l'écran. Nous l'avons découvert tardivement mais un module de réglage du contraste de l'écran ce situe à l'arrière de l'écran. Le notre
étant par défaut trop contrasté, nous ne pouvions pas voir le texte afficher sur celui-ci. Un simple réglage à réglé le problème.

- 3) Pour remédier à ce problème, nous avons rajouter une matière plastifiée, glissante et autocollante avec laquelle nous avons recouvert la glissière. De plus, nous avons graissé
légérement la glissière afin d'assurer le bon fonctionnement de celle-ci.

- 4) Ce problème est du à l'instalation de la glissière. Une fois installé, la glissière n'est pas fixé perpendiculairement aux parois de la tirelire ni parrallèlement au sol.
Dans un premier temps, elle est penché d'un certain degrès permettant aux pièces de glisser dessus. De plus, elle est légérement incliner sur sa largeur (elle penche légérement sur
la paroi de la tirelire). Sans les pièces bien collées à la paroi, notre système ne fonctionnerai pas. Or, lors de la conception de la glissière, nous n'avons pas pris en compte
dans les mesures des trous le fait que la glissère est légérement penché ainsi. Cela à donc faussé de quelque dixième de millimètre les mesures. Certaines pièces se retrouvé donc
avec une diamètre de trou très légérement inférieur à la normal ce qui les empéchaient de tomber.
  

## 7 - Conclusion-perspective : il faudra rappeler ce qui a été fait, ce qui marche, ce qui ne marche pas et qu’est-ce qu’il faudrait faire par la suite si je vous donne encore 9 séances ## //Ralph



## 8 - Bibliographie : mettre les liens des sites qui vous ont aidé à développer votre projet ##


