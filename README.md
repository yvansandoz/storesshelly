# Stores avec modules Shelly 2.5 (en construction)

Automatisation de stores avec modules Shelly 2.5 sur Home Assistant

La configuration de mes stores se base sur le travail déjà effectué par Aurélien Brunet sur le site [Domo Blog](https://www.domo-blog.fr):

[Shelly 2.5 : Comment installer le module domotique wifi et piloter des volets roulants avec Jeedom](https://www.domo-blog.fr/shelly-2-5-comment-installer-le-module-domotique-wifi-volets-roulants-jeedom/)

# Table des matières

1. [Construction](#Construction)
2. [Configuration](#Configuration)
3. [Intégration](#Intégration)

# Configuration des modules Shelly 2.5

Aurélien décrit la procédure de connexion à travers l'application Shelly Cloud sur smartphon. Je préfére dans mon cas passer par l'option de la connexion par un browser, ce qui évite aussi de passer par le cloud de Shelly.

Cette procédure nécessite de connecter les modules Shelly les uns après les autres afin de pouvoir les indentifier.

1. Brancher le module Shelly tel que décris dans le schéma de branchment. A ce stade seul les bornes L, L et N sont nécessaires.
2. Une fois sous tension le module créer un réseau wifi (shellyswitch25-xxxxxxxx).
3. Connectez-vous à ce wifi depuis votre ordinateur.
4. Sur un browser, joindre l'adresse [http://192.168.33.1](http://192.168.33.1)
5.  Configurer l'accès wifi du module avec une adresse IP fixe ou pas dans "Internet & Security / Wifi Mode-Client". 
6.  Reconnectez-vous au module avec la nouvelle adresse IP (ça aide si vous avez défini une adresse IP Fixe, sinon, il faut la trouver sur votre routeur).
7.  Faire l'udpate du module dans "Settings / Firmware Update".
8.  Une fois l'update terminé, revenez sur la page de configuration du module et changez les paramètres suivants:
 - Device Type: Roller Shutter
 - Power ON Parameters: STOP - Configure Shelly roller to STOP when it has power.
 - Button Type: Momentary
 - Device Name: Soyez logique si vous avec plusieurs modules...
 - LED Light Control: J'ai choisi de désactiver la LED

Calibration

Il y a une fonction "Calibration" dans le menu de configuration. Cette calibration permet de mémoriser les positons ouvertes, fermées et intermédiaires de vos stores.


# Intégration dans Home Assistant

Une fois configuré, chaque nouveau module est découvert automatiquement dans Home Assistant, il suffi de cliquer sur "Configure" dans les intégrations pour lui affecter une pièce dans la maison et le tout est jouer.




