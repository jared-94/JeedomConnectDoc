# Documentation du plugin Jeedom Connect

<img src="../images/JeedomConnect_icon.png"  width="10%" />

Télécharger l'application (au format APK) en fonction de la version du plugin installé sur Jeedom [voir ici](#version)  


1. [Présentation du projet](#presentation)
2. [Fonctionnalités](#fonctionalites)
3. [Screenshots](#screenshots)
4. [Installation du plugin](#install)
5. [Configuration du plugin](#configurePlugin)
6. [Geston des Widgets](#gestionWidget)
7. [Ajouter des équipements](#addEq)
8. [Configuration d'un équipement](#configureEq)
9. [Géolocalisation](#geoloc)
10. [Matching entre les versions Application (APK) <=> Plugin](#version)
11. [FAQ](#faq)

## Présentation du projet <a name="presentation"></a>
Le projet **Jeedom Connect** se compose de 2 parties : un plugin pour Jeedom, et une application Android. Une version pour iOS pourra être envisagée plus tard.

L'application utilise la plupart des éléments de navigation d'une application : un drawer (menu dépliable sur la gauche), un menu bas, un menu haut, et des listes accordéon. Tous ceux-ci sont personalisables à partir du plugin.

La brique de base est la notion de *widget*, qui va représenter un "équipement domotique" (une alarme, une lumière, une info température...). Contrairement à l'application mobile officielle, Jeedom Connect n'ira pas chercher vos équipements / commandes pour vous les afficher directement. C'est à vous de définir un à un vos widgets. Ceci permet une flexibilité au niveau du rendu final.

Le plugin, ainsi que l'application sont complètement **gratuit** et le resteront. Je ne suis pas développeur et fais ça sur mon temps libre, relativement limité. Si vous souhaitez **soutenir le projet**, vous pouvez suggérer des améliorations, signaler des bugs et contribuer au code du plugin si vous avez des notions de PHP/JS/HTML, ou de l'application si vous maîtriser le React Native.

<br/><br/>

## Fonctionnalités <a name="fonctionalites"></a>
- Affichage et gestion de vos équipements domotiques et des scénarios
- Historiques sous forme de graphique ou tableau
- Possibilité de sécuriser toutes les action avec données biométriques
- Personalisation poussée de l'interface
- Notifications Push enrichies compatibles avec Ask
- [Géolocalisation](#geoloc) avec gestion avancée de la batterie (modes Geofencing et Tracking)
- Communication via le protocole WebSocket à faible latence, ou bien en HTTP
- Thème personalisable (couleur, mode sombre)

<br/><br/>  

## Screenshots <a name="screenshots"></a>
<img src='../images/JeedomConnect_screenshot1.png' width='200px' /><img src='../images/JeedomConnect_screenshot2.png' width='200px' /><img src='../images/JeedomConnect_screenshot3.png' width='200px' /><img src='../images/JeedomConnect_screenshot4.png' width='200px' /><img src='../images/JeedomConnect_screenshot5.png' width='200px' /><img src='../images/JeedomConnect_screenshot6.png' width='200px' /><img src='../images/JeedomConnect_screenshot7.png' width='200px' /><img src='../images/JeedomConnect_screenshot8.png' width='200px' /><img src='../images/JeedomConnect_screenshot9.png' width='200px' />

<br/><br/>  

## Installation du plugin <a name="install"></a>
Il s'installe depuis le market comme les autres.  

La version beta contient les nouveautés les plus récentes. (A noter que cette version peut contenir des bugs et reste à privilégier pour des utilisateurs expérimentés).


<br/><br/>  

## Configuration du plugin <a name="configurePlugin"></a>
Il y a plusieurs champs  pré-remplis que vous pouvez modifier. Des placeholder sont indiqués sur chacun d'entre eux. S'ils vous semblent corrects, inutile de les modifier.
* **Adresse http externe** : Indiquez ici votre adresse d'accès à Jeedom depuis l'extérieur de votre domicile.
* **Adresse http interne** : Adresse de Jeedom sur votre réseau local.
* **Activer la connexion par Websocket** : Indiquera à l'application si vous préférez utiliser le protocole Websocket pour la communication avec vos appareils. Notez tout de même que l'adresse HTTP est nécessaire au bon fonctionement de certains services (images persos, géolocalisation, actions sur notifications)
* **Port d'écoute du websocket** : Sauf si vous avez une application qui utilise ce port, vous n'avez pas besoin de le modifier. En cas de modification, n'oubliez pas de redémarrer le démon.
* **Adresse externe websocket** : Adresse websocket accessible depuis l'extérieur (nécessite une configuration de votre réseau)
* **Adresse interne websocket** : Adresse websocket sur votre réseau local

Si vous modifiez un de ces champs, il faudra bien sûr sauvegarder, puis re-générer les QR Code des équipements. En cas d'utilisation du HTTP, il faudra aussi redémarrer l'appli.

<br/><br/>  

## Page principale du plugin JeedomConnect <a name="gestionWidget"></a>  

La page principale du plugin se décompose en deux parties :     
1. Sur la partie haute, vous pourrez voir et gérer [vos équipements](#addEq) (appareil muni de l'application JeedomConnect)
2. Sur la seconde partie : vous aurez accès à l'ensemble de [vos widgets](#gestionWidget) et pourrez les modifier à souhait. 

<img src="../images/plugin-home.png"  width="50%" />


<br/><br/>  

## Gestion des widgets <a name="gestionWidget"></a>

Il est nécessaire de commencer par créer un widget pour ensuite pouvoir le rattacher à un (ou plusieurs) équipement(s).  
Sur la page principale vous avez accès à l'ensemble des widgets que vous avez créé. Il est possible de les filtrer par type et de les classer (par Pièces, Nom, ou Type).  

Pour créer un widget, cliquez sur "Ajouter un widget", sélectionnez ensuite le type de widget que vous souhaitez créer dans la liste déroulante de gauche puis renseignez les différents champs affichés à l'écran avant de finaliser la création en appuyant sur le bouton "Sauvegarder".  

Quelques éléments sont standard et seront demandés pour l'ensemble des widgets :  
   * **Actif** : Le widget sera (ou pas) affiché dans l'application. Pratique si vous voulez par exemple gérer un groupe de lumières, mais ne pas afficher certaines d'entre elles.
   * **Pièce** : Sélection de la pièce associée (identique aux objets gérés dans Jeedom)
   * **Nom** : Nom du widget
   * **Sous-titre** Information complémentaire affichée dans l'application. Le mode personalisé permet de mettre une phrase quelconque, avec certains "mots-clé", généralement `room`, `value`, `formatedValue`, `elapsedTime`, `power`.   
   Par exemple :  
   `Mon ampoule est formatedValue depuis elapsedTime et consomme power W`  
   donnera :  
   `Mon ampoule est allumée depuis 1h12min et consomme 15W`  
   * **Affichage forcé** : De façon standard, chaque widget (sauf exception) possède 3 types d'affichage : carte, vignette et détail. Les affichages carte et vignettes peuvent être choisis via l'icône en haut à droite dans l'application. L'affichage détail est une page entière affichée quand on click sur le widget. Vous pouvez ici forcer un widget à s'afficher d'une de ces 3 façons.  
   Attention pour le mode détail, le widget doit être seul sur sa page.
   * **Sécuriser les actions** : Toutes les commandes de type action peuvent être sécurisées à l'aide de ces deux boutons :  
     ![](../images/screen-secureBtn.png)   
   Le premier permet de faire une simple demande de confirmation de l'action.  
   Le second demande l'empreinte digitale pour exécuter l'action (sur appareils disposant d'un capteur)
   * **Images** : Les images de l'application sont stockée dans le dossier `plugins/JeedomConnect/data/img/`. Si vous souhaitez ajoutez des images persos, utilisez l'assistant, ou bien copiez vos images dans `plugins/JeedomConnect/data/img/user_files/`. Il est conseillé d'utiliser des images PNG en 128x128. Vous pouvez aussi mettre des GIF animés.
   * **Images sous conditions** : Vous pouvez dans certains widgets définir une image en fonction des valeurs d'une commande. L'ordre des ces condition sera prise en compte par l'appli (les plus hautes sont prioritaires).  
   * **Ajouter des infos** : vous permet d'ajouter des commandes de type `info` de votre Jeedom et de vous en servir pour les autres champs du formulaire 'Images sous conditions', 'Nom', 'Sous-titre'.

La duplication d'un widget est réalisable dès que celui-ci a été sauvegardé une première fois. Cliquez simplement sur le bouton "Dupliquer", réaliser vos modifications (ou pas), et enregistrer (impérativement) en validant avec le bouton "Sauvegarder".  

La suppression est également possible. Attention toutefois, si un widget est supprimé, alors il disparaitra de l'ensemble des équipements auxquels il avait été ajouté !  


* ### Widgets disponibles  


|  |  |  |
|------|-----|-----|
|Lumière On/Off|Lumière à variation|Lumière de couleurs|
|Groupe de lumières|Prise|Groupe de prises|
|Scénario|Résumé|Résumé de pièce|
|Favoris|Luminosité|Humidité|
|Température|Puissance|Thermostat|
|Climatiseur|Porte|Groupe de portes|
|Fenêtre|Groupe de fenêtres|Portail coulissant|
|Volet|Groupe de volets|PIR|
|Groupe de PIR|Alarme|Groupe d'alarmes|
|Générique binaire|Groupe de génériques binaires|Générique numérique|
|Générique texte|Générique switch|Générique slider|
|Générique actions|Mode|Web View|
 

<br/><br/>  

## Ajouter des équipements <a name="addEq"></a>
Vous pouvez ajouter des équipements dans le plugin de façon standard.

1 équipement = 1 appareil muni de l'application

![](../images/screen-eqConfig.png)

A la création d'un équipement, une clé API, ainsi qu'un QR Code est automatiquement généré avec les informations de configuration du plugin. Lors du démarrage de l'application, vous pourrez alors entrer manuellement vos identifiants jeedom, ou bien scanner le QR Code. Une fois connecté, l'équipement et l'appareil sont liés. Pour vous connecter avec un autre appareil, il vous faut le *détacher*  en cliquant sur le bouton associé.

La configuration d'un équipement consiste en un fichier JSON configurable avec l'assistant, et que vous pouvez exporter / importer. Si vous voulez par exemple cloner un équipement, ajoutez en un nouveau et utiliser l'exportation / importation.  

Le dernier bouton permet lui de transmettre votre fichier de configuration complet, en cas de problème, au développeur. Ce fichier ne DOIT PAS être importer sur un autre équipement JeedomConnect.  

<br/><br/>  

## Configuration d'un équipement <a name="configureEq"></a>
La configuration du contenu de l'application se passe dans l'assistant.

Le changement de configuration a lieu à chaque click sur le bouton *Sauvegarder*. Si l'application est démarrée, elle est automatiquement transférée (websocket uniquement). Vous pouvez recharger la configuration dans l'appli en appuyant sur le logo du 'menu hamburger'.  
Si vous pensez avoir une erreur avant d'avoir sauvegarder (par exemple supprimé un élément par erreur), actualisez simplement la page. Le bouton *Réinitialiser* (suivi de *Sauvegarder*) remet toute la configuration à zéro, attention donc !

<br/>  

* ### Menu du bas

![](../images/screen-assistantBottom.png)

Cette partie est assez explicite, elle permet de configurer les onglets qui apparaissent en bas de l'écran. Vous avez la possibilité de choisir vos icônes parmis tout un panel : celles de Jeedom, celles proposées par Material Design, ou encore sur Font Awesome(un moteur de recherche est intégré).  
La configuration de cette partie est optionnelle, et n'est à réaliser que si vous souhaitez utiliser ces onglets.

<br/><br/>  

* ### Menu du haut
 ![](../images/screen-assistantTop.png)

 Cette partie est également explicite. Un menu sous forme d'onglets en haut de l'écran que vous pouvez 'slider'. Egalement facultatif.

<br/><br/>  

* ### Pièces
 Chaque widget peut être associé à une pièce à ajouter dans cette partie.  Chaque pièce correspond à un objet Jeedom.  

<br/><br/>  

* ### Widgets
 ![](../images/screen-assistantWidgets.png)
 Définissez d'abord l'emplacement où placer le widget : sur quel menu / sous-menu que vous voulez le configurer.   
 Vous pouvez ensuite filtrer sur le type de widget que vous allez ajouter (ne sont proposés que les types de widget déjà créés).  
 Sélectionnez le widget que vous souhaitez ajouter, puis enfin cliquez sur le **Ajouter ce widget** pour l'ajouter à votre configuration.  
 * **Ajouter un groupe** : Vous pouvez ranger vos widgets dans un menu dépliable (type "acordéon").  
   * **Actif** : Le groupe sera (ne sera pas) affiché dans l'application.
   * **Développé par défaut** : Le comportement par défaut (plié / déplié) du menu.  
  <img src="../images/screen-groupConfig.png" width="25%" />
 
 Différentes actions sur possible sur chaque élément :  
 <img src="../images/btn-action-widget.png" width="20%" />  
 * les flèches bleues permettent de changer la place du widget par rapport aux autre widgets sur la même page : le monter ou le descendre  
 * le moins rouge permet d'enlever le widget de la page (ça ne supprime pas le widget dans Jeedom)
 * la flèche verte (vers la droite) permet de déplacer le widget sur une autre page  

<br/><br/>  

## Géolocalisation <a name="geoloc"></a>
Jeedom Connect dispose d'une fonction de Geofencing : définissez des lieux géographiques sur une carte et des commandes binaires seront créées dans votre équipement vous indiquant si l'appareil est dans ce lieu ou pas.

Commencez par ouvrir l'application et rendez-vous dans les Préférences puis activez la géolocalisation.  
<img src='../images/screen-geo1.png' width='200px' />
<img src='../images/screen-geo2.png' width='200px' />
<img src='../images/screen-geo3.png' width='200px' />

Pour le bon fonctionnement du service, il est impératif d'accepter toutes les autorisations, en particulier la `Localisation` doit être sur `Toujours autoriser` (Android 10+)

Vous pouvez ensuite aller sur `Gestion des lieux`.
- Pour **définir une zone**, faites un appuie long sur la carte puis donner un nom et un rayon (en mètres). Le binaire est immédiatement créé côté Jeedom.
- Pour **supprimer ou éditer une zone**, appuyez sur le marqueur puis sur le nom qui apparait.
- Pour **déplacer une zone**, faites un appuie long sur le marqueur puis glisser.
Jeedom Connect possède aussi une fonction de Tracking qui vous permet de connaitre à tout moment la position de votre appareil. Les coordonnées GPS (latitude,longitude) sont accessibles dans la commande `Position` de votre équipement.

<br/><br/>  

# Matching version Application (APK) <=> version Plugin sur Jeedom <a name="version"></a> 

L'apk est téléchargeable en cliquant sur le numéro de version.

## Version Stable 

|Version plugin |Version Application  |
|------|-----|
|0.16.0 (22/02/2021)|[0.16.0](https://github.com/jared-94/JeedomConnect/releases/download/0.16.0/JeedomConnect-0.16.0.apk) |

<br/>  

## Version Beta 

|Version plugin |Version Application  |
|------|-----|
|0.17.1 (05/03/2021) | [0.17.1](https://github.com/jared-94/JeedomConnect/releases/download/0.17.1/JeedomConnect-0.17.1-beta.apk)  |
|0.17.0 (04/03/2021) | [0.17.0](https://github.com/jared-94/JeedomConnect/releases/download/0.17.0/JeedomConnect-0.17.0.apk)  |

<br/>  

## Lien github générique 

https://github.com/jared-94/JeedomConnect/releases/latest

<br/><br/>  

# FAQ <a name="faq"></a> 
  
  * [Comment télécharger l'application ?](#qOU) 
  * [J'ai un Iphone, comment utiliser l'application ?](#qIphone) 
  * [L'application m'indique "Merci de migrer votre configuration"](#qMigration) 
  * [J'ai l'erreur suivante "Cette application requiert une version plus récente du plugin"](#qVersion) 
  


---
  
## Comment télécharger l'application ? <a name="qOU"></a>   

L'application est pour le moment uniquement disponible sur Android.  
Sa publication sur le Store est encore en cours de validation, en attendant il est nécessaire de passer par un téléchargement et une installation manuelle.  

<br/>

## J'ai un Iphone, comment utiliser l'application ? <a name="qIphone"></a>  

Pour l'instant il n'est pas possible d'utiliser l'application JeedomConnect sur Iphone.  
Le développement de l'application est bien prévu, mais non réalisé pour le moment.  
Aucune date n'est annoncée sur la sortie de celle-ci, mais dès que ce sera possible une communication sera faite sur le forum !

<br/>

## L'application m'indique "Merci de migrer votre configuration" <a name="qMigration"></a>  

La mise à jour que vous venez de réaliser nécessite une mise à jour au niveau du fichier de configuration utilisé pour définir vos widgets.  
Que va faire cette opération ? Elle va lire votre(vos) fichier(s) de configuration et créér automatiquement tous les widgets correspondant.  
:warning: si vous avez plusieurs équipements (téléphone/tablette/...) de configurer, il y a de forte chance que l'opération créé des widgets en doublon (ou plus).  
Deux choix s'offrent à vous :  
  1. migrer UN seul de vos équipement (appareil), exporter sa configuration puis l'importer sur tous vos autres équipements :  
      * le + : pas de widgets créés en doublons, pas de longue suppression manuelle à réaliser    
      * le - : si certains de vos appareils ont des widgets bien à eux, il faudra alors les recréer manuellement  
  2. migrer l'ensemble de vos équipements :  
      * le + : tous les widget seront créés automatiquement
      * le - : chaque équipement étant migré comme s'il était seul, certains widgets seront créés en doublon. Vous aurez donc besoin de faire un peu de ménage en modifiant les configurations de certains équipements puis en supprimant les widgets inutiles en doublon.   

Nous préconisons la solution #1 ! Voici comment nous vous proposons de faire : 
* désactiver l'ensemble de vos équipement sous le plugin JeedomConnect, et n'en laisser qu'<b>UN SEUL actif</b> (le plus utilisé, ou celui qui contient le plus de widgets)
<img src='../images/JC_disableEq.gif' width='50%' />  

* rendez-vous sur la page `configuration` de votre plugin (Menu `Plugins/Gestion des plugins/Jeedom Connect`)  
<img src='../images/JeedomConnect_configuration.png' width='600px' />  

L'option `Migration des configurations` va vous aider à réaliser cette mise à jour.  
* sélectionnez le choix `uniquement les équipements actifs`  
* cliquez sur le bouton `Migrer`  
Un message de confirmation vous indique que tout s'est bien passé !  
Vous pouvez retourner sur votre page principale du plugin JeedomConnect et vous devriez voir quelques changements : l'ensemble de vos widgets sont maintenant disponible directement sur cette page.  
* vous pouvez maintenant ouvrir la configuration de votre appareil, faire un `export` de la configuration, puis sur chacun de vos autres équipements `importer` cette configuration, puis réactiver vos équipements.

<br/>

## J'ai l'erreur suivante "Cette application requiert une version plus récente du plugin" <a name="qVersion"></a>   

Pour fonctionner, il faut que le plugin installé sur Jeedom et l'application (APK) que vous avez téléchargé et utilisé soit alignés.  
Notez vos différentes versions et rendez-vous sur le [tableau de versions](#version) pour vérifier votre installation, et connaitre l'élément à mettre à jour.  

La version du plugin est disponible sur la page de `configuration` du plugin :  
<img src='../images/JC_pluginVersion.gif' width='30%' />  
<br/>
La version de l'application est disponible sur la page de connexion :  
<img src='../images/JeedomConnect_VersionApk.jpeg' width='30%' />  
ainsi qu'en bas de la page `Préférences` (dans la menu de l'application) :  
<img src='../images/JC_getAplVersion.gif' width='30%' />  