# Stores avec modules Shelly 2.5
## Mais c'est si simple!

Automatisation de stores avec modules Shelly 2.5 sur Home Assistant

La configuration de mes stores se base sur le travail déjà effectué par Aurélien Brunet sur le site [Domo Blog](https://www.domo-blog.fr):

[Shelly 2.5 : Comment installer le module domotique wifi et piloter des volets roulants avec Jeedom](https://www.domo-blog.fr/shelly-2-5-comment-installer-le-module-domotique-wifi-volets-roulants-jeedom/)

# Table des matières

1. [Construction](#Construction)
2. [Configuration](#Configuration)
3. [Intégration](#Intégration)

# Construction
Il n'y pour ainsi dire rien à construire, il faut juste brancher les modules Shelly 2.5 entre vos interrupteurs mécaniques existants et vos moteurs des stores. Le schéma d'Aurélien est très explicatif et résume l'ensemble des connexions à faire. Le challenge réside à trouver la place pour les modules Shelly et à bien couper le courant avant de faire les branchements.

<img src="https://github.com/yvansandoz/storesshelly/blob/main/pictures/shelly-2-volets-roulants-roller-shutter-wifi.jpg" alt="Shelly 2.5"
	title="Schéma de branchement" width="600" height="400" />


# Configuration

Aurélien décrit la procédure de connexion à travers l'application Shelly Cloud sur smartphone. Je préfére passer par l'option de la connexion par un browser, ce qui évite aussi de passer par le cloud de Shelly.

Cette procédure nécessite de connecter les modules Shelly les uns après les autres afin de pouvoir les indentifier.

1. Brancher le module Shelly tel que décris dans le schéma de branchment ci-dessus. A ce stade seul les bornes L, L et N sont nécessaires pour alimenter le module.
2. Une fois sous tension le module créer un réseau wifi (shellyswitch25-xxxxxxxx).
3. Connectez-vous à ce réseau wifi depuis votre ordinateur.
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

## Calibration

Il y a une fonction "Calibration" dans le menu de configuration. Cette calibration permet de mémoriser les positons ouvertes, fermées et intermédiaires de vos stores. Grâce à cette calibration, vous pourrez aussi commander la position précise de vos stores depuis Home Assistant 


# Intégration

Une fois configuré, chaque nouveau module est découvert automatiquement dans Home Assistant, il suffi de cliquer sur "Configure" dans les intégrations pour changer son nom et lui affecter une pièce dans la maison.

Le tour est joué, vous pouvez vous lancer maintenant dans l'automatisation de vos stores.




