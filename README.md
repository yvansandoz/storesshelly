# Stores avec modules Shelly 2.5 (en construction)

Automatisation de stores avec modules Shelly 2.5 sur Home Assistant

La configuration de mes stores se base sur le travail déjà effectué par Aurélien Brunet sur le site [Domo Blog](https://www.domo-blog.fr):

[Shelly 2.5 : Comment installer le module domotique wifi et piloter des volets roulants avec Jeedom](https://www.domo-blog.fr/shelly-2-5-comment-installer-le-module-domotique-wifi-volets-roulants-jeedom/)

# Table des matières

1. [Construction](#Construction)
2. [Configuration](#Configuration)
3. [Intégration](#Intégration)

# Configuration des modules Shelly 2.5





# Construction

## Matériel

Les options choisies pour les émetteur/récepteur sont :

- Émetteur : STX822
- Récepteur : SRX822

<img src="https://github.com/yvansandoz/OpenMQTT-RF-HA/blob/4fbbad7d5b96a7a5aa151c5fdb4944f830195c67/pictures/stx_srx_822.JPG" alt="822"
	title="STX822/RTX822" width="100" height="100" />



Il existe des kits avec le STX822 et le SRX822 sur Banggood et sur Aliexpress. Bastelgarage.ch offre aussi des composants similaires à un prix très attractif.

### Commentaire

Avec le



| Composants       | Connexions |&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;&nbsp; &nbsp;|&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;&nbsp; &nbsp;|&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;&nbsp; &nbsp;|
| ---------------- | ---------- | ---- | ---- | ---- |
| Wemos D1 mini    | 5V         | G    | D1   | D2   |
| SRX822           | VCC        | GND  | CS   |      |
| STX822           | VCC        | GND  |      | DATA |



# Configuration

L'option 3 du mode de configuration est choisie, avec l'aide du logiciel Arduino IDE, c'est l'option qui offre la plus grande flexibilité de configuration.

Les 2 fichiers (User_config.h et config_RF.h) dont la modification est décrite ci-dessous sont disponibles déjà modifiés dans le dossier ["main"](https://github.com/yvansandoz/OpenMQTT-RF-HA/tree/main/main) de ce projet.

## Programmation de l'ESP

1. Assurez-vous d'avoir la dernière version de Arduino IDE avec la libraire ESP8266 (ou ESP32 en fonction de l'ESP choisi) ([tutoriel](https://github.com/esp8266/Arduino#installing-with-boards-manager)).
2. Télécharger la librairie spécifique à ce projet (RF avec Wemos D1 mini): [nodemcuv2-rf-librairies.zip](https://github.com/1technophile/OpenMQTTGateway/releases/download/v0.9.8/nodemcuv2-rf-libraries.zip) (Vous trouvez ici le lien pour la liste de toutes les autres librairies au cas où vous souhaitez partir sur d'autres composants ou pour créer un autre type de passerelle : [lien](https://github.com/1technophile/OpenMQTTGateway/releases))



## xxx

xxx

# xxx

xxx


