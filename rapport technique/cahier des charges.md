# Cahier des charges

## Mécaniques du jeu :
- Moteur génératif, l’application devra permettre de lancer un scénario à partir d’un fichier csv (ou template d’un autre format à définir) ; mais aussi de jouer les parties implémentées via le template
    - La partie Motrice de l’application devra être simple et ne nécessiter qu’un upload du template
        - Le template devra correspondre à un standard bien précis avec :
            - Situation de départ
            - Situation de résolution
            - Condition(s) de résolution (fin de partie réussie)
            - Condition(s) d’échec critique (fin de partie)
            - Objets d’interaction (matériel, personnage, lieu)
            - Gestion d’inventaire (apparition / retrait d’objet)
            - Déplacements possibles
            - Actions autorisées (sous forme de liste fournie ou non)
            - Proposition d’indices d’aide
            - Sauvegarde de partie
            - Reprise de partie à la sauvegarde (en cas d’échec)
        - La partie Générative de l’application proposera un jeu d’aventure textuel (pas d’affichage autre que du texte, et pas d’implémentation d’actions autres que du texte)
        - Il peut être envisagé (facultatif) un calcul de score de réussite en fonction de l’atteinte d’objectifs, du nombre de sauvegarde, le nombre d’indices utilisés et du nombre de reprise du scénario après échec
    - Langage de programmation
        - Il est laissé à l’appréciation des étudiants ou de l’encadrement de Polytech
    - Aucune spécificité n’est demandée concernant :
        - Les graphismes : aucun n’est prévu
        - Le mode multijoueur : un seul Personnage-Joueur est joué. Il peut l’être en même temps par plusieurs joueurs devant leur écran, qui discutent de la meilleure marche à suivre
        - Les sons ou la musique : aucun n’est prévu
        - L’IA : la ligne scénaristique est écrite et ne nécessite aucun ajustement

## Liste de fonctionalitées:
- charger un scénario
- lancer un scénario
- sauvegarder ca partie
- reprendre une partie sauvegardé
- présenter la situation actuelle
- connaitre son environement
- connaitre son inventaire
- intéragir textuellement
- éffectuer des déplacement
- éffectuer une actions
- reconnaitre des verbes prédéfinis
- obtenir un indice
- évaluer la réussite de la partie
- obtenir un score de réussite
- traduction

### Liste des contraintes:
- sous forme d'extension moodle