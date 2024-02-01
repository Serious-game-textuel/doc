## Serious Game

### liste de fonctionalitées:
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

### liste des contraintes:
- sous forme d'extension moodle

### Diagramme de Contexte

```plantuml 

@startuml Context-Diagram

Component Medical_world_adventure as Mwa
actor Utilisateur as util
actor Administrateur as admin


util -left-> Mwa : Ajout de scénario\nrépondre aux choix
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

util -up- IHM
admin -down- IHM
Mwa -right- BDD
IHM -right- Mwa

@enduml
```

### Model de donnée

```plantuml
@startuml

Class Partie{
  {static} id : Integer (auto increment)
  --
  mort : int
  action : int
  lieu_visité : int
  heure_debut : date(YYYY-MM-DD HH:MM:SS)
}

Class Inventaire{
  {static} id : Integer (auto increment)
  --
}


Class Sauvegarde{
  {static} id : Integer (auto increment)
  --
}

Class Sortie{
  {static} id : Integer (auto increment)
  {final}nom : string
}

Class Materiel{
  {static} id : Integer (auto increment)
  --
  {final}description : string
  {final}nom : string
  status : Map(string, boolean)
}

Class Personnage{
  {static} id : Integer (auto increment)
  --
  {final}description : string
  {final}nom : string
  status : Map(string, boolean)
}

Class Lieu{
  {static} id : Integer (auto increment)
  --
  {final} description : string
  {final}nom : string
  status : Map(string, boolean)

}

Class Action{
  {static} id : Integer (auto increment)
  --
  {final}nom : string
}

class Condition{
  {static} id : Integer (auto increment)
  --
  {final}description : string[]
}


Class Reaction{
  {static} id : Integer (auto increment)
  --
  {final}description : string
  {final}changement_status : string
  {final}transition_lieux : Map(string, string)
}



Class Indice{
  {static} id : Integer (auto increment)
  --
  {final}description : string
}


' Partie "1" o-u- "0..*" Joueur
Sortie --o Lieu
Sortie o-- Condition
Personnage o-- Inventaire
Partie o-- Inventaire
Partie o- Sauvegarde
Lieu o-- Inventaire
Lieu o-- Indice
Action o-- Condition
Condition o-- Reaction
Action --o Lieu
Lieu o-- Personnage
Partie o-- Lieu
Inventaire o-- Materiel
' ObjetInteractif *..{ Materiel
' ObjetInteractif *..{ Personnage
' ObjetInteractif *..{ Lieu



@enduml
```