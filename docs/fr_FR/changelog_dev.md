## Version 1.5.2 (28/10/2022)

* Nouveautés :
  * Refonte graphique de l'appli. Ajout de thèmes de couleurs et diverses options pour configurer l'apparence de l'interface
  * `Prochaine Alarme` : ajout d'un filtre pour ne récupérer la prochaine alarme du téléphone uniquement si elle fait partie d'une liste de programme que vous souhaitez récupérer.  
    Android ne permet toujours que de récupérer la PROCHAINE alarme prévue dans la system. Deux cas de figure donc :  
    * vous ne mettez pas de filtre => vous obtenez des maj de la cmde à chaque fois que la prochaine alarme est modifiée (sans vraiment savoir de qui elle vient)
    * vous filtrez par exemple uniquement sur les alarmes provenant du package "réveil" :
      * si la prochaine alarme est émise par ce package --> le plugin recoit la maj
      * si la prochaine alarme provient d'un autre package --> vous n'aurez pas la maj
    * Ajout d'une nouvelle commande `Package Prochaine Alarme` qui permet de savoir quel est le plugin qui déclenchera la prochaine alarme sur votre téléphone

  * `Notification multiple` : vous avez dorénavant la possibilité de créer plusieurs commande de type `Notifier tous` :  
    Vous pouvez par exemple définir un 'Notifier Tous - Enfants', 'Notifier Tous - Parents' et un 'Notifier Tous - Famille' --> en fonction du cas nécessaire vous appelerez l'une de ces commandes dans vos scénarios !

  * Création de la commande `Visibilité Menu` : qui permet de masquer/afficher un menu d'un équipement
  * Création de la commande `Visibilité Widget` : qui permet de masquer/afficher un widget sur <u>tous les équipements</u>

  * Regénération automatiquement du QR Code si nécessaire après la modification de l'équipement
  * Séparation par onglet des différents type des commandes pour y voir plus clair
  * Ajout d'un affichage de type `Jauge` sur les widgets `Générique numérique`, `Puissance` et `Prise`
  * Lorsqu'un widget est toujours présents sur la configuration de votre équipement mais n'est plus disponible sur votre installation Jeedom, alors il est automatiquement effacé
  * Déplacement de l'affichage du QR Code sur la page principale du plugin
  * Scanne du QR Code depuis l'application possible avec la caméra frontale
  * L'utilisation du JavaScript est possible sur le champ `statusText` d'un widget Générique Texte  
  * Mise sous condition d'affichage d'un widget ou d'un menu : vous pouvez définir si un élément peut être affiché en fonction d'une condition.
  * Dans le widget `Groupe géolocalisation`, un appui sur le nom d'un marqueur va vers sa carte dédiée
  * Ajout du paramètre `"Facteur de zoom` sur le widget `Groupe géolocalisation`

* Bug fixes :
  * Import de la configuration du plugin
  * Masquage de l'api key de JC dans les logs du démarrage du démon
  * Erreur lorsqu'un menu haut n'est pas rattaché à un menu bas
  * Récupération des applis de l'appareil dans certains cas
  * Envoi des actions (type `TTS`) lorsque l'appli est en background 
  