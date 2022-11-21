## Version 1.5.5 (dev en cours)

- Nouveautés :
  - Commande info `Volume actuel` pour connaitre les 6 différents volumes de son appareil (en fonction des OS et surcouche). La commande est valorisée par défaut avec l'ensemble des volumes disponible, selon le format suivant : `Alarme;Appel;Musique;Notification;Sonnerie;Système;`. Vous avez la possibilité de spécifier si vous ne souhaitez conserver qu'un seul type de volume et dans ce cas la commande renverra uniquement la valeur de ce type de volume. Dans le cas de `Toutes` les valeurs, ça sera à vous de vous créer un virtuel avec autant de commandes que vous souhaitez récupérer parmis les 6 types dispo.
  - Redesign page d'accueil pour afficher moins de menu

- Bug fixes :
  - Coquille sur le démon qui ne renvoie pas les messages d'erreur mais coupe simplement la connexion
  - Les actions `Mode sonnerie` et `Modifier Volume` ont été modifiées pour permettre le choix parmi une liste de valeur. Si vous avez réalisé des scénario avec la version 1.5.4 alors il vous faut les modifier pour prendre en compte ce changement
  - La commande `Modifier Volume` accepte la valeur "0" (avec les guillemets) de façon à forcer la valeur à 0
  - Suppression de la colonne `Notifier tous` dans la synthèse de équipement
