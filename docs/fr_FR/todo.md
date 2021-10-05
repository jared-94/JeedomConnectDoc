Pugin et à l'application JeedomConnect

Les items présents ici correspondent à l'ensemble des points pris en compte en tant qu'évolution et/ou correction.  
La dernière partie liste les points qui n'ont pas été retenus.  

# Plateforme
    - créer une version pour IOS  --> beta déjà disponible (04/08/21) // stable en cours de validation par Apple - date inconnue

# Widgets à créer  
	- multimédia
	- porte de garage (https://community.jeedom.com/t/widgets-porte-de-garage/52963)
	- VMC
	- Serrure
	- Vanne thermostatique
	- Velux

# Options supplémentaires
	- remplir automatiquement les zones en fonction d'une premiere sélection lors de la création d'un widget (Statut -> ON + OFF)
	- retour d'informations de l'appareil (batterie, statut écran, connexion...) vers Jeedom
	- envoyer des actions vers l'appareil (allumer écran, couper bluetooth...)
	- widgets Android sur launcher
	- programmer une action sur un widget (ex: baisse de 2°C dans une heure)
	- préviens moi sur un widget (ex: envoie une notification si temperature > 24°C)
	
# Options sur APK
	- définir la taille d'une vignette (https://community.jeedom.com/t/ergonomie-appli/55798)
	- pouvoir définir carte/vignette par page et non pas au global
	

# Bugs connus
	- problème de rafraichissement des conf (liste) avec le daemon !?  


<br/><br/>
---
---
<br/><br/>

# Déjà mis en place

Plateforme :  

	- mettre les apk disponible sur le Play Store (17/03/21)

Nouveaux widgets :  

	- liste de choix (23/03/21)
	- générique message (23/03/21)
	- caméra (01/04/21)  
	- lancer une application (10/05/21)
	

Petis plus :  

	- ajouter une option "code", en plus de l'action de confirmation ou de l'empreinte (23/03/21)
	- ajouter une option "pour gaucher" sur l'apk, permettant d'inverser l'affichage des actions (à gauche plutôt qu'à droite) (23/03/21)
	- trop plein d'actions : ajouter un retour chariot pour ne pas avoir d'ascenceur (23/03/21)
	- widget fenêtre - Status accepte les valeurs numériques maitenant (en + de binaire) (23/03/21)
	- toutes les actions d'un `générique action` sont affichées en mode carte (23/03/21)
	- avoir la possibilité de customiser les icônes 'Résumé' (01/04/2021)
	- ajouter des tags au lancement d'un scénario (01/04/2021)
	- option mode sombre sur les map (01/04/2021) 
	- effacer les notifications android lorsque l'on supprime les notifs dans l'application (https://community.jeedom.com/t/effacement-des-notifications/53269) (16/04/21)
	- sur l'apk, accès à une pièce via un widget : pas de possibilité d'afficher carte/vignette (16/04/21)
	- permettre de réaliser une action lorsqu'on affiche un menu bas (16/04/21)
	- définir le pas d'un slider  (16/04/21)
	- ajouter bouton + et - aux extrémités d'un slider (https://community.jeedom.com/t/widget-thermostat-jeedom-connect/54694) (16/04/21)
	- permettre le clic sur une vignette pour réaliser l'action (allumer/éteindre une lumière, ..)  (16/04/21)
	- Unité sur les infos supplémentaires (16/04/21)
	- alarme avec plusieurs mode (https://community.jeedom.com/t/alarme-jeedom-connect/53849) (05/09/21)  
	- pouvoir gérer la température de blanc (https://community.jeedom.com/t/widget-lampe-rgbw/49901)   (05/03/21)  
	- commandes pour aller à une page donnée de l'application (10/05/21)  
	- ajout de l’altitude, type d’activité (pas SSID et pcBatterie) dans les info dispo du tracking Geoloc (05/09/21)  
	- pouvoir inverser l'icône et le texte (info) sur les vignettes (18/05/21)
	- choisir comment ouvrir l'historique par défaut : table ou graph (https://community.jeedom.com/t/historique-ouvrant-en-table-par-defaut/55629)  (16/09/21)  
	

Correction bugs : 
	- le menu haut ne s'affiche pas en entier  (-> corrigé avec la nouvelle lib?)  (16/04/21)
	- l'application crash lors de l'édition des widgets  (-> affichage d'un widget "erreur") (16/04/21)


Documentation :  

	- faire un paragraphe sur les notifications (23/03/21)
	- éclaircir le paramétrage et l'utilisation des notifications (23/03/21)
	- faire un paragraphe sur "http VS websocket"

<br/><br/>

# Abandonnés
