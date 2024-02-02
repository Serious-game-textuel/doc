### Diagramme de Contexte

```plantuml 

@startuml Context-Diagram

Component Medical_world_adventure as Mwa
actor Utilisateur as util
actor Administrateur as admin


util -left-> Mwa : Démarrer une partie\nrépondre aux choix
util <-left- Mwa : texte

admin -right-> Mwa : Ajout/\nSuppression \nde scénario
admin <-right- Mwa : scénario

@enduml
```

### Vue logique

```plantuml
@startuml Logical-View
actor Utilisateur as util
actor Administrateur as admin

Component IHM
Component Medical_world_adventure as Mwa
Component BDD
Component Moodle

util -up- IHM
admin -down- IHM
Mwa -right- BDD
IHM -right- Mwa
BDD -right- Moodle

@enduml
```

### Model de donnée

```plantuml
@startuml

Enum Langue {
    FR
    EN
}

Class Partie{
    -{static} id : int
  --
    -mort : int
    -action : int
    -lieu_visité : int
    -heure_debut : date
    -langue : Langue
  --
    +bool change_lieu(id: int)
}

Class Inventaire{
    -{static} id : int
  --
    +Materiel get_materiel(id: int)
    +Materiel[] get_materiel()
}

Class Sauvegarde{
    -{static} id : int
  --
    +void creer_sauvegarde()
    +void charger_sauvegarde()
}

Class Sortie{
    -{static} id : int
  --
    -nom : string
  --
    +boolean check_condition()
}

Class Materiel{
    -{static} id : int
  --
    -description : string
    -nom : string
    -status : Map<string, bool>
}

Class Personnage{
    -{static} id : int
  --
    -description : string
    -nom : string
    -status : Map<string, boolean>
  --
    +Inventaire get_inventaire()
}

Class Lieu{
    -{static} id : int
  --
    -description : string
    -nom : string
    -status : Map<string, bool>
  --
    +Inventaire get_inventaire()
    +Personnage[] get_personnages()
    +bool check_action(action: Action)
    +Indice[] get_indices()
}

Class Action{
    -{static} id : int
  --
    -nom : string
  --
    +bool check_condition()
}

class Condition{
    -{static} id : int
  --
    -description : string[]
  --
    +void do_reaction()
}

Class Reaction{
    -{static} id : int
  --
    -description : string
    -changement_status : string
    -transition_lieux : Map<string, string>
}

Class Indice{
    -{static} id : int
  --
    -description : string
}

note "Chaque champ private a\nun getter et un setter" as N1

Sortie --o Lieu
Sortie o-- Condition
Personnage o-- Inventaire
Partie o-- Personnage
Partie o- Sauvegarde
Partie o- Langue
Lieu o-- Inventaire
Lieu o-- Indice
Action o-- Condition
Condition o-- Reaction
Action --o Lieu
Lieu o-- Personnage
Partie o-- Lieu
Inventaire o-- Materiel

@enduml
```