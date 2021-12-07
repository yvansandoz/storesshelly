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
Le challenge va consister à trouver de la place dans le boîtier de vos interrupteurs pour placer les modules Shelly 2.5. Je ne vais pas m’étendre sur les options à disposition ; dans mon cas le boîtier encastrable existant était suffisamment profond pour pouvoir ajouter les modules à plat sur l’arrière des interrupteurs. Avec un câblage organisé et compact, j’ai réussi à tout caser sans devoir agrandir l’espace.

En termes de câblage, il faut brancher les modules Shelly 2.5 entre vos interrupteurs mécaniques existants et vos moteurs des stores. Le schéma d’Aurélien est très explicatif et résume l’ensemble des connexions à faire. 

Attention de bien couper le courant avant de faire les branchements.

<img src="https://github.com/yvansandoz/storesshelly/blob/main/pictures/shelly-2-volets-roulants-roller-shutter-wifi.jpg" alt="Shelly 2.5"
	title="Schéma de branchement" width="600" height="400" />


## Situation de départ
Sur le bas on voit les 4 interrupteurs à 2 boutons mécaniques (montée/descente) pour activer 4 stores séparés.

<img src="https://github.com/yvansandoz/storesshelly/blob/main/pictures/montage1.jpg" alt="Situation de départ"
	title="Situation de départ" width="400" height="600" />


## Câblage des 4 modules
Sachant que j’allais pouvoir mettre les modules sur l’arrière des interrupteurs, j’ai défini la position de chacun d’eux et leur ai attribué une position définie.

**Note:** Libre à vous de faire le montage et de configurer les modules ensuite. Dans le cas présent, j’ai numéroté les modules et je les ai configurés avant le montage en les alimentant tel que décrit dans la procédure de configuration dans le chapitre suivant.

<img src="https://github.com/yvansandoz/storesshelly/blob/main/pictures/montage2.jpg" alt="Câblage initial"
	title="Câblage initial" width="600" height="400" />

Comme on le voit sur le schéma de branchement, il faut alimenter les modules Shelly 2.5 sur les bornes L, L et N, ce qui en soit fait déjà pas mal de câbles. Je choisi l’option des bornes Wago Compact à 5 conducteurs pour optimiser le câblage au maximum et réduire l’espace utiliser.

<img src="https://github.com/yvansandoz/storesshelly/blob/main/pictures/montage3.jpg" alt="Optimisation du câblage"
	title="Optimisation du câblage" width="600" height="400" />

Reste ensuite à placer l’ensemble et finaliser le câblage, toujours sur la base du schéma.

<img src="https://github.com/yvansandoz/storesshelly/blob/main/pictures/montage4.jpg" alt="Branchements"
	title="Branchements" width="400" height="600" />


## Résultat final
<img src="https://github.com/yvansandoz/storesshelly/blob/main/pictures/montage5.jpg" alt="Résultat final"
	title="Résultat final" width="400" height="700" />







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




