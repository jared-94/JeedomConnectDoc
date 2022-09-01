## Version 1.4.2 (dev en cours)

* Nouveautés :
  * Websocket :
    * Gros chantier et refonte complète de la connexion en websocket pour la rendre plus performante et ne plus avoir d'état incohérent entre Jeedom et JC.  
    Il pouvait arriver que le statut d'un plugin diffère entre Jeedom et JC, qu'une commande ne s'éxécute pas, etc ...  
    Ces problèmes étaient liés à un cache sur le démon écrit alors en php. Nous avons ré-écrit les différents modules et sommes passés en Python pour ne plus avoir ces soucis.  
    Un nouveau paramétre peut être modifié dans la configuration `Port Socket Démon` qui permet la communication entre Jeedom et le démon (par défaut `58090`). Alors que le `Port Websocket JC` est celui qui est utilisé pour ouvrir une connexion entre chaque application JC et le démon (inchangé, par défaut `8090`).
    * Il sera dorénavant à nouveau possible de mettre à jour le plugin JC depuis son application, même si on est connecté en websocket
    * Nouvelles règles pour le démon :
      * automatiquement arrêté si aucun équipement n'est configuré pour utiliser le websocket
      * non démarrable si aucun équipement n'est configuré pour utiliser le websocket
      * démarré si depuis l'application on décide de faire passer son équipement en websocket et que le démon est stoppé
      * redémarré automatiquement si un champ de configuration essentiel est modifié (à la sauvegarde de la configuration)

  * Géolocalisation :
    * Widget `Géolocalisation` : vous pouvez lui donner un petit nom à afficher
    * Création d'un nouveau widget `Groupe de Géolocalisation` : permet d'afficher plusieurs points de géolocalisation sur un seul widget
    * Affichage d'un message d'info si aucun équipement n'est paramétré pour être affiché sur la carte/widget `Localisation`
    * Possibilité d'afficher le traffic routier sur la carte
    * Possibilité d'afficher l'historique des positions (limitée aux 1000 derniers points)

  * Général - Côté plugin :
    * Revamping de la page `configuration` du plugin
    * `Générique action` : pour les commandes de sous-type message option supplémentaire pour `Afficher/masquer le titre` ou `garder le dernier message` (comme sur le `générique message`)
    * Contrôle de cohérence version plugin/application : beta/beta ou stable/stable, pas de mix

  * Général - Côté app :
    * Ajout d'un contrôle pour vérifier que les versions de l'application et du plugin sont bien alignées : beta/beta ou stable/stable
    * Ajout d'une option pour sauvegarder automatiquement la configuration de l'application (est réalisée lors du démarrage de l'appli)
    * Ajout d'une option pour recharger automatiquement la configuration Jeedom (est réalisée lors du démarrage de l'appli)
    * Inversion possible des sliders dans les paramètres personnalisés :
      * horizontal : droite <-> gauche
      * vertical : haut <-> bas
      * circulaire : horaire <-> antihoraire
