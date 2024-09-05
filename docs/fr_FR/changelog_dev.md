## Version 1.10.2 (dev en cours)
  
- Nouveauté
  - Nouvelle méthode authentification possible sur les snapshots du widget `Caméra` : `digest`

- Bug fixes
  - Correction API Google v14
  - Picovoice :
    - creation d'un nouveau wakeword, aboutit sur une erreur dans l'app.
    - wakeword ne fonctionne plus
  - Sous titre d'un widget `binaire` : un sous titre composé d'infos vide montre "" <https://community.jeedom.com/t/vider-une-commande-info-type-autre-avec-event-affichage-etrange/127368?u=tomitomas>
  - Typo : corrections typo orth diverses
  - Option pour mettre l'arrière plan d'un widget en mode dégradé ou non (android, déjà présent sur ios)
  - Widget `Portail` : le sous-titre `temps ecoulé` ne fonctionne pas
  - Choix par défaut lors de la création de certain widget
  - Widget `Résumé de pièce` : le choix `Global` n'est pas dispo dans l'appli
  - Slider : sous ios il n'est pas possible de personnaliser le pas puisqu'un point est attendu, mais le clavier ios ne propose qu'une virgule
