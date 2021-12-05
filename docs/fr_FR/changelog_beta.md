# Changelog JeedomConnect

## Version 0.23.4 (en dev)
- Nouveautés :
  * Accès aux logs des scénarios et plugins depuis l'appli (uniquement pour les utilisateurs admin)
  * Widget `géolocalisation` : option pour définir le zoom par défaut, mode animation de la carte auto en option, et ajout d'un marqueur sur la dernière position sur un tracé
  * Widget `Modes` : option pour mettre les modes dans la contenu de la carte (plutôt qu'une modale)
  * Modification du menu `Mise à jour plugins` par `Plugins` : visualisation de l'ensemble des plugins dispo, documentation, et logs (uniquement logs principales pour le moment)

- Bug fixes :
  * Crash dans la grille principale si vide
  * Fix ordre des infos supplémentaires
  * Masquer prévisualisation de la carte en personalisation
  * Pleins d'autres petits bug corrigés, amélioration...


## Version 0.23.3+1 (28/11/2021)
- Bug fix plugin uniquement (pas de mise à jour de l'application)

## Version 0.23.3 (27/11/2021)
- Nouveautés :
  * Création automatique des widgets directement depuis l'appli (via types génériques)
  * Les groupes sont à nouveau disponibles en mode grille avancée (mais pas rétractables pour le moment)
  * Possibilité définir la mise en page des widgets dans un groupe (mode grille avancée)
  * Possibilité de configurer le nombre de positions stockées par la géolocalisation (0 pour désactiver la base : la position est alors envoyée immédiatement ou perdue à jamais)
  * Personnalisation des sous-titres en mode Grand widget (taille et couleur)
  * Possibilité de masquer l'aperçu dans la personnalisation
  * Ajout d'un lien `Changelog` dans la fenêtre `A propos`
  * Ajout des types génériques `Climatiseur` et `Géolocalisaton` (/!\ ces types sont propres à JC pour le moment)

- Bug fixes :
  * Bouton lock/unlock dans le grand widget thermostat
  * Problème d'affichage des widgets dans un groupe
  * Les groupes désactivés sont masqués
  * Empêche la connexion au websocket si connexion en cours
  * Pas de polling si option activée mais en websocket
  * Création de widget depuis l'appli était cassée (pas d'id affecté)
  * Rafraichissement des images dans le widget `Images`


## Version 0.23.2 (19/11/2021)
- Nouveautés Plugin :  
  * Ajout d'un bouton `Infos Community` : ouvre une fenêtre qui affiche toutes les informations qui nous sont nécessaires lorsque vous créez un nouveau sujet sur le forum. Il vous suffit simplement de cliquer sur le bouton `Copier`, puis sur le forum coller ces infos. Tout est déjà préformaté ! 
  * Création de widgets en masse : ces créations sont possibles uniquement si les commandes de vos équipements sont correctement configurées avec des types génériques (normalement à la charge des développeurs des plugins que vous utilisez).  
  Pour vérifier/modifier vos commandes avec les bons types génériques, vous pouvez utiliser le bouton `Config types génériques` <i>(pour les personnes qui seraient déjà en version beta/alpha sur le core de jeedom (4.2.x) vous pouvez utiliser `Outils/Types d'équipement`)</i>  
  L'outil peut détecter des widgets déjà existants, dans ce cas ils seront mis en surbrillance et décochés.  
  * Création de widget (unitaire) en automatique : si vous choisissez de créer un widget de façon unitaire, vous avez la possibilité de pré-charger les différentes commandes nécessaires pour le widget en cliquant sur le bouton `Création automatique` (même pré-requis que le point précédent) et en sélectionnant l'équipement qui sera utilisé pour créer le widget.  
  * Pré-sélectionne automatiquement la pièce lors du choix des commandes en fonction de la pièce sélectionnée sur le widget
  * Notification iOs - Option pour qu'une notification arrive en `alerte critique` et possibilité de régler le volume du son (sonnera même si le son est coupé ou en mode `Ne pas déranger`)
  
- Nouveautés Application :
  * Mode grille avancée (à activer dans `menu/préférences`) : permet de choisir la taille des widgets et les placer à l'endroit désiré sur l'écran. Vous n'êtes plus limité dans une grille standard de 3 ou 4 widgets par lignes avec tous les mêmes tailles, mais vous pouvez organiser chaque page comme bon vous semble, avec des espaces, des widgets grands, petits, longs, hauts, ...  (nb : les menus/regroupements `groupe` n'existent plus avec cet affichage !)
  * Personnalisation possible de l'affichage forcée avec le nouveau mode `Grand widget`
  * Personnalisation du statut pour la vue `Vignette`
  * Personnalisation des valeurs min/max sur les historiques
  * Possibilité de dupliquer un widget
  * L'accès à la page de notifications ne requière plus d'être connecté

- Bug fixes :
  * Renfort sécurité pour la 4.2 : gestion des autorisations de téléchargements 
  * Clic long sur widget pour iOS
  * Correction du contenu des sous-groupes lorsqu'il y a plusieurs colones
  * Amélioration de la connexion
  * Image du `groupe de PIR` qui reste "rouge" meme si le nombre d'alertes est à 0
  * Widget mode : retrait de l'icone en doublon (était également affiché sur la valeur active)
  * Sauvegarde de l'image de notification dès sa réception
  * Fix animation décentrée des icônes FA
  

## Version 0.23.1 (22/10/2021)
- Nouveautés :
  * Ajout de la variable `#value#` dans les widgets compatibles
  * L'historique est masqué si la commande n'est pas historisée
  * Widget clim : 
    - Possibilité d'ajouter autant de modes que voulu - **Obligation de re-créer les modes**
    - Possibilité pour la ventilation d'utiliser une info `string` et une action `select`
  * Affichage du widgetId dans l'application
  * Nouvelle fenêtre pour configurer les commandes `Notifier tous` sur la page principale du plugin

- Bug fixes :
  * Problèmes de connexion au démarrage
  * Sauvegarde des notifications reçues
  * Crash de la modale de partage des paramètres persos
  * Son des notifications sous iOS
  * Possible fix du problème d'appui sur widget sur iOS
  * Envoie du niveau de batterie
  * Animation des images au format gif
  * Nombre d'éléments dans les widgets groupe
  * Affichage des infos supplémentaires dans la vue détails
  * Accès aux images et vidéos dans les notifications avec l'URL locale si sur le réseau local
  * Page de personnalisation du widget slider générique
  * L'ajout de variables dans l'édition de textes se fait à la position du curseur
  * Affichage des boutons de zoom ne reste plus grisés
  * Le zoom de l'historique n'est pas changé en cas de nouvelles données dans l'historique
  * Affichage des images dans un sous-dossier
  * Affichage des badges sur les icônes dans le drawer


## Version 0.22.4 (07/10/2021)
- Nouveautés :
  * Amélioration de la connectivité
  * Envoie de l'utilisateur et du widget à chaque exécution de commande

- Bug fixes :
  * Résolution du bug sur les menus hauts (Android)
  * Lignes multiples pour les sous-titres  
  * Fix autorisations des fichiers sur les dernières beta de Jeedom
  * Affichage de l'image dans les notifications sans titre
  * Boutons zoom dans historique

## Version 0.22.3 (01/10/2021)
- Bug fixes :
  * Affichage heure dans les notifications
  * Problèmes avec les actions
  * Page de personnalisation pour les widgets résumés ne plante plus
  * Bouton de Déconnexion remarche
  * iOS : menu du haut en défaut


## Version 0.22.2 (30/09/2021)
- Nouveautés :
  * Ajout d'un système de logs dans l'application
  * Nouveau widget `Image` qui permet d'afficher une image à partir d'une URL ou une commande info
  * Nouvelle commande pour envoyer des SMS (Version APK seulement). Fonctionne quelque soit l'état de l'application
  * Nouvelles commandes action pour gérer les préférences de l'application depuis Jeedom (pour l'instant tracking, recharger les données)
  * Options de personnalisations des vues résumés de widgets
  * Mise en place du DeepLink (pour intéractions avec d'autres applis comme Tasker)
  * Mise à jour de (presque) toutes les libs de l'appli, et passage à React Native 0.65.1 (dont le moteur JS Hermes 20 à 30% plus rapide sur iOS)
  * Les commandes `Lancer App`, `Afficher page` et `Pop-Up` ne prennent plus en compte qu'un seul champ dans les scénarios (anciennement `message`). Si jamais vous utilisiez le champs `Titre` il convient de modifier légèrement votre scénario pour basculer les informations dans le champ `message`. (Si la modif a lieu après la maj du plugin, il convient de supprimer l'action et de la re-créer dans le scénario).
  * Ajout d'un délai possible entre deux authentifications
  * Ajout de la commande `Modifier Préférences Appli` : permet de modifier certaines options de votre application. Faites un choix dans la liste déroulante, puis indiquez la valeur à mettre si nécessaire : `ON`, `OFF`, `MARCHE`, `ARRET`
  * Prise en compte des options indiquées dans les notifications
  * Possibilité d'envoyer n'importe quel type de fichier dans les notifications
  * Ajout de l'option perso pour cacher le statut en mode carte
  
- Bug fixes : 
  * Levée du problème sur la taille disponible en bdd pour la personnalisationisation des widgets  
  * Ré-activation de la commande `Détacher`
  * Notifications iOS et Android
  * Affichage correct des popups sur iOS
  * Affichage des groupes en mode paysage
  * Accès aux historiques dans la vue détail
  * Affichage des actions dans le widget Clim
  * Slider température blanc dans les groupes de lumières
  * Grisement des icônes persos sur les scénarios désactivés

## Version 0.22.1 (16/09/2021)
- Nouveautés
  * Nouveau widget `Historique` (graphique dans la grille)
  * Historiques : paramètres de personnalisation (couleurs, type de courbe, affichage par défaut...) 
  * Nouvelle commande pour afficher un `Pop-Up` dans l'application (si JC n'est pas en cours d'utilisation [Android uniquement], alors on l'affiche à l'écran)
  * Widget `Géolocalisation` : affichage de la carte dans le widget en mode carte
  * Ask dans les notifications natives sur iOS
  * Notifications : suppression manuelle ou auto de notifications
  * Notifications : possibilité de filter par type de notifications
  * Changements graphiques du centre de notifications
  * Widget `générique action` : options d'affichage disponible en personnalisation
  * Ajout de la variable `#value#` dans le widget Volet
  * Affichage de commande(s) orpheline(s) sur les widgets (page principale du plugin, pas sur la page Jeedom !)
  * Ajout de la commande `Notifier tous les appareils JC` qui permet d'envoyer une notification commune sur les appareils éligible (case à cocher depuis l'assistant des notifications, sur les notifications à utiliser dans ce cas)

- Bug fixes :
  * Authentification biométrique au démarrage
  * Rafraîchissement des caméras
  * Actions dans les notifications (Android)
  * Résumés de pièces : prise de compte de l'affichage sur valeur nulle configurée dans Jeedom
  * Historique : affichage en français pour l'axe de temps
  * Historique : intervalle de temps complet même si pas de valeur
  * Correction du Mode Expert
  * Ask dans les notifications natives d'Android

## Version 0.21.7 (05/09/2021)
(passage en stable 08/09/2021)
- Nouveautés :
  * Titres et sous-titres sous conditions : possibilité de mettre du code JavaScript (ex: `#[Réseau][PC bureau][Online]# == 1 ? "En ligne" : "Hors ligne"`)
  * Personnalisation du fond d'écran en vue Détails (screenId=10), pour l'instant commun à toutes les vues Détails
  * Widget générique slider : mode Heure (format Jeedom, ex: 145 -> 01H45, 1805 -> 18H05)
  * Widget générique slider : accès boîte de dialogue avec slider en vue vignette 
  * Widget générique actions : 2 nouvelles options pour personnaliser l'affichage
  * Widget Alarme : option pour les modes
  * Nouvelle option de personnalisation : masquer contenu de la carte
  * Option pour ajouter l'altitude, le type d'activité et le niveau de batterie à la commande de position
  * iOS : pastille de notifications non lues sur l'icône de l'appli
  * iOS : image / vidéo dans la notification native
  * iOS : actions rapides dans la notification native

- Bug fixes :
  * Action sur vignette widget clim/chauffage
  * Action sur vignette widget générique message
  * Espace vide dans Résumé de widgets si widget désactivé
  * Icône Jeedom de couleur pour les résumés et pièces
  * Centrage dans Favoris de widgets
  * Widget Caméra : dimensions corrigées en plein écran
  * Chargement des fichiers même protégés dans les notifications
  * Suppression des espaces de début et fin dans l'URL de connexion
  * Crash sur le bouton de suppression d'image
  * iOS : utilisation de FaceID
  * iOS : bug du bouton `Retirer ce widget`
  * iOS : bug de sélection d'une date  

## Version 0.21.6 (02/08/2021)
- Nouveautés :
  * Couleur de thème, plus de choix de couleurs, et mode auto noir/blanc
  * Groupe : choix de l'arrière plan (via l'appli)
  * Taille des titres et sous-titres pour chaque widget
  * Déplacement d'un widget ou d'un groupe à la place d'un autre widget

- Bug fixes :
  * Vue détails dans le widget lumières
  * Transparence et gestion des fonds d'écran
  * Bug au choix d'une commande info sur l'éditeur de widgets
  * Actions des toaster rétablies
  * La perso des widgets ne se rajoute plus pour les groupes
  * Défilement dans l'onglet Général de la page de perso
  * L'app ne crash plus lorsque qu'un widget est défaillant
  * Temps écoulé sur scénarios
## Version 0.21.5 (30/07/2021)
- Nouveautés :
  * Couleurs en fond d'écran (image, dégradés, gestion de la transparence)
  * Couleurs ou image sur fond des widgets (avec ou sans conditions)
  * Choix des couleurs titre/sous-titre pour chaque widget
  * Gestion des pièces et des résumés depuis l'application (pensez à recharrger les données [menu préférences])
  * Bouton de ré-initialisation des paramètres perso dans chaque widget

- Bug fixes :
  * Problème de perte de config au re-démarrage
  * Bug dans la page scénarios
  * Amélioration de la connexion
  * Sous-dossiers de img pris en compte
## Version 0.21.3 (22/07/2021)
- Nouveautés :
  * Edition des widgets depuis l'application (appui long sur un widget)
  * Paramètres personnalisés pour les widgets pour chaque appareil
  * Edition des menus depuis l'application (appui long)
  * Sauvegarde / restauration des paramètres de l'appli
  * Icônes / images : filtres et animations
  * Historique : possibilité de régler individuellement l'affichage en mode détaillé
  * Sécurisation des pages Préférences et Interface web
  * Vérouillage de l'interface
  * Possibilité de mettre une URL locale dans les webview

- Bug fixes :
  * Bug de la sauvegarde des paramètres de géolocalisation


## Version 0.21.2 (15/06/2021)
- Nouveautés :
  * Page Santé : permet de voir la page santé de votre jeedom, et gérer les démons de vos plugins : statut/start/stop (start/stop uniquement possible si l'utilisateur rattaché à l'équipement connecté appartient au groupe admin)
  * Page Mise à jour des plugins : permet de voir le nombre de mise à jour disponible sur vos plugins et réaliser tout ou partie de ces maj (maj uniquement possible si l'utilisateur rattaché à l'équipement connecté appartient au groupe admin)
  * Paramètres avancés pour la géolocalisation : 
  * Sélection de l'affichage ou non du niveau de batterie de son équipement JC sur la page `Equipement` de votre Jeedom (et donc la page JC correspondante)

- Bug fixes :
  * Ajout de la configuraiton du widget `liste de choix` quand il n'existe qu'en sous-widget
  * Correction des `#` manquants sur les champs dispo dans les listes `+`
  * Rafraichissement de la page `Batteries` toutes les 5 secondes et/ou lorsqu'on arrive sur la page.

## Version 0.21.1 (03/06/2021)
- Nouveauté :
  * Page batteries / piles
  * Option pour activer le polling en http

- Bug fixes :
  * Enregistrement des notifications dans l'appli
  * utilisation de l'adresse externe pour la géolocalisation

## Version 0.20.7 (25/05/2021)

- Nouveautés : 
  * Bouton export (format csv) sur la "vue d'ensemble" des widgets
  * Sur l'assistant widget : ajout d'un icone sur les widgets désactivés
  * Option pour n'afficher qu'une seule vignette par ligne

- Bug fixes :
  * Affichage des notifications
  * Version du plugin dans `A propos`

- Technique :
  * Ajout de nouvelles fonctionnalités pour traitement en masse, cf [post dédié](https://community.jeedom.com/t/jeedom-connect-bloc-code-pour-realiser-diverses-operations/61818)

## Version 0.20.6 (19/05/2021)

- Nouveautés :
  * Niveau de batterie
  * Ajout d'une commande info pour le snapshot caméra

- Bug fixes :
  * Affichage des notifications
  * Affichage des apps en favoris
  * Etat des scénarios en connexion http
  * Rotation écran après affichage d'une webview
  * Utilisateur et mot de passe dans les headers pour snapshot camera


## Version 0.20.5 (18/05/2021)

- Nouveautés :
  * Mode launcher : Jeedom Connect peut se substituer à votre launcher Android
  * Page lanceur d'applications à ajouter dans les boutons de la barre du haut. Créez aussi des liens vers vos apps favorites (appuie long sur l'application, puis `ajouter/supprimer en favoris`)
  * Notifications : 
    * Prise en charge dans l'application du code HTML des messages
    * Ouverture des liens dans le navigateur. 
    * Boutons d'actions alignés verticalement
  * Widgets en mode vignettes : choix d'utiliser l'ancien ou le nouveau design
  * Assistant widget : ajout de filtres (pièces, présents) pour l'ajout de widgets
  * Configuration : définir le trie des widgets par défaut (appliqué sur la page principale du plugin, et dans la liste déroulante de sélection des widgets sur l'assistant)

- Bug fixes :
  * Suppression du '2' dans la température de la météo
  * Temps écoulé dans les groupes de widgets : prise en compte du plus récent changement
  * Alignement dans le widget résumé

## Version 0.20.4 (10/05/2021)

- Nouveautés :
  * Nouvelle commande `Afficher page` : permet de naviguer vers une page de l'appli lorsque celle-ci est en premier plan
  * Nouvelle commande `Lancer app` qui permet de lancer une application lorsque l'appli est en premier plan (Android uniquement)
  * Nouveau widget `Lanceur d'application` qui permet de lancer une application (Android uniquement)
  * Option pour centrer les widgets
  * Authentification pour le flux caméra
  * Nouvelle commande pour détacher l'appareil lié à un équipement
  * Bouton `Copier vers` qui permet de copier la conf d'un équipement vers un autre

- Bug fixes :
  * Recentrage widgets
  * Arrondis widgets humidité et luminosité
  * Modale du widget Mode scrollable
  * Cacher les éléments s'applique au mode carte
  * Crash de l'appli au démarrage
  * Réception des notifications
  * Textes de la météo qui s'intercallent
  * Rafraichissement de l'historique

## Version 0.20.3 (05/05/2021)

- Nouveautés
  * Possibilité de sécuriser le démarrage de l'application par mot de passe ou empreinte biométrique
  * Possibilité de cacher les titres des menus bas
  * Changement d'organisation de la grille des widgets sur écran large
  * Second style pour l'horloge

- Bug fixes :
  * Images sous conditions
  * Notifications qui n'arrivent pas
  * Point de géolocalisation correctement situé
  * Résumé avec un widget en double

## Version 0.20.2 (01/05/2021)
- Nouveauté:
  * Possibilité de choisir le mode d'action sur icône
  * Affichage modifié dans la page des préférences

- Bug fixes:
  * Conditions sur images
  * Altitude dans la commande position

## Version 0.20.1 (30/04/2021)
- Nouveautés appli :
  * Mode immersif (permet de masquer les barres de statut et de navigation d'Android)
  * Fond d'écran : possibilité de le définir avec des conditions sur la page courante ou de commandes.
  * Barre du haut : possibilité d'ajouter et trier des boutons de racourcis
  * Barre du haut : possibilité d'afficher horloge + météo
  * Menu haut : mode flotant
  * Menu du bas : possibilité de le positionner à gauche
  * Menu du bas : possibilité de mettre des images à la place d'icônes

- Nouveautés plugin :
  * Vue d'ensemble qui permet de faire de l'édition de masse sur les widgets (uniquement sur les données communes)
  * Conditions des images plus flexible : possibilité d'enchaîner les conditions
  * Option pour ajouter l'altitude à la commande position
  * Conserve les filtres et ordres défini sur la page principale du plugin 

- Bug fixes :
  * Correction du timestamp pour les données de géolocalisation
  * Bug des sous-widget de la vue détail corrigé
  * Bug des widgets supprimés alors qu'ils existent dans un "widget parent"
  * Disparition des informations sur l'onglet équipement (après ouverture de la modale choix d'icone)
  * Affichage du texte complet dans les notifications

## Version 0.20.0 (21/04/2021)
- passage en version stable (identique à 0.19.5)

## Version 0.19.5 (19/04/2021)
- Nouveauté :
  * Dans la vue vignette possibilité de cacher différents éléments : nom, sous-titre, status et/ou image

- Bug fixes :
  * Modales des widgets Thermostats et message liste
  * Affichage des statuts de plusieurs widgets (mode vignettes)
  * Affichage des (sous) widgets dans la vue détails
  * Suppression d'un widget met à jour immédiatement la configuration des équipements
  * Drag & drop : ajout d'un élément dans un groupe (déjà rempli)

## Version 0.19.4 Beta (17/04/2021)
- Nouveautés :
  * Commande Position : ajout de l'altitude (nouveau format :`latitude,longitude,altitude`)
  * Nouvelle commande info `Activité` (valeurs possibles : still, on_foot, running, on_bicycle and in_vehicle)
  * Possibilité de définir le type de connexion pour chaque équipement (http ou websocket). Pensez à re-générer vos QR-code

- Bug fixes :
  * Modale choix de couleur
  * Titres coupés dans menu haut sur One Plus (?) 
  * Affichage et sélection des images perso
  * Drag and drop fix

## Version 0.19.3 Beta (16/04/2021)  
- Nouveautés Plugin : 
  * `Drag & drop` l'ensemble des objets sur les assistants & widgets
  * Création automatique d'une sauvegarde de la définition des widgets à chaque backup de Jeedom
  * Affichage du nom de l'équipement en cours de modification (sur la modale assistant)
  * Ajout des `directions` sur le widget Caméra
  * Ajout la possibilité d'intégrer d'autres widgets à l'intérieur d'un widget (sur la vue détail)
  * Ajout de l'`unité` sur les informations supplémentaires
  * Permet de définir le `pas` d'un slider (1 par défaut)
  * Permet de `cacher le titre` du widget à l'affichage sur l'application (mode carte)
  * Ajout d'une action automatique lorsqu'une page du menu bas est affichée (similaire au swipe Up ou Down, mais là systématiquement et automatiquement)
  * Prise en compte des `tags` pour les `scenario` sur les actions `SwipeUp`, `SwipeDown` et `Action` des menus bas


- Nouveautés Application : 
  * Clic sur l'icône de la vignette réalise une action : changement d'état d'une lumière/switch, générique action : déclenche la 1ère action paramétrée, ...
  * Modification de l'affichage des widgets
  * Affichage d'un widget en erreur, si ça configuration n'est pas bonne (il ne devrait plus y avoir d'écran blanc !)
  * Modification de l'affichage d'un slider : ajout des icônes + et - de chaque côté, et informations au-dessus du slider
  * Support du nouveau system de DNS Jeedom (automatique)
  * Boîte de dialogue `A propos`

- Bug fixes :
  * Affichage de l'option carte/vignette sur une pièce (arrivé depuis un widget)
  * Effacement des notifications android lorsque l'on supprime les notifs dans l'application
  * Les titres ne sont plus tronqués sur certains appareil (!?)
  * Effacement du texte d'un message générique après envoie (en vue détail)
  * Correction d'un bug d'affichage lors d'une rotation de l'écran quand une vidéo est en plein écran

## Version 0.19.2b Beta (08/04/2021)
- Bug Fixes :
  * corriger l'erreur sur la création d'un nouvel équipement 

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
- Possibilité de personnaliser les champs Nom et Sous-titre à l'aide de commandes infos
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
