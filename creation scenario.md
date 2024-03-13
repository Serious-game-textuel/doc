# ENGLISH

## Scenario creation

A scenario is creating with a CSV file. You will find an example with the file ```example.csv```.

***Note* : Some cells will contain lists. They have the following syntax : ```elem1 / elem2 / elem3```. It it possible to write lists with 0 or 1 element.**

### General Properties

- ```Interaction with non-existent object``` : TODO
- ```Search by default``` : TODO
- ```Language``` : EN (It is possible to choose FR. In this case, please follow the French version of this tutorial and the French CSV template.)

### Items

One column at a time, each item is represented by 3 features :
- its name
- its description
- its initial statuses [list]

### Characters

One column at a time, each character is represented by 4 features:
- its name
- its description
- its initial statuses [list]
- its initial items [list] (Warning: in this list, each item name must have been written in the table concerning items)

**Important** :
- the player is a character and its name must be ```player```
- when this character obtains the status ```dead```, the player loses the game
- when it obtains the status```victory```, the player wins

### Locations

One column at a time, each location is represented by 6 features :
- its name
- its initial statuses [list]
- its initial items [list] (Warning: in this list, each item name must have been written in the table concerning items)
- its initial characters [list] (Warning: in this list, each character name must have been written in the table concerning characters)
- its hints [liste]
- its actions (These are detailed in the next section)

### Actions

Each action is attributed to a location. To do so, a block must be filled in the column the correspondant location.

A block (action) is represented by 9 features :
- its name (this is what the player will write to execute an action)
- its condition (expression determining if an action can be performed)
    - a simple condition follows one of the following syntaxes :
        - ```Location``` is ```Status```
        - ```Location``` is not ```Status```
        - ```Location``` has ```Item```
        - ```Location``` has not ```Item```
        - ```Location``` has ```Character```
        - ```Location``` has not ```Character```
        - ```Character``` is ```Status```
        - ```Character``` is not ```Status```
        - ```Character``` has ```Item```
        - ```Character``` has not ```Item```
    - the expressions ```has``` et ```has not``` assert that :
        - a location has or not un a character or an item
        - a character has or not an item
    - the expressions ```is``` et ```is not``` assert that :
        - a location or a character has or a certain status
    - une complex condition is composed of several simple conditions and logical terms :
        - ```&``` to assert that two conditions are true
        - ```|``` to assert that at least of two conditions is true
        - ```(``` and ```)``` to define prioritary expressions (```&``` has priority over ```|```)
    - ```Example``` : (player has fish | house is haunted) & house has not player
- its reaction (this is simply the message that will be displayed if the player writes an action for which the condition is true)
- its affected entity (name of a ```Location``` or ```Character```)
- its added statuses [list] (statuses that will be added to the affected entity)
- its removed statuses [list] (statuses that will be removed from the affected entity)
- its added items [list] (items that will be added to the affected entity)
- its removed items [liste] (items that will be removed from the affected entity)
- its new location (if the affected entity is a ```Character```, it will go to this new location)

# FRANCAIS

## Création d'un scénario

Un scénario se crée grâce à un fichier CSV. Vous trouvez un exemple dans le fichier ```exemple.csv```.

***Note* : Certaines cellules contiendront des listes. Elles suivent la syntaxe suivante : ```elem1 / elem2 / elem3```. Il est néanmoins possible d'écrire des listes de 0 ou 1 élément.**

### Propriétés générales

- ```Interaction avec objet``` : TODO
- ```Fouiller par défaut``` : TODO
- ```Langue``` : FR (Il est possible de choisir EN. Dans ce cas, nous vous conseillons vivement de suivre ce tutoriel en version anglaise et d'utiliser l'exemple de CSV en anglais.)

### Objets

Une colonne après l'autre, les objets sont représentés par 3 caractéristiques :
- leur nom
- leur description
- leurs statuts initiaux [liste]

### Personnages

Une colonne après l'autre, les personnages sont représentés par 4 caractéristiques :
- leur nom
- leur description
- leurs statuts initiaux [liste]
- leurs objets au début de la partie [liste] (Attention les noms des objets mis dans cette liste doivent avoir été écrits dans le tableau concernant les objets)

**Important** :
- le joueur est un personnage et son nom doit absolument être ```joueur```
- lorsque ce personnage obtient le statut ```mort```, le joueur a perdu et la partie est finie
- lorsqu'il obtient le statut ```victoire```, le joueur a gagné

### Lieux

Une colonne après l'autre, les lieux sont représentés par 6 caractéristiques :
- leur nom
- leurs statuts initiaux [liste]
- leurs objets au début de la partie [liste] (Attention les noms des objets mis dans cette liste doivent avoir été écrits dans le tableau concernant les objets)
- leurs personnages au début de la partie [liste] (Attention les noms des personnages mis dans cette liste doivent avoir été écrits dans le tableau concernant les personnages)
- leurs indices [liste]
- leurs actions (Celles-ci sont détaillées dans la section suivante)

### Actions

Chaque action est attribuée à un lieu. Pour ce faire, il faut remplir un bloc dans la colonne du lieu correspondant.

Un bloc (action) est caractérisé par 9 caractéristiques :
- son nom (ce que le joueur devra écrire pour lancer l'action)
- sa condition (expression qui détermine si l'action peut être exécutée)
    - une condition simple peut être dans les formes suivantes :
        - ```Lieu``` est ```Statut```
        - ```Lieu``` est pas ```Statut```
        - ```Lieu``` a ```Objet```
        - ```Lieu``` a pas ```Objet```
        - ```Lieu``` a ```Personnage```
        - ```Lieu``` a pas ```Personnage```
        - ```Personnage``` est ```Statut```
        - ```Personnage``` est pas ```Statut```
        - ```Personnage``` a ```Objet```
        - ```Personnage``` a pas ```Objet```
    - les expressions ```a``` et ```a pas``` permettent de vérifier si :
        - un lieu possède ou non un personnage ou un objet
        - un personnage possède ou non un objet
    - les expressions ```est``` et ```est pas``` permettent de vérifier si :
        - un lieu ou un personnage possède un certain statut
    - une condition complexe est composée de plusieurs conditions simples (cs) et de caractères logiques :
        - ```&``` pour vérifier que deux conditions sont vraies
        - ```|``` pour vérifier qu'au moins une parmi deux conditions est vraie
        - ```(``` et ```)``` pour définir des expressions prioritaires (en effet, ```&``` est prioritaire devant ```|```)
    - ```Exemple``` : (joueur a poisson | maison est hantée) & maison a pas joueur
- sa réaction (il s'agit tout simplement du message qui sera affiché si le joueur écrit une action dont la condition est vérifiée)
- son entité affectée (```lieu``` ou ```personnage```)
- ses statuts ajoutés [liste] (ensemble des statuts qui seront attribués à l'entité affectée)
- ses statuts retirés [liste] (ensemble des statuts qui seront retirés à l'entité affectée)
- ses objets ajoutés [liste] (ensemble des objets qui iront dans l'inventaire de l'entité affectée)
- ses objets retirés [liste] (ensemble des objets qui sortiront de l'inventaire de l'entité affectée)
- son changement de lieu (si l'entité affectée est un ```Personnage```, celui-ci ira vers le lieu indiqué)