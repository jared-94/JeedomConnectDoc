## Version 1.7.1 (dev en cours)

- Nouveautés :
  - Grille avancée : Lors de l'édition, possibilité de figer les éléments pour configurer le verrouillage et la profondeur des éléments
  - Refonte des historique pour plus performances, et nouvelles options, affichage des statistiques
  - Nouveau widget `Groupe d'historiques` : affichage de plusieurs historiques dans un seul graphe
  - `Widget Caméra` : possibilité de faire du pinch-to-zoom ou double-tap
  - Composants : ajout du champs `Pièce`
  - [Android] Nouvelle commande action `Effacer les données`, utile en cas de perte ou vol de l'appareil. Pour confirmer l'action il faudra saisir le mot `erase` sur le champs correspondant.
  - Ajout du paramétre `Visibilité sous condition` dans les personnalisations des widgets
  - Passage en mode `Hors connexion` dès que l'équipement est désactivé sur Jeedom
  - Changement de la structure de données des éléments (et nettoyage du code). Attention si vous avez des blocs code et faites des changements vous même il se peut que certaines choses ne fonctionnent plus...

- Bug fixes :
  - Amélioration du temps d'ouverture sur l'édition d'un élément
  - Correction de l'action d'activation du geofence  
  - [iOS]: couleur de l'aiguille de la jauge
  - Crash sur la jauge lorsque la valeur est supérieur au max défini
  - Rendu de la jauge et slider circulaire qui disparait
  - Crash dans le slider lumières de couleurs
  - Augmentation du timeout sur les requêtes http
  - Composant `Séparateur` prend toute la largeur sur écran large
  - Marges des widgets dans un groupe
