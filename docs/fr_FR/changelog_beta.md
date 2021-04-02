# Changelog JeedomConnect  

## Version 0.19.2 Beta (02/04/2021)
- Nouveautés:
  * Ajout des vidéos dans les notifications
  * Ajout d'un slider dans le player vidéo

- Bug fixes:
  * Ordre des résumés de pièces
  * Le lecteur vidéo ne plante plus lorsque le dossier d'enregistrement n'est plus spécifié
  * Correction de la commande LAN seulement (basculement auto sur snapshot)
  * Sous-titres persos sur widget camera

## Version 0.19.1 Beta (01/04/2021)
- Nouveautés:
  * Personnalisation des icones sur les résumés : nouveau menu "Résumé" à configurer dans l'assistant widget
  * Prise en compte des résumés "non-standard" (ie: ajoutés par l'utilisateur)
  * Ajout du widget ... caméra !
  * Prise en compte de tous les types `action message` dans le widget `Générique Action`
  * Prise en compte des tags dans le **widget** `Scenario`
  * Ajout de l'option "désactiver l'accélération matérielle" sur le widget Webview

- Bug fixes :
  * recherche des icônes non sensible à la casse
  * liste des widgets triées par ordre alphabétique

## Version 0.18.4 Beta (25/03/2021) [Application uniquement]
- Corrige la récupération de l'historique en http
- Thème sombre pour les cartes
- Fixe l'historique sur le widget Géolocalisation
- Correction automatique des URL jeedom dans la webview
- Fix icône thermostat
- Fix crash possible au démarrage
- Fix crash sur retour du webview
- Ajout d'une option pour masquer les historiques
- Ajout d'une option pour définir le zoom par défaut sur les historiques

## Version 0.18.3 Beta (24/03/2021)
- Nouveautés :  
  * SplashScreen qui pique pas les yeux  
  * Possibilité de sécuriser les action avec un code alphanumérique  
  * Possibilité de personnaliser le chemin des images persos (par défaut `plugins/JeedomConnect/data/img/user_files/`)  
  * Widget `liste de choix` (générique pour les commandes `action` sous-type `select`)  
  * Widget `générique message`  
  * Mode RTL (Right To Left) dans l'appli (on se refait le film à l'envers)
  * La barre de navigation Android (Retour, Accueil, Récent) s'adapte au théme sombre (si présent à l'écran)  

- Améliorations :  
  * Widget WebView :
    + accélération matérielle activée.
    + Login automatique sur les pages de Jeedom  
  * Meilleures performances sur l'Historique  
  * Lors de la suppression d'un widget, affichage du nom des équipements auxquels il est attaché
  * Widget fenêtre : Statut accepte les valeurs numériques maitenant (en + de binaire)
  * Toutes les actions d'un `générique action` sont affichées en mode carte

- Bug Fix :  
  * Correction des heures mal affichées ou avec retard d'une heure  
  * Correction des informations 'NaN' sur les titres/sous-titres
  * Alignement dans les widgets Favoris, Résumé, et dans les vignettes sans statut  
  * Interdictoin de sélectionner plusieurs fois la même pièce dans l'onglet du même nom  
  * Récupération des scénarios sur l'appli (via le menu)  


## Version 0.18.2 Beta ET Stable (18/03/2021)  
Dorénavant l'application (apk) sera disponible au téléchargement directement et uniquement sur le Store, aussi bien pour la version stable que pour la version bêta (dans ce dernier cas, un enregistrement est nécessaire -- [lire la doc](index.md#qBeta))  
- Changement du logo et du splash-screen
- Possibilité de passer en mode Vignette/Cartes sur la page des Pièces
- Accès aux notifications depuis l'icône 'Sonnerie' en haut à droite de l'écran
- Bug Fix :  
  * prise en compte de l'inversion des états pour les volets roulant

Côté plugin :
- Possibilité d'exporter & d'importer l'ensemble des widgets (sur page configuration du plugin)
- Ajout du lien d'inscription au programme bêta-testeur
- Bug Fix :  
  * importer plusieurs fois des fichiers à la suite

## Version 0.18.1 Beta (17/03/2021)  
- Bug Fix :
  * lors d'une modification d'un widget, l'application est mise à jour automatiquement
  * erreur sur le déplacement des widgets sans parent


## Version 0.18.0 Beta (15/03/2021)  
:information_source: Pré-requis (facultatif mais préférable !) : <b>AVANT</b> de mettre à jour le plugin, ouvrez l'assistant sur chacun de vos équipements, allez sur l'onglet `Pièces` et assurez vous que chacune des pièces créée est bien attachée à un objet Jeedom !  
Pensez également à mettre le plugin JeedomConnect en `DEBUG` !

:warning: Une fois la mise à jour effectuée, une migration manuelle est nécessaire pour faire fonctionner cette nouvelle version. <b>Merci de lire la [documentation](index.md#qMigration)</b> pour voir comment faire ! :warning:

- Refonte complète de la gestion des widgets :
  * création des widgets depuis la page principale du plugin
  * l'assistant disponible sur chaque équipement permet dorénavant de rattacher un widget existant à l'équipement
  * fonction de migration permettant de créer automatiquement tous les widgets d'une version précédente dans la version courante (sur la page de configuration)
  * ajout fonction de recherche sur les widgets : fonctionne sur le nom et sur l'id du widget (visible en info-bulles)

- Ajout du widget `Géolocalisation`

- Bug fix :
  * les commandes de chaque équipements sont déplaçables
  * amélioration de la performance sur la recherche des icônes (merci olivvv59)

- côté APK :
  * affichage d'un message plus précis sur la différence entre la version de plugin et celle de l'application
  * mise en place d'un pop-up pour télécharger la bonne dernière version de l'application directement


## Version 0.17.1 Beta (05/03/2021)  -- Version Stable (15/03/2021)
- Possibilité d'envoyer plusieurs images dans les notifications
- Images dans les notifications accessibles en cliquant dessus (plein écran, zoom et scroll)
- Widget clim : fanSpeed non limité
- Nouveau slider pour la température de blanc dans les widgets de lumière
- Nouveau widget Web View qui permet d'afficher un design, le dashboard ou n'importe quelle page web
- Bug fix

## Version 0.17.0 Beta (04/03/2021)
- Ajout d'un bouton Dupliquer pour les widgets
- Ré-écriture du sélectionneur d'icônes / images
- Possibilité de choisir image ou icône sur les widgets
- Possibilité d'ajouter des commandes infos à tous les widgets
- Images sous conditions dans tous les widgets
- Possibilité de personaliser les champs Nom et Sous-titre à l'aide de commandes infos
- Améliorations diverses et corrections de bugs dans l'appli

## Version 0.16.0 (22/02/2021)
- Notifications : Possibilité d'envoyer des images
- Geolocalisation : mode Tracking pour le suivi constant de l'appareil (nouvelle commande `Position` dans les équipements)
- Fix widgets non supprimés

## Version 0.15.4 (11/02/2021)
- Notification : comptibilité avec l'architecture X32
- Option pour afficher la barre du haut

## Version 0.15.3 Beta (10/02/2021)
- Fix bug taille icônes Jeedom
- Fix connection http

## Version 0.15.2 Beta (09/02/2021)
- Ajout des icônes Jeedom
- Correction du bug des widgets en double

## Version 0.15.1 Beta (06/02/2021)
- Widget groupe de prises
- Lumières : température de blancs

## Version 0.15.0 Beta (04/02/2021)
***Attention, l'application n'est plus en debug mais en release, veuillez désinstaller la version précédente***
- Pièces : possibilité de lié un objet Jeedom aux pièces
- Pièces : ajout du widget Pièce qui donne le résumé de l'objet
- Pièces : ajout dans l'app d'un bouton Pièces (menu gauche) qui donne accès à tous les résumés
- Authentification automatique à l'interface Web
- Menu du bas : possibilité d'exécuter des actions lors d'un swipe vers le haut ou le bas
- Historique : Axe horizontal en bas (même avec valeurs négatives)
- Historique : Option pour ne pas afficher dans la vue détails
- Historique : Option pour choisir le zoom par défaut
- Thermostat : slider désactivé lorsque vérouillé
- Optimisation de la connexion http
- Résolution de divers bugs et améliorations mineures

## Version 0.14.3 (27/01/2021)
=======
## Version 0.14.3 (28/01/2021)

- Correction bug status lumières
- Ajout icônes groupe
- Option pour inverser un binaire
- Assistant widget: remplissage auto de certains champs info
- Appli : option pour retour haptique sur action
- Bugs corrigés sur l'assistant de config
- Bug échelle historique

## Version 0.14.0 Beta (19/01/2021)
- Widget Portail : status en option
- Widget Lumière On/Off : le status peut être numérique
- Fix : titre des fenêtres dans l'assistant
- Nouveaux widgets : Groupe PIR - Groupe génériques binaires - Générique slider
- Ajout des icônes Font Awesome
- Appli fix : images des notifications
- Appli : Option pour définir les arrondis des éléments
- Un groupe vide fera passer à la ligne en mode vignettes

## Version 0.13.3 (18/01/2021)
- Ajout de la connexion en http
- Possibilité de donner 2 adresses (locale et externe). Le switch se fait automatiquement pas l'appli
- Nouveau widget Prise
- Fix : image perso sur le générique switch
- Fix : Arrondi sur valeur intensité lumière
- Volets : status et action stop en option
- Maj de la doc

## Version 0.12.0
- Historique : correction du bug des boutons de zoom
- Historique : accès à l'historique de toutes les commandes info via la page détails
- Notification : ajout de la compatibilité avec les machines ARM 64 bits
- Assistant : ajout des pièces dans la liste des widgets
- Scénarios : option pour l'accès à la page des scénarios. correction d'un bug sur cette page
- Page de login : meilleur rendu en mode paysage

## Version 0.11.0
- Notifications : possibilité de mettre à jour le contenu d'une notification existante
- Possibilité d'ajouter des conditions sur status pour le choix de l'image sur les widgets (gérérique numérique - Température - Humidité - Puissance)
- Scénarios : Ajout d'une page dédiée récupérant tous les scénarios. Un appui sur l'icône lance le scénario (si actif). Icône grisée si désactivé
- Les lumières d'un groupe sont affichées dans la vue détails
- Changement de l'icône de notification
- Amélioration de la géolocalisation. La localisation est récupérée même si l'appareil a été éteind ou en mode avion.
- Widget volets : Possibilité de mettre un binaire pour l'état. Stop et slider facultatifs
- Corrections de bugs

## Version 0.10.0
- Ajout de la géolocalisation

## Version 0.5.0
- Ajout d'un widget Mode
- Ajout d'un widget Action Générique (other)

## Version 0.1.0
Version initiale
