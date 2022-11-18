## Version 1.5.4 (dev en cours)

* Nouveautés :
  * Gestion des notifications depuis l'application
  * Centre de notifications : option pour centrer le contenu
  * Nouvelles commandes dans le plugins :
    - `Mode sonnerie` *[Android]* : Permet d'activer un mode de sonnerie `Silencieux`, `Normal` ou `Vibreur`. 
    - `Volume` : Permet de régler le volume de l'appareil (en %). Pour Android, vous pouvez spécifier en plus dans champs `Titre` de la commande le canal audio à modifier
  * Maintient de l'écran allumé en plein écran pour une caméra
  * Possibilité de changer de thème depuis une commande Jeedom
  * Possibilité de télécharger le QR code de connexion depuis l'application

* Bug fixes :
  * Problème avec l'authentification au démarrage sur iOS 
  * Crash lors de la sélection du style d'horloge
  * Exécution et affichage dans les widgets `Choix de listes` et `Mode`
  * Suppression du cache sous iOS
  * Accès à l'historique d'une info supplémentaire
  * Mode sombre automatique au retour de background
  * Rechargement du widget `Webview` au retour de background
  * Utilisation de la commande `Puissance` dans la jauge du widget `Prise`
  * Boutons de la barre du haut qui s'affichent au dessus de l'horloge
  * Affichage d'une notification Ask sans options
  * Images sous conditions dans les widget de lumières
  * Autorisations de notifications pour Android 13
