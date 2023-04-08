# Changelog JeedomConnect  

## Version 1.8.0 (08/04/2023)

Relancez l'app au moins une fois avant d’utiliser les nouveautés (ie : kill l’application JC, puis la relancer).

- Nouveautés :
  - [Android 11+] Mise en place du contrôle d’appareils par le système. Seuls les widgets dispo sur l’équipement de votre appareil seront proposés. Pour le moment sont supportés : Alarme, Luminosité, Humidité, Caméra, Porte, Portail, les Générique (Actions**, Binaire, Numérique, Texte, Slider, Switch), Puissance, PIR, Prise, Scénario, Volet, Lumière(s), Température, Climatiseur, Thermostat, Fenêtre
    - Les widgets visibles dans le paramétrage de cette option peuvent être réduits en cochant l’option "Masquer l'appareil sur le widget".
    - De même, il est possible d’interdire l’exécution de la commande depuis un écran verrouillé en cochant l’option "Contrôle depuis l'écran de verrouillage" sur le widget également
   

    [Petite précision] :  sur les widgets Générique Actions → seule la 1ère action du widget est exécutée lorsque ce widget est ajouté comme contrôleur ! :warning:

  - [Android 11+] Ajout des contrôleurs de type `Composant` : Switch, Slider et Texte
  - [Android] Nouvelle commande action `Effacer les données`, utile en cas de perte ou vol de l'appareil. Pour confirmer l'action il faudra saisir le mot `erase` sur le champ correspondant.
  - [Android 7+] : Possibilité d'ajouter des raccourcis rapides dans le panneau des raccourcis de paramètres du volet de notifications
  - [Android] : Nouvelle commande `Ne pas déranger`
  
  - Changement de la structure de données des éléments (et nettoyage du code). Attention si vous avez des blocs code et faites des changements vous même il se peut que certaines choses ne fonctionnent plus...
  
  - Ajout de boutons "cocher tout/décocher tout" sur la page `Synthèse des widgets`
  - Grille avancée : Lors de l'édition, possibilité de figer les éléments pour configurer le verrouillage et la profondeur des éléments
  - Refonte des historiques pour plus de performances, et nouvelles options, affichage des statistiques
  - Nouveau widget `Groupe d'historiques` : affichage de plusieurs historiques dans un seul graphe
  - `Widget Caméra` : possibilité de faire du pinch-to-zoom ou double-tap
  - Composants : ajout du champ `Pièce`
  - Ajout du paramétre `Visibilité sous condition` dans les personnalisations des widgets
  - Passage en mode `Hors connexion` dès que l'équipement est désactivé sur Jeedom
  - Affichage de graphe d'historique en arrière-plan des widgets
  - Créer du relief : élévation des tuiles et widgets dans l'application
  - Configuration pour le redimensionnement des images en arrière-plan
  - Choisir la taille des menus du haut
  - Définir une sécurité sur les commandes des widgets `Groupes`
  - Permet qu'un toaster soit affiché sur l'app lorsqu'un scénario est utilisé avec l'instruction `Retourner un texte/une donnée` (mot clé `scenario_return`)
  - Mise en place d'une seule barre de recherche sur le plugin
  - Prise en compte des conditions de visibilité sur les widgets dans la vue `Détails`
  
  - [Version APK] : Réception des SMS. Deux nouvelles commandes donnent le dernier SMS reçu et le numéro de l'expéditeur
  
- Bug fixes :
  - Amélioration du temps d'ouverture sur l'édition d'un élément
  - Correction de l'action d'activation du geofence  
  - Crash sur la jauge lorsque la valeur est supérieure au max défini
  - Rendu de la jauge et slider circulaire qui disparait
  - Crash dans le slider lumières de couleurs
  - Augmentation du timeout sur les requêtes http
  - Composant `Séparateur` prend toute la largeur sur écran large
  - Marges des widgets dans un groupe
  - Migration automatique
  - Fix anomalie snapshot 0%
  - Fix fonction de sauvegarde depuis l'application
  - Affichage des images en arrière-plan
  - Affichage de tous les widgets en mode édition de grille avancée (y compris ceux pour lesquels la `condition de visibilité` est évaluée à fausse)
  - Prise en compte du pas lors de l'arrondi de valeurs numériques sur les widgets
  - Crash dans les pages `Batteries` et `Pièces`
  - Prise en compte du fuseau horaire (si l'appareil est sur un autre fuseau que Jeedom)
  - Divers bugs sur le service Android et les raccourcis rapides
  - Crash du service Android dans certaines conditions
  - Crash de l'appli avec la webview
  - Crash lors de l'édition de la grille d'un groupe
  - [iOS] :
    - couleur de l'aiguille de la jauge
    - Fix icône de l'app
    - Action directe sur l'image d'un widget
    - Fix boutons du widget `Historique`
    - Fix boutons de la barre du haut
    - Authentification au démarrage
    - Sélection du thème sur iOS
    - Téléchargement du QR Code depuis l'appli

## Version 1.7.0+ (08/01/2023)

PLUGIN UNIQUEMENT

- Bug Fix :
  - édition d’un widget image ouvre et sauvegarde un composant image à la place

## Version 1.7.0 (06/01/2023)

La grosse nouveauté de cette version est l'arrivée des "Composants", un cousin germain du "Widget".
Il s'agit d'élément "brut" unitaire très simple permettant (ou non) de réaliser une action, sans intelligence ni artifice (pas d'images sous conditions, de vue détaillée, d'habillage, ...).  
Aujourd'hui 6 types de composants existent : Séparateur, Bouton, Switch, Slider, Jauge et Image.  
Ils peuvent être ajoutés dans chaque page, en plus des widgets et des groupes, ainsi qu'à l'intérieur d'un groupe.  

Il devient par exemple très facile de créer une télécommande, ou de mettre une image (d'un module par exemple) sur laquelle on peut placer n'importe quelle(s) information(s) à différents endroits, ...
Les possibilités de personalisation deviennent immense ! Vous pouvez dorénavant faire exactement ce que vous désirez, comme vous le désirez sans qu'on vous impose un style, une mise en page, un emplacement, une marge trop grande/petite, ...  
  
- Autres Nouveautés :
  - Intégration des composants sur la page principale du plugin
  - Ajout la possibilité de verrouiller la position d'un widget : cliquez sur le cadenas ! en approchant un autre élément à côté d'un élément verrouillé, alors celui-ci viendra se placer au plus prêt sans bouger tous ceux verrouillés autour !
  - Possibilité de superposer différents éléments lorsque ceux-ci ne sont pas verrouillés :
    - composant sur composant ✅
    - widget sur composant ✅
    - composant sur widget ✅
    - widget sur widget 🚫
  
  - Notifications (Android) : Possibilité de rendre une notification permanente (envoyez un message `cancel` pour la supprimer)
  - Edition des grilles avancées : affichage des coordonnées et tailles des éléments, diminution du pas de la grille et possibilité de verrouiller les éléments (une réinitialisation des grilles peut être nécessaire)
  - Suppression des groupes sans nom (--> utiliser un séparateur pour créer un espace)
  - Edition du champ `visibilité sous conditions` depuis l'application
  - Option d'opacité pour l'arrière plan d'un groupe
  - Nouveau champs `Nom d'affichage` qui défini un nom "lisible" utilisé à l'affichage sur la page principale du plugin et de l'application. Permettant ainsi d'avoir un champ `nom` avec des variables ou autres, initialement un peu moins lisible
  
  - Nouvelle commande `Obtenir infos` pour rafraîchir les données provenant de l'appareil
  - Action `geofence` pour activer/désactiver le geofencing depuis la commande `Modifier Préférences Appli`
  
  - Changement d'icônes pour widgets génériques binaire, numérique et texte (depuis le plugin besoin d'ouvrir et sauvegarder chaque widget pour que la maj soit faite)
  - Fond d'écran : possibilité d'utiliser une `commande` dans les conditions
  - Affichage d'un icone `!` orange sur les widgets qui ont des commandes dont l'équipement est désactivé / n'existe plus
  - Restaure automatiquement la précédente sauvegarde de configuration lorsque le fichier courant est corrompu
  
- Bug fixes :
  - Affichage des applications de l'appareil (Android)
  - Accès aux historique de commandes depuis la vue Détails
  - Problème dans la sélection de modes
  - Erreur dans la page d'édition de widget
  - Edition des couleurs des icônes de menu bas
  - Changement de mise en page pour les widgets de résumés
  - Changement de nom du fichier QR code téléchargé
  - Bouton Envoyer pour un widget générique message en vue détail
  - `Images sous conditions` pour les widgets de lumières
  - Menu `Raccourcis` sur iOS
  - Recherche insensible à la casse dans l'application
  - Crash de la reconnaissance vocale
  - `Ask` sur une commande `notifier tous` ne renvoyez plus l'info d'une réponse déjà obtenue (android)
  - Oblige la sélection d'un widget sur les éléments "plus de widgets"

## Version 1.6.0+ (06/12/2022) - PLUGIN UNIQUEMENT

- Bug fix :
  - non création du répertoire où sont stockées les images perso

## Version 1.6.0 (30/11/2022)

- Nouveautés :
  - Grosse refonte graphique de l'appli :  
    - Ajout de thèmes de couleurs : Plus de 40 thèmes de couleurs au choix avec pour chacun, une couleur primaire/secondaire, + un thème personnalisable
    - Ces couleurs de thème sont accessibles depuis les différents éléments de personnalisation de l'appli
    - Options de mixage des couleurs des surfaces et éléments de surface
    - Changement de la police des textes, qui n'utilise plus celle du système
    - Paramètre de couleur pour la barre du haut, de transparence pour le menu bas
    - Choix des couleurs et transparence par défaut des différents éléments d'un widget (titre, sous-titre, statut, background)
    - Réorganisation du menu `Préférences`

  - `Prochaine Alarme` : ajout d'un filtre pour ne récupérer la prochaine alarme du téléphone uniquement si elle fait partie d'une liste de programme que vous souhaitez récupérer.  
    Android ne permet toujours que de récupérer la PROCHAINE alarme prévue dans la system. Deux cas de figure donc :  
    - vous ne mettez pas de filtre => vous obtenez des maj de la cmde à chaque fois que la prochaine alarme est modifiée (sans vraiment savoir de qui elle vient)
    - vous filtrez par exemple uniquement sur les alarmes provenant du package "réveil" :
      - si la prochaine alarme est émise par ce package --> le plugin recoit la maj
      - si la prochaine alarme provient d'un autre package --> vous n'aurez pas la maj
    - Ajout d'une nouvelle commande `Package Prochaine Alarme` qui permet de savoir quel est le package qui déclenchera la prochaine alarme sur votre téléphone

  - `Notifications multiples` : vous avez dorénavant la possibilité de créer plusieurs commande de type `Notifier tous` :  
    Vous pouvez par exemple définir un 'Notifier Tous - Enfants', 'Notifier Tous - Parents' et un 'Notifier Tous - Famille' --> en fonction du cas nécessaire vous appelerez l'une de ces commandes dans vos scénarios !

  - Création de la commande `Visibilité Menu` : qui permet de masquer/afficher un menu d'un équipement
  - Création de la commande `Visibilité Widget` : qui permet de masquer/afficher un widget sur <u>tous les équipements</u>

  - Regénération automatiquement du QR Code si nécessaire après la modification de l'équipement
  - Séparation par onglets des différents type des commandes pour y voir plus clair
  - Ajout d'un affichage de type `Jauge` sur les widgets `Générique numérique`, `Puissance` et `Prise`
  - Lorsqu'un widget est toujours présents sur la configuration de votre équipement mais n'est plus disponible sur votre installation Jeedom, alors il est automatiquement effacé
  - Déplacement de l'affichage du QR Code sur la page principale du plugin
  - Scanne du QR Code depuis l'application possible avec la caméra frontale
  - L'utilisation du JavaScript est possible sur le champ `statusText` d'un widget Générique Texte  
  - Mise sous condition d'affichage d'un widget ou d'un menu : vous pouvez définir si un élément peut être affiché en fonction d'une condition.
  - Dans le widget `Groupe géolocalisation`, un appui sur le nom d'un marqueur va vers sa carte dédiée
  - Ajout du paramètre `"Facteur de zoom` sur le widget `Groupe géolocalisation`
  - Récupération des labels `titre` et `message` si définies sur les commandes de sous-type `message`, alors ceux-ci sont affichés sur l'application
  - Gestion des notifications depuis l'application
  - Centre de notifications : option pour centrer le contenu
  - Nouvelles commandes dans le plugins :
    - `Mode sonnerie` *[Android]* : Permet d'activer un mode de sonnerie `Silencieux`, `Normal` ou `Vibreur`.
    - `Volume` : Permet de régler le volume de l'appareil (en %). Pour Android, vous pouvez spécifier en plus dans champs `Titre` de la commande le canal audio à modifier
  - Maintient de l'écran allumé en plein écran pour une caméra
  - Possibilité de changer de thème depuis une commande Jeedom
  - Possibilité de télécharger le QR code de connexion depuis l'application
  - Les actions `Mode sonnerie` et `Modifier Volume` ont été modifiées pour permettre le choix parmi une liste de valeur. Si vous avez réalisé des scénario avec la version 1.5.4 alors il vous faut les modifier pour prendre en compte ce changement  
  - *[Android, Service]* Commande info `Volume actuel` pour connaitre les 6 différents volumes de son appareil. La commande est valorisée par défaut avec l'ensemble des volumes disponible, selon le format suivant : `Alarme;Appel;Musique;Notification;Sonnerie;Système;`. Vous avez la possibilité de spécifier si vous ne souhaitez conserver qu'un seul type de volume et dans ce cas la commande renverra uniquement la valeur de ce type de volume. Dans le cas de `Toutes` les valeurs, ça sera à vous de vous créer un virtuel avec autant de commandes que vous souhaitez récupérer parmis les 6 types dispo.
  - Redesign page d'accueil du plugin pour afficher moins de menu
  - Ajout du nom de l'équipement sur le QR-Code
  - Modification de l'affichage sur le dashboard Jeedom pour les commandes ayant des listes de choix possible
  - Ajout du déclencheur de changement de volume dans le service Android

- Bug fixes :
  - Import de la configuration du plugin
  - Masquage de l'api key de JC dans les logs du démarrage du démon
  - Erreur lorsqu'un menu haut n'est pas rattaché à un menu bas
  - Récupération des applis de l'appareil dans certains cas
  - Envoi des actions (type `TTS`) lorsque l'appli est en background
  - Correction sur la création de notification qui plante
  - Suppression automatique à tord de commande "notifier tous"
  - Problème avec l'authentification au démarrage sur iOS
  - Crash lors de la sélection du style d'horloge
  - Exécution et affichage dans les widgets `Choix de listes` et `Mode`
  - Suppression du cache sous iOS
  - Accès à l'historique d'une info supplémentaire
  - Mode sombre automatique au retour de background
  - Rechargement du widget `Webview` au retour de background
  - Utilisation de la commande `Puissance` dans la jauge du widget `Prise`
  - Boutons de la barre du haut qui s'affichent au dessus de l'horloge
  - Affichage d'une notification Ask sans options
  - Images sous conditions dans les widget de lumières
  - Autorisations de notifications pour Android 13
  - Coquille sur le démon qui ne renvoie pas les messages d'erreur mais coupe simplement la connexion
  - La commande `Modifier Volume` accepte la valeur "0" (avec les guillemets) de façon à forcer la valeur à 0
  - Suppression de la colonne `Notifier tous` dans la synthèse de équipement
  - Problème avec l'historique des commandes infos - string
  - Ajout d'une marge pour le status dans Vignette Style 2 (dépassait un peu avec l'arondi)

## Version 1.5.1+ (18/11/2022)  -  Plugin uniquement

- Bug Fixe sur les notifications :
  - Problème lorsque le nom de la notif, la commande ou le scnéario contient un apostrophe
  - Mauvaise enregistrement lors de la création d'une notif
  - Suppression de la commande action créé automatiquement et nommée `{`
  
## Version 1.5.0 (12/10/2022)

- Nouveautés :
  - Websocket :
    - Gros chantier et refonte complète de la connexion en websocket pour la rendre plus performante et ne plus avoir d'état incohérent entre Jeedom et JC.  
    Il pouvait arriver que le statut d'un plugin diffère entre Jeedom et JC, qu'une commande ne s'éxécute pas, etc ...  
    Ces problèmes étaient liés à un cache sur le démon écrit alors en php. Nous avons ré-écrit les différents modules et sommes passés en Python pour ne plus avoir ces soucis.  
    Un nouveau paramétre peut être modifié dans la configuration `Port Socket Démon` qui permet la communication entre Jeedom et le démon (par défaut `58090`). Alors que le `Port Websocket JC` est celui qui est utilisé pour ouvrir une connexion entre chaque application JC et le démon (inchangé, par défaut `8090`).
    - Il sera dorénavant à nouveau possible de mettre à jour le plugin JC depuis son application, même si on est connecté en websocket
    - Nouvelles règles pour le démon :
      - automatiquement arrêté si aucun équipement n'est configuré pour utiliser le websocket
      - non démarrable si aucun équipement n'est configuré pour utiliser le websocket
      - démarré si depuis l'application on décide de faire passer son équipement en websocket et que le démon est stoppé
      - redémarré automatiquement si un champ de configuration essentiel est modifié (à la sauvegarde de la configuration)

  - Géolocalisation :
    - Widget `Géolocalisation` : vous pouvez lui donner un petit nom à afficher
    - Création d'un nouveau widget `Groupe de Géolocalisation` : permet d'afficher plusieurs points de géolocalisation sur un seul widget
    - Affichage d'un message d'info si aucun équipement n'est paramétré pour être affiché sur la carte/widget `Localisation`
    - Possibilité d'afficher le trafic routier sur la carte
    - Possibilité d'afficher l'historique des positions

  - Général - Côté plugin :
    - Revamping de la page `configuration` du plugin
    - `Générique action` : pour les commandes de sous-type message option supplémentaire pour `Afficher/masquer le titre` ou `garder le dernier message` (comme sur le `générique message`)
    - Contrôle de cohérence version plugin/application : beta/beta ou stable/stable, pas de mix
    - Permet l'affichage de la carte `Localisation` sur le dashboard d'un utilisateur non-admin
    - Lors de la sauvegardes des préférences de l'application, si le fichier de backup est identique au précédent, alors le plus vieux est supprimé
    - Purge automatique des fichiers de sauvegarde des préférences de l'application. Vous pouvez définir le nombre à conserver sur la page de configuration (`Tous` par défaut)

  - Général - Côté app :
    - Ajout d'un contrôle pour vérifier que les versions de l'application et du plugin sont bien alignées : beta/beta ou stable/stable
    - Ajout d'une option pour sauvegarder automatiquement la configuration de l'application (est réalisée lors du démarrage de l'appli) de façon régulière (par défaut : `jamais`)
    - Ajout d'une option pour recharger automatiquement la configuration Jeedom (est réalisée lors du démarrage de l'appli) de façon régulière (par défaut : `tous les jours`)
    - Ajouts des fonctions `modifiedDate` et `collectDate`, ainsi que la librairie `momentjs` pour les textes dynamiques
    - Inversion possible des sliders dans les paramètres personnalisés :
      - horizontal : droite <-> gauche
      - vertical : haut <-> bas
      - circulaire : horaire <-> antihoraire

- Bug fixes :
  - Connections multiples quand le démarrage de l'app est sécurisé
  - Corrections sur le Geofencing
  - Remontée de la prochaine alarme à `-1` si aucune alarme programmée

## Version 1.4.1 (29/08/22)

- Bugs fixes sur la partie Geofencing/Localisation du plugin :
  - Affichage d'un message si aucun équipement n'est sélectionné pour être affiché sur la carte `Localisation`
  - Fix erreur si aucun élément n'est affiché
  - En modifiant une zone geofence de l'équipement, on perd le lien avec le modèle

## Version 1.4.0 (27/08/22)

- Nouveautés :
  - Reconnaissance Vocale et interaction :
    - Ajout de la reconnaissance vocale dans l'application. Possibilité d'envoyer vers les interactions Jeedom, une commande message ou un scénario
    - Détection de mots clés vocaux personnalisés (ie : `hotword`) pour activer la reconnaissance vocale. Chaque mot clé peut avoir un comportement différent (interaction, commande, scénario) => `"hey mon super assistant, ouvre les volets"`, `hey darkvador, éteins les lumières`)
    - [Android] La détection du `hotword` fonctionne en permanence lorsque le service d'arrière plan est activé.
    - [Android] Option pour ne pas inclure le son du microphone dans le stream RTSP (à activer pour la reconnaissance vocale)
    - Ajout du login de l'utilisateur qui lance une interaction

  - Géolocalisation :
    - Définition des positions de geofencing depuis le plugin
      - Possibilité de créer et partager des positions de geofencing depuis le plugin
      - Ajout d'une barre de recherche pour localiser précisément une adresse postale et créer la zone correspondante
      - Possibilité de partager une zone de geofencing créée sur un équipement à tout le reste de la famille (bouton `+` sur une zone dans la partie `mon équipement`)
    - Visualiser la localisation de l'ensemble de vos équipements JC sur une carte. Les positions sont mises à jour dynamiquement à chaque déplacement d'un appareil. (Pensez à autoriser l'affichage sur la carte globale sur la page configuration de chaque équipement sur le plugin)
    - Widget `Géolocalisation` : vous pouvez personnaliser le pin (et la couleur) du repère
    - `Géolocalisation` (app):
      - Ajout d'un bouton sur la carte pour passer en plein écran,
      - Nouveaux paramètres : configurer le type de carte (Standard, Satellite ou Relief), le thème sombre/clair, et afficher les geofences (seulement si l'option `gefencing` est activée sur l'équipement)
      - Corrections de bugs, et ajout d'une option pour améliorer le geofencing
    - Possibilité d'ajouter un widget (Jeedom, pas JC) pour afficher la carte des localisations JC sur le Dashboard de votre Jeedom
  
  - QR-Code :
    - Affichage du QR-Code de chaque équipement visible directement sur la page principale du plugin, à chaque survole d'un équipement par la souris (choix à faire au niveau de la page `configuration` du plugin, après un rafraichissement)
    - Le QR-Code de l'équipement est masqué dès lors qu'une modification essentielle est en cours sur l'équipement. Celui-ci est automatiquement regénéré à la sauvegarde de l'équipement
    - Les QR-Codes de l'ensemble des équipements JC sont automatiquement regénérés si les urls de connexions sont modifiées sur la page de configuration du plugin. (Si les modifications interviennent au niveau de la configuration `Réseaux` de Jeedom, alors la génération devra être réalisée à la main)
  
  - Général - Côté plugin :
    - Ajout d'une fenêtre de synthèse sur les équipements JC : configurez un certain nombre d'éléments en un clic l'ensemble de vos équipements JC
    - Lors de la définition d'un nouvel équipement JC : choix de `polling` par défaut si connexion par DNS Jeedom détectée
    - Ajout d'un filtre possible sur les types de widget pour les modales de sélection de widgets
    - Ajout des tooltips pour avoir le nom des commandes sur les champs des commandes parfois tronqués (comme "Informations supplémentaires" & co...)
    - Refonte de toute la partie configuration des Notifications sur le plugin
    - Ajout de l'information `tendance` pour les commandes historisées (utilisation: `tendance(#cmd#)`) : retourne 'up', 'down', 'stable' ou 'null' (si non dispo)
    - Les informations historisées (moyenne, min, max, tendance) sont utilisables dans les conditions des images sous conditions  

  - Général - Côté Application :
    - Ajout de la gestion des swipes up/down et action sur les menus bas directement depuis l'application
    - Exécution d'un scénario : ajout du tag `eqId` qui permet de récupérer l'id de l'équipement qui lance l'exécution du scénario

## Version 1.3.1 (03/07/2022)

- Ajout d’une option sur la page configuration pour définir si le plugin doit gérer les connexions IPV6 ou non → ‹ non › étant le défaut  

## Version 1.3.0 (30/06/2022)

- Nouveautés :
  - L'application peut être utilisée en mode hors connexion, lorsque l'appareil n'est pas connecté au réseau (bien entendu les actions sont impossibles, et les infos peuvent ne plus être à jour...!)
  - Amélioration des performances et de l'ergonomie de l'appli
  - Affichage d'une fenêtre d'information pour préciser qu'il faut nous partager les informations d'installation pour chaque nouveau post sur community (sera affiché 3 jours de suite, si vous quittez la fenêtre en appuyant sur le "bon bouton" :), sinon s'affichera beaucoup plus longtemps ...)
  - Nouveau widget `Lecteur multimedia`
  - Traduction de l'application en Anglais, en Espagnol et en Catalan
  - Double authentification et restriction des utilisateurs en local lors de la connexion (si configurée dans Jeedom)
  - Option pour configurer la transparence des widgets
  - Ajout du paramètre de personnalisation `Bloquer vue détails`
  - Possibilité de détacher un appareil sur un équipement JC depuis l'appli (admin uniquement)
  - Reset valeur par défaut dans les slider de personnalisation
  - Choix de la couleur du titre des groupes
  - Option pour historique en mode Barre
  - [Android] Serveur RTSP pour streamer sur le réseau les caméras et microphone de l'appareil
  - [Android] Détection des visages en temps réel (commande binaire créée dans chaque équipement)
  - Possibilité d'agrandir le menu bas
  - `Générique texte` : personnalisation du texte de statut dans le widget
  - `Widget multimedia` : possibilité de définir la jaquette à partir d'un chemin de fichier local
  - Edition de widget dans l'appli : ajout automatique du nom de widget quand une commande est choisie. Pour la sélection des autres commandes, l'équipement est présélectionné
  - Sélecteur de widget : pull to refresh pour recharger la liste
  - Ajout activation de l'option `polling` sur chaque équipement du plugin
  - Ajout activation de l'option `websocket` dans l'application
  - La mise à jour du plugin JC n'est plus proposée par l'application, si la connexion active est en websocket
  - Clic possible n'importe où sur la tuile (et plus uniquement l'icone) si un widget en mode vignette bloque l'accès à la vue détail
  - Option pour retourner horizontalement la vidéo streamé (certaines caméras frontales ont un effet miroir)
  - Option pour bloquer l'accès détails d'un résumé de widget
  - Sur la configuration d'un widget depuis le plugin, ajout des noms des équipements sur lesquels le widget est paramétré
  - Sauvegarde quotidienne des fichiers de configuration
  - Ajout des options `averageValue`, `minValue`, `maxValue` (récupérées sur les commandes historisées uniquement). (utilisation: `average(#cmd#)` ou `min(#cmd#)` ou `max(#cmd#)`)
  - Check et affichage d'un message d'info si jamais le démon est en marche (et automatique) alors qu'aucun équipement n'utilise le websocket
  - Ajout de la version de l'os/api sur chaque équipement dans le résumé d'infos
  - Flaguer les widgets sans nom (visible avec le bouton "erreur")
  - Gestion de l'IPv6 pour la connexion Websocket  
  
<details>
  <summary>Bugs fixes</summary>  
  *Arrière plan auto pour les widgets lumières
  * Icône lumière quand intensité < 5%
  *Sélecteur de fichiers sur iOS
  * Notifications iOS quand l'appli est fermée
  *Crash au démarrage si objet vide dans la conf Jeedom
  * Crash au démarrage sur certains appareils Android
  *Mode immersif sur certains appareils Android
  * Min/max de l'axe vertical du widget `Historique`
  *Nombre de plugin à mettre à jour corrigé
  * Encodage des caractères dans les notifications
  *Bug de la lecture des vidéos depuis l'extérieur
  * Les personnalisations étaient parfois perdues après un changement/création de widget
  *Message vide si changement d'équipement non possible
  * Edition d'un scénario sans nom
  *Masquer le bouton mise à jour, lorsque seule la version de jeedom est à mettre à jour
  * Crash sur certaines configurations sans menus bas
  *Affichage de la barre du haut sur iOS
  * Authentification au démarrage par FaceId
  * Titre dans la modale du widget actions génériques
</details>

## Version 1.2.0 (12/04/2022)

- Nouveautés :
  - Ajout des raccourcis sur l'application : vous pouvez définir jusqu'à 4 raccourcis sur l'application. Ces actions sont accessibles après un appuie long sur l'icône de l'application JC sur votre bureau. Vous pouvez choisir d'éxecuter une commande, un scénario, ou l'affichage d'une page.
  - Prise en compte des droits utilisateurs (pour une connexion avec un `utilisateur limité`) sur l'exécution des scénarios et des commandes
  - Switch d'un équipement à l'autre sans se déconnecter/reconnecter possible depuis le menu `Paramètres de connexion`
  - Réorganisation du menu `Paramètres de connexion` : Afficher les informations de connexion, Permet la déconnexion, Gère l'option de polling
  - Personnalisation des sliders : choix des couleurs, taille, format (horizontale, verticale, circulaire), ...
  - Nouveau sélecteur de couleurs dans l'appli, dispo aussi dans les widgets `Lumières de couleurs` et `Groupe de lumières`
  - Ajout du `Centre de Messages`
  - Ajout de la `Timeline`
  - Permet la recopie des personnalisations sur un autre équipement JC
  - Le paramètre `Grille avancée` peut se configurer sur chaque page  
  - Ajout du choix du volume sur la commande `TTS`
  - Permet la regénération de la clé API d'un équipement (/!\ l'application doit être arrêtée et tuée avant de faire la manip sur le plugin /!\ )
  - Personnalisation possible du titre de la notification lors d'un `ASK` (utiliser la synthaxe : `title= Mon super Nouveau Titre | message=Ma question ?`)
  - Ajout des infos utilisateur (id et nom) lors de l'exécution d'un scénario (via widget ou menu) pour récupérer l'info dans les logs
  - Ajout du tag `#userJC#` lors de l'execution d'un scenario
  - Mise en place du `pull to refresh` sur les pages : santés, plugins, messages, timeline
  - Lorsqu'une page est en mode édition (grille avancée), pour une meilleur utilisation lors des redimensionnements il n'est pas possible d'ouvrir le menu principal de JC
  - Prise en compte du code html dans le widget `texte` (=> `<br>` pour un saut de ligne)
  - Ajout du widget `Evénement` : permet de mettre à jour une commande de type info
  - Ajout raccourci vers la page `Messages`
  - Fond d'écran : possibilité de régler plus finement les gradients de couleurs
  - Arrière plan des widgets : possibilité d'utiliser des cmd info pour les couleurs (par exemple mettre sur un widget lumières de couleurs le même fond que la couleur de la lumière)
  - Nouvelle gestion des images persos dans l'appli avec une page dédiée dans les préférences
  - Possibilité de supprimer ou ajouter des images persos depuis l'appli
  - Nouvelles options pour la personnalisation des sliders
  - Personnalisation de la taille de l'image d'un widget
  - Widget `WebView` : affichage de la page en mode carte (option), possibilité d'utiliser une commande pour l'URL, et possibilité d'injecter du code JavaScript dans la page
  - Widget `Images` : La taille s'ajuste automatiquement lors du redimensionnement du widget en grille avancée. Arrière plan automatique en option avec couleur qui dépend de l'image
  - Ajout de l'option de couleur automatique en fonction du thème dans le sélecteur de couleurs pour les arrières plans
  - Ajout de l'information `pièce` d'un widget dans les listes de widget (groupe, widget supplémentaires, ...)
  - Possibilité de vider le cache de l'appli directement depuis le menu `Préférences`
  - Possibilité d'utiliser la date de collecte d'une commande via la fonction `collect()`
  - L'affichage d'une page web dans un widget `webview` est par défaut désactivé
  - Choix plus élargi pour la taille des boutons des widgets
  - Widget `Lanceur d'application` : choix de l'appli lors de l'édition/création depuis l'appli
  - Ajout de l'option min/max sur le widget historique
  - Utilisation du nom perso d'une commande dans la modale de confirmation d'action
  - Ajout du pack d'icônes `kiko`  

## Version 1.1.0 (04/01/2022)

- Nouveautés [Android only]:
  - Mise en place du Service d'arrière plan qui permet une communication permanente entre JC et le plugin. Les infos sur l'appareil et les actions depuis Jeedom seront exécutées quelque soit l'état de l'application.
  - Ajout de nouvelle commandes info : `Etat écran`, `En charge`, `Etat Bluetooth`, `Etat Wifi`, `Adresse IP`, `Réseau wifi (SSID)`, `Prochaine Alarme`
  - Ajout de nouvelles commandes actions : `Allumer l'écran`, `Eteindre l'écran`, `Jouer un son`, `Commande shell`

- Nouveautés :
  - Ajout de nouvelles commandes actions : `TTS`
  - Widget `scénario` : ajout des options de sécurité pour executer le scenario
  - Accès direct à la configuration des widgets et des notifications sur un équipement depuis la page principale du plugin
  - Ajout du lien vers le forum community, dans le menu `A propos`
  - Ajout des informations nécessaires à la création d'un post sur community sur l'application
  - Possibilité de choisir une des 3 tailles sur les boutons d'actions des widgets
  - Possibilité de définir l'arrondi des boutons d'actions
  - Séparation des commandes infos et actions sur les équipements pour un visuel plus facile
  - Ajout de l'option `Modes dans la carte` pour les widgets `Thermostat` et `Climatisation`
  - Possibilité d'utiliser un fichier/image pour le scan du QR code
  - Petite refonte de la page `Préférence` de l'appli
  - Mise à jour des librairies de notification (dont compatibilité avec Android 12)  
  - Récupère l'intégralité des logs des plugins
  
- Bug fixes :
  - Boutons d'actions prennent maintenant la couleur du thème
  - Trie des widgets sur le bouton `Widgets supplémentaites`
  - Titre dans la barre du haut quand pas de menu bas
  - Positionnement des marqueurs sur les cartes
  - Statut du widget Lumière de couleurs
  - Position du badge sur l'icône Plugin
  - Rayon min pour définir un geofence à 30m
  - Fix compteur du badge de notification sur iOS
  - Fix crash avec l'horloge
  - Fix édition des widgets
  - Erreur lorsqu'un équipement JC n'a pas d'utilisateur qui lui est rattaché
  - Correction de la récupération de la valeur de la prochaine alarme
  - Ajoute la possibilité de ne choisir aucune sécurisation sur un widget scénario
  - Corrige l'affichage des choix disponibles d'un widget type `liste de choix` lorsqu'ajouté comme widget supplémentaire
  - Lancement à nouveau possible depuis le menu `Scénario`
  - Widget `Historique` prise en compte de l'intervalle défini dans le widget, et pas celui défini dans l'application (menu/pref/zoom)

## Version 1.0.0+1 (17/12/2021)

maj plugin uniquement !
fix mineur liens / documentation

## Version 1.0.0 (10/12/2021)

- Nouveautés :
  - Ajout d'un bouton `Infos Community` : ouvre une fenêtre qui affiche toutes les informations qui nous sont nécessaires lorsque vous créez un nouveau sujet sur le forum. Il vous suffit simplement de cliquer sur le bouton `Copier`, puis sur le forum coller ces infos. Tout est déjà préformaté !
  - Création de widgets en masse (depuis le plugin et depuis l'app !) : ces créations sont possibles uniquement si les commandes de vos équipements sont correctement configurées avec des types génériques (normalement à la charge des développeurs des plugins que vous utilisez).  
  Pour vérifier/modifier vos commandes avec les bons types génériques, vous pouvez utiliser le bouton `Config types génériques` <i>(pour les personnes qui seraient déjà en version beta/alpha sur le core de jeedom (4.2.x) vous pouvez utiliser `Outils/Types d'équipement`)</i>  
  L'outil peut détecter des widgets déjà existants, dans ce cas ils seront mis en surbrillance et décochés.  
  - Création de widget (unitaire) en automatique : si vous choisissez de créer un widget de façon unitaire, vous avez la possibilité de pré-charger les différentes commandes nécessaires pour le widget en cliquant sur le bouton `Création automatique` (même pré-requis que le point précédent) et en sélectionnant l'équipement qui sera utilisé pour créer le widget.  
  - Mode grille avancée (à activer dans `menu/préférences`) : permet de choisir la taille des widgets et les placer à l'endroit désiré sur l'écran. Vous n'êtes plus limité dans une grille standard de 3 ou 4 widgets par lignes avec tous les mêmes tailles, mais vous pouvez organiser chaque page comme bon vous semble, avec des espaces, des widgets grands, petits, longs, hauts, ...
  - Nouvelle fenêtre pour configurer les commandes `Notifier tous` sur la page principale du plugin
  - Widget `Climatisation` :
    - Possibilité d'ajouter autant de modes que voulu - **Obligation de re-créer les modes**
    - Possibilité pour la ventilation d'utiliser une info `string` et une action `select`
  - Ajout de la variable `#value#` dans les widgets compatibles
  - Pré-sélectionne automatiquement la pièce lors du choix des commandes en fonction de la pièce sélectionnée sur le widget
  - Notification iOs - Option pour qu'une notification arrive en `alerte critique` et possibilité de régler le volume du son (sonnera même si le son est coupé ou en mode `Ne pas déranger`)
  - Personnalisation possible de l'affichage forcée avec le nouveau mode `Grand widget`
  - L'historique est masqué si la commande n'est pas historisée
  - Personnalisation du statut pour la vue `Vignette`
  - Personnalisation des valeurs min/max sur les historiques
  - Affichage du `widgetId` dans l'application
  - Possibilité de dupliquer un widget
  - L'accès à la page de notifications ne requière plus d'être connecté
  - Possibilité de définir la mise en page des widgets dans un groupe (mode grille avancée)
  - Possibilité de configurer le nombre de positions stockées par la géolocalisation (0 pour désactiver la base : la position est alors envoyée immédiatement ou perdue à jamais)
  - Personnalisation des sous-titres en mode Grand widget (taille et couleur)
  - Possibilité de masquer l'aperçu dans la personnalisation
  - Ajout d'un lien `Changelog` dans la fenêtre `A propos`
  - Ajout des types génériques `Climatiseur` et `Géolocalisaton` (/!\ ces types sont propres à JC pour le moment)
  - Accès aux logs des scénarios et plugins depuis l'appli (uniquement pour les utilisateurs admin)
  - Widget `géolocalisation` : option pour définir le zoom par défaut, mode animation de la carte auto en option, et ajout d'un marqueur sur la dernière position sur un tracé
  - Widget `Modes` : option pour mettre les modes dans la contenu de la carte (plutôt qu'une modale)
  - Modification du menu `Mise à jour plugins` par `Plugins` : visualisation de l'ensemble des plugins dispo, documentation, et logs (uniquement logs principales pour le moment)
  - Possibilité de supprimer une image dans le dossier "images personnelles"

<details>
<summary>Nombreux Bug fixes</summary>
<p>

- Problèmes de connexion au démarrage
- Sauvegarde des notifications reçues
- Crash de la modale de partage des paramètres persos
- Son des notifications sous iOS
- Possible fix du problème d'appui sur widget sur iOS
- Envoie du niveau de batterie
- Animation des images au format gif
- Nombre d'éléments (comptage) dans les widgets groupe
- Affichage des infos supplémentaires dans la vue détails
- Accès aux images et vidéos dans les notifications avec l'URL locale si sur le réseau local
- Page de personnalisation du widget slider générique
- L'ajout de variables dans l'édition de textes se fait à la position du curseur
- Affichage des boutons de zoom ne reste plus grisés
- Le zoom de l'historique n'est pas changé en cas de nouvelles données dans l'historique
- Affichage des images dans un sous-dossier
- Affichage des badges sur les icônes dans le drawer
- Renfort sécurité pour la 4.2 : gestion des autorisations de téléchargements
- Clic long sur widget pour iOS
- Correction du contenu des sous-groupes lorsqu'il y a plusieurs colones
- Amélioration de la connexion
- Image du `groupe de PIR` qui reste "rouge" meme si le nombre d'alertes est à 0
- Widget mode : retrait de l'icone en doublon (était également affiché sur la valeur active)
- Sauvegarde de l'image de notification dès sa réception
- Fix animation décentrée des icônes FA
- Bouton lock/unlock dans le grand widget thermostat
- Problème d'affichage des widgets dans un groupe
- Les groupes désactivés sont masqués
- Empêche la connexion au websocket si connexion en cours
- Pas de polling si option activée mais en websocket
- Création de widget depuis l'appli était cassée (pas d'id affecté)
- Rafraichissement des images dans le widget `Images`
- Crash dans la grille principale si vide
- Fix ordre des infos supplémentaires
- Masquer prévisualisation de la carte en personalisation
- Amélioration du rafraichissement de tous les états
- Pleins d'autres petits bug corrigés, amélioration...

</p>
</details>
<br>

## Version 0.23.0 (07/10/2021)

- Nouveautés :
  - Nouveau widget `Historique` (graphique dans la grille)
  - Historiques : paramètres de personnalisation (couleurs, type de courbe, affichage par défaut...)
  - Nouvelle commande pour afficher un `Pop-Up` dans l'application (si JC n'est pas en cours d'utilisation [Android uniquement], alors on l'affiche à l'écran)
  - Widget `Géolocalisation` : affichage de la carte dans le widget en mode carte
  - Ask dans les notifications natives sur iOS
  - Notifications : suppression manuelle ou auto de notifications
  - Notifications : possibilité de filter par type de notifications
  - Changements graphiques du centre de notifications
  - Widget `générique action` : options d'affichage disponible en personnalisation
  - Ajout de la variable `#value#` dans le widget Volet
  - Affichage de commande(s) orpheline(s) sur les widgets (page principale du plugin, pas sur la page Jeedom !)
  - Ajout de la commande `Notifier tous les appareils JC` qui permet d'envoyer une notification commune sur les appareils éligible (case à cocher depuis l'assistant des notifications, sur les notifications à utiliser dans ce cas)
  - Ajout d'un système de logs dans l'application
  - Nouveau widget `Image` qui permet d'afficher une image à partir d'une URL ou une commande info
  - Nouvelle commande pour envoyer des SMS (Version APK seulement). Fonctionne quelque soit l'état de l'application
  - Nouvelles commandes action pour gérer les préférences de l'application depuis Jeedom (pour l'instant tracking, recharger les données)
  - Options de personnalisations des vues résumés de widgets
  - Mise en place du DeepLink (pour intéractions avec d'autres applis comme Tasker)
  - Mise à jour de (presque) toutes les libs de l'appli, et passage à React Native 0.65.1 (dont le moteur JS Hermes 20 à 30% plus rapide sur iOS)
  - Les commandes `Lancer App`, `Afficher page` et `Pop-Up` ne prennent plus en compte qu'un seul champ dans les scénarios (anciennement `message`). Si jamais vous utilisiez le champs `Titre` il convient de modifier légèrement votre scénario pour basculer les informations dans le champ `message`. (Si la modif a lieu après la maj du plugin, il convient de supprimer l'action et de la re-créer dans le scénario).
  - Ajout d'un délai possible entre deux authentifications
  - Ajout de la commande `Modifier Préférences Appli` : permet de modifier certaines options de votre application. Faites un choix dans la liste déroulante, puis indiquez la valeur à mettre si nécessaire : `ON`, `OFF`, `MARCHE`, `ARRET`
  - Prise en compte des options indiquées dans les notifications
  - Possibilité d'envoyer n'importe quel type de fichier dans les notifications
  - Ajout de l'option perso pour cacher le statut en mode carte
  - Amélioration de la connectivité
  - Envoie de l'utilisateur et du widget à chaque exécution de commande
  - Nombreux bug fix

## Version 0.22.0 (07/09/2021)

- Nouveautés
  - Page batteries / piles
  - Option pour activer le polling en http
  - Page Santé : permet de voir la page santé de votre jeedom, et gérer les démons de vos plugins : statut/start/stop (start/stop uniquement possible si l'utilisateur rattaché à l'équipement connecté appartient au groupe admin)
  - Page Mise à jour des plugins : permet de voir le nombre de mise à jour disponible sur vos plugins et réaliser tout ou partie de ces maj (maj uniquement possible si l'utilisateur rattaché à l'équipement connecté appartient au groupe admin)
  - Paramètres avancés pour la géolocalisation :
  - Sélection de l'affichage ou non du niveau de batterie de son équipement JC sur la page `Equipement` de votre Jeedom (et donc la page JC correspondante)
  - Edition des widgets depuis l'application (appui long sur un widget)
  - Paramètres personnalisés pour les widgets pour chaque appareil
  - Edition des menus depuis l'application (appui long)
  - Sauvegarde / restauration des paramètres de l'appli
  - Icônes / images : filtres et animations
  - Historique : possibilité de régler individuellement l'affichage en mode détaillé
  - Sécurisation des pages Préférences et Interface web
  - Vérouillage de l'interface
  - Possibilité de mettre une URL locale dans les webview
  - Couleurs en fond d'écran (image, dégradés, gestion de la transparence)
  - Couleurs ou image sur fond des widgets (avec ou sans conditions)
  - Choix des couleurs titre/sous-titre pour chaque widget
  - Gestion des pièces et des résumés depuis l'application (pensez à recharrger les données [menu préférences])
  - Bouton de ré-initialisation des paramètres perso dans chaque widget
  - Couleur de thème, plus de choix de couleurs, et mode auto noir/blanc
  - Groupe : choix de l'arrière plan (via l'appli)
  - Taille des titres et sous-titres pour chaque widget
  - Déplacement d'un widget ou d'un groupe à la place d'un autre widget
  - Titres et sous-titres sous conditions : possibilité de mettre du code JavaScript (ex: `#[Réseau][PC bureau][Online]# == 1 ? "En ligne" : "Hors ligne"`)
  - Personnalisation du fond d'écran en vue Détails (screenId=10), pour l'instant commun à toutes les vues Détails
  - Widget générique slider : mode Heure (format Jeedom, ex: 145 -> 01H45, 1805 -> 18H05)
  - Widget générique slider : accès boîte de dialogue avec slider en vue vignette
  - Widget générique actions : 2 nouvelles options pour personnaliser l'affichage
  - Widget Alarme : option pour les modes
  - Nouvelle option de personnalisation : masquer contenu de la carte
  - Option pour ajouter l'altitude, le type d'activité et le niveau de batterie à la commande de position
  - iOS : pastille de notifications non lues sur l'icône de l'appli
  - iOS : image / vidéo dans la notification native
  - iOS : actions rapides dans la notification native
  - Nombreuses corrections de bugs

## Version 0.21.0 (31/05/2021)

- Nouveautés appli :
  - Mode immersif (permet de masquer les barres de statut et de navigation d'Android)
  - Fond d'écran : possibilité de le définir avec des conditions sur la page courante ou de commandes.
  - Barre du haut : possibilité d'ajouter et trier des boutons de racourcis
  - Barre du haut : possibilité d'afficher horloge + météo (2 styles)
  - Menu haut : mode flotant
  - Menu du bas : possibilité de le positionner à gauche
  - Menu du bas : possibilité de mettre des images à la place d'icônes
  - Possibilité de choisir le mode d'action sur icône
  - Affichage modifié dans la page des préférences
  - Possibilité de sécuriser le démarrage de l'application par mot de passe ou empreinte biométrique
  - Possibilité de cacher les titres des menus bas
  - Changement d'organisation de la grille des widgets sur écran large
  - Nouvelle commande `Afficher page` : permet de naviguer vers une page de l'appli lorsque celle-ci est en premier plan
  - Nouvelle commande `Lancer app` qui permet de lancer une application lorsque l'appli est en premier plan (Android uniquement)
  - Nouveau widget `Lanceur d'application` qui permet de lancer une application (Android uniquement)
  - Option pour centrer les widgets
  - Authentification pour le flux caméra  
  - Mode launcher : Jeedom Connect peut se substituer à votre launcher Android
  - Page lanceur d'applications à ajouter dans les boutons de la barre du haut. Créez aussi des liens vers vos apps favorites (appuie long sur l'application, puis `ajouter/supprimer en favoris`)
  - Notifications :
    - Prise en charge dans l'application du code HTML des messages
    - Ouverture des liens dans le navigateur.
    - Boutons d'actions alignés verticalement
  - Widgets en mode vignettes : choix d'utiliser l'ancien ou le nouveau design  
  - Configuration : définir le trie des widgets par défaut (appliqué sur la page principale du plugin, et dans la liste déroulante de sélection des widgets sur l'assistant)
  - Niveau de batterie
  - Option pour n'afficher qu'une seule vignette par ligne

- Nouveautés plugin :
  - Vue d'ensemble qui permet de faire de l'édition de masse sur les widgets (uniquement sur les données communes)
  - Conditions des images plus flexible : possibilité d'enchaîner les conditions
  - Option pour ajouter l'altitude à la commande position
  - Conserve les filtres et ordres défini sur la page principale du plugin
  - Sur l'assistant widget : ajout d'un icone sur les widgets désactivés
  - Bouton export (format csv) sur la "vue d'ensemble" des widgets
  - Ajout d'une commande info pour le snapshot caméra
  - Assistant widget : ajout de filtres (pièces, présents) pour l'ajout de widgets
  - Nouvelle commande pour détacher l'appareil lié à un équipement
  - Bouton `Copier vers` qui permet de copier la conf d'un équipement vers un autre
  - Ajout de nouvelles fonctionnalités pour traitement en masse, cf [post dédié](https://community.jeedom.com/t/jeedom-connect-bloc-code-pour-realiser-diverses-operations/61818)

- Bug fixes :
  - Correction du timestamp pour les données de géolocalisation
  - Bug des sous-widget de la vue détail corrigé
  - Bug des widgets supprimés alors qu'ils existent dans un "widget parent"
  - Disparition des informations sur l'onglet équipement (après ouverture de la modale choix d'icone)
  - Affichage du texte complet dans les notifications
  - Point de géolocalisation correctement situé
  - Résumé avec un widget en double
  - Arrondis widgets humidité et luminosité
  - Modale du widget Mode scrollable
  - Cacher les éléments s'applique au mode carte
  - Crash de l'appli au démarrage
  - Rafraichissement de l'historique
  - Temps écoulé dans les groupes de widgets : prise en compte du plus récent changement
  - Alignement dans le widget résumé
  - Etat des scénarios en connexion http
  - Rotation écran après affichage d'une webview

## Version 0.20.0 (20/04/2021)

- Nouveautés :
  - Ajout du widget caméra !
  - Personnalisation des icones sur les résumés : nouveau menu "Résumé" à configurer dans l'assistant widget
  - Prise en compte des résumés "non-standard" (ie: ajoutés par l'utilisateur)
  - Prise en compte de tous les types `action message` dans le widget `Générique Action`
  - Prise en compte des tags dans le **widget** `Scenario`
  - Ajout de l'option "désactiver l'accélération matérielle" sur le widget Webview
  - Dans la vue vignette possibilité de cacher différents éléments : nom, sous-titre, status et/ou image
  - Ajout des vidéos dans les notifications
  - Clic sur l'icône de la vignette réalise une action : changement d'état d'une lumière/switch, générique action : déclenche la 1ère action paramétrée, ...
  - Modification de l'affichage des widgets
  - Affichage d'un widget en erreur, si sa configuration n'est pas bonne (il ne devrait plus y avoir d'écran blanc !)
  - Modification de l'affichage d'un slider : ajout des icônes + et - de chaque côté, et informations au-dessus du slider
  - Support du nouveau system de DNS Jeedom (automatique)
  - Boîte de dialogue `A propos`
  - `Drag & drop` l'ensemble des objets sur les assistants & widgets
  - Création automatique d'une sauvegarde de la définition des widgets à chaque backup de Jeedom
  - Affichage du nom de l'équipement en cours de modification (sur la modale assistant)
  - Ajout la possibilité d'intégrer d'autres widgets à l'intérieur d'un widget (sur la vue détail)
  - Ajout de l'`unité` sur les informations supplémentaires
  - Permet de définir le `pas` d'un slider (1 par défaut)
  - Permet de `cacher le titre` du widget à l'affichage sur l'application (mode carte)
  - Ajout d'une action automatique lorsqu'une page du menu bas est affichée (similaire au swipe Up ou Down, mais là systématiquement et automatiquement)
  - Prise en compte des `tags` pour les `scenario` sur les actions `SwipeUp`, `SwipeDown` et `Action` des menus bas
  - Commande Position : ajout de l'altitude (nouveau format :`latitude,longitude,altitude`)
  - Nouvelle commande info `Activité` (valeurs possibles : still, on_foot, running, on_bicycle and in_vehicle)
  - Possibilité de définir le type de connexion pour chaque équipement (http ou websocket). Pensez à re-générer vos QR-code

- Bug fixes :
  - Titres coupés dans menu haut sur One Plus
  - Effacement des notifications android lorsque l'on supprime les notifs dans l'application
  - Ordre des résumés de pièces
  - recherche des icônes non sensible à la casse
  - liste des widgets triées par ordre alphabétique

## Version 0.19.0 (01/04/2021)

- Nouveautés :  
  - SplashScreen qui pique pas les yeux  
  - Possibilité de sécuriser les action avec un code alphanumérique  
  - Possibilité de personnaliser le chemin des images persos (par défaut `plugins/JeedomConnect/data/img/user_files/`)  
  - Widget `liste de choix` (générique pour les commandes `action` sous-type `select`)  
  - Widget `générique message`  
  - Mode RTL (Right To Left) dans l'appli (on se refait le film à l'envers)
  - La barre de navigation Android (Retour, Accueil, Récent) s'adapte au théme sombre (si présent à l'écran)  
  - Thème sombre pour les cartes
  - Ajout d'une option pour masquer les historiques
  - Ajout d'une option pour définir le zoom par défaut sur les historiques

- Améliorations :  
  - Widget WebView :
    - accélération matérielle activée.
    - Login automatique sur les pages de Jeedom  
  - Meilleures performances sur l'Historique  
  - Lors de la suppression d'un widget, affichage du nom des équipements auxquels il est attaché
  - Widget fenêtre : Statut accepte les valeurs numériques maitenant (en + de binaire)
  - Toutes les actions d'un `générique action` sont affichées en mode carte

- Bug Fix :  
  - Correction des heures mal affichées ou avec retard d'une heure  
  - Correction des informations 'NaN' sur les titres/sous-titres
  - Alignement dans les widgets Favoris, Résumé, et dans les vignettes sans statut  
  - Interdictoin de sélectionner plusieurs fois la même pièce dans l'onglet du même nom  
  - Récupération des scénarios sur l'appli (via le menu)  
  - Fix historique sur le widget Géolocalisation
  - Fix icône thermostat
  - Fix crash possible au démarrage
  - Fix crash sur retour du webview

## Version 0.18.2 Beta ET Stable (18/03/2021)  

Dorénavant l'application (apk) sera disponible au téléchargement directement et uniquement sur le Store, aussi bien pour la version stable que pour la version bêta (dans ce dernier cas, un enregistrement est nécessaire -- [lire la doc](index.md#qBeta))  

- Changement du logo et du splash-screen
- Possibilité de passer en mode Vignette/Cartes sur la page des Pièces
- Accès aux notifications depuis l'icône 'Sonnerie' en haut à droite de l'écran
- Bug Fix :  
  - prise en compte de l'inversion des états pour les volets roulant

Côté plugin :

- Possibilité d'exporter & d'importer l'ensemble des widgets (sur page configuration du plugin)
- Ajout du lien d'inscription au programme bêta-testeur
- Bug Fix :  
  - importer plusieurs fois des fichiers à la suite

## Version 0.18.1 Beta (17/03/2021)  

- Bug Fix :
  - lors d'une modification d'un widget, l'application est mise à jour automatiquement
  - erreur sur le déplacement des widgets sans parent

## Version 0.18.0 Beta (15/03/2021)  

:information_source: Pré-requis (facultatif mais préférable !) : <b>AVANT</b> de mettre à jour le plugin, ouvrez l'assistant sur chacun de vos équipements, allez sur l'onglet `Pièces` et assurez vous que chacune des pièces créée est bien attachée à un objet Jeedom !  
Pensez également à mettre le plugin JeedomConnect en `DEBUG` !

:warning: Une fois la mise à jour effectuée, une migration manuelle est nécessaire pour faire fonctionner cette nouvelle version. <b>Merci de lire la [documentation](index.md#qMigration)</b> pour voir comment faire ! :warning:

- Refonte complète de la gestion des widgets :
  - création des widgets depuis la page principale du plugin
  - l'assistant disponible sur chaque équipement permet dorénavant de rattacher un widget existant à l'équipement
  - fonction de migration permettant de créer automatiquement tous les widgets d'une version précédente dans la version courante (sur la page de configuration)
  - ajout fonction de recherche sur les widgets : fonctionne sur le nom et sur l'id du widget (visible en info-bulles)

- Ajout du widget `Géolocalisation`

- Bug fix :
  - les commandes de chaque équipements sont déplaçables
  - amélioration de la performance sur la recherche des icônes (merci olivvv59)

- côté APK :
  - affichage d'un message plus précis sur la différence entre la version de plugin et celle de l'application
  - mise en place d'un pop-up pour télécharger la bonne dernière version de l'application directement

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
