### Création d'un scénario

Un scénario est défini dans un fichier `.csv`.

Un exemple de scénario vous est fourni [ici](./exemple.csv).

Une liste sera de la forme : ```element1 / element2 / element3 ...``` (les `/` peuvent ne pas être entourés d'espaces)

Une liste de liste sera de la forme : ```[liste1] / [liste2] / [liste3] ...``` (les `/` peuvent ne pas être entourés d'espaces)

Un scénario défini :
- un inventaire de départ composé d'une liste de matériel
- un statut de départ composé d'une liste de statut
- un lieu de départ
- une intéraction par défaut avec un objet de la forme : ```"ch1" + verbe + "ch2"``` où ```verbe``` sera automatiquement remplacé par le verbe de l'action demandée, ```ch1``` et ```ch2``` seront 2 chaînes de caractères potentiellement nulle.
- une réponse à l'action 'fouiller' par défaut sous la forme d'une chaîne de caractères.
- les lieux :
    - son nom sous la forme d'une chaîne de caractères
    - ses statuts de base sous forme de liste
    - ses indices sous la forme d'une liste
    - ses sorties possibles sous la forme d'une liste de lieux
    - les objets présents dans ce lieu sous forme de liste
    - les personnages présents dans ce lieu sous forme de liste
    - les objets des personnages sous forme de liste de liste **:warning: faire attention à garder le même ordre que les personnages**
    - les statuts des personnages sous forme de liste de liste **:warning: faire attention à garder le même ordre que les personnages**
    - des blocs d'action possibles :
        - un champ action contenant le nom de l'action de la forme : 
            - ```description``` : action spéciale exécutée automatiquement à l'entrée de chaque lieu
            - ```fouiller lieu``` : sera exécuté à la place de la réponse par défaut donnée en début de fichier
            - ```verbe objet``` : sera exécuté à la place de la réponse par défaut donnée en début de fichier
            - tout autre forme n'aura pas d'action supplémentaire à celles du bloc
        - un champ condition de l'action de la forme :
            - ```entité a objet``` / ```entité a pas objet``` / ```entité possède objet``` / ```entité possède pas objet``` : vérifie si l'entité (lieu, personnage ou joueur) possède l'objet dans son inventaire.
            - ```entité est statut``` / ```entité est pas statut``` : vérifie di l'entité (lieu, personnage ou joueur) a ce statut
            - ```entité dans lieu``` / ```entité pas dans lieu``` : vérifie que le joueur ou un personnage est dans un lieu.
            - ```cond1 et cond2``` : vérifie si les conditions sont toutes les deux valides.
            - ```cond1 ou cond2``` : vérifie si au moins une des condition est valide.
            - une condition peut être entourée de parenthèses ```(cond1)``` pour pouvoir être prioritaire sur son évaluation sinon les ```et``` seront prioritaires sur les ```ou```. Notez que des espaces peuvent être ajoutés avant ou après les parenthèses.
        - un champ réaction sous la forme de chaîne de caractères qui sera affichée lors de l'exécution de l'action.
        - un champ entité affectée : le nom de l'entité (joueur, personnage ou lieu) dont on veut changer les statuts, son inventaire ou encore sa localisation. Notez que si c'est un changement de lieu, ce champ doit obligatoirement être le joueur.
        - un champ status + sous la forme de liste de statut permettant d'ajouter des statuts à l'entité ciblée. Si le statut ```mort``` est ajouté au joueur, il perd la partie. Si le statut ```victoire``` est ajouté au joueur, il gagne a partie.
        - un champ status - sous la forme d'une liste de statut permettant de retirer des statuts à l'entité ciblée. Notez que si un status - n'est déjà pas présent sur l'entité, rien ne se passera pour ce statut mais les autres seront quand même pris en compte.
        - des champs objets +, objets - sous la forme de liste d'objets permettant d'ajouter ou de retirer des objets à l'entité ciblée. Notez que si un objet - n'est déjà pas présent sur l'entité, rien ne se passera pour cet objet mais les autres seront quand même pris en compte.
        - un champ changement de lieu permettant de faire changer le joueur (obligatoirement) de lieu.
        - **Note :** des mots clés sont à disposition tel que ```moi``` pour parler du joueur et ```lieu``` pour parler du lieu actuel.
    - Notez que chaque bloc d'action est dans la colonne d'un lieu et donc ne peut s'exécuter dans celui-ci. Cela rajoutera à chaque action la condition ```moi dans lieu``` automatiquement.
