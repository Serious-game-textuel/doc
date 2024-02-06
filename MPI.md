# Création d’un moteur de génération de jeu sérieux textuel

## Cahier des charges

### Contexte et enjeux
- <b>environnement</b> : moodle, IFPS
- <b>client</b> : Lionel DI MARCO (Département de Maïeutique des UFR de Médecine et CHU Grenoble Alpes)
- <b>parties prenantes</b> : client (Lionel DI MARCO), professeurs encadrants (Didier DONZEZ, Emmanuelle TREHOUST)
- <b>problème à résoudre</b> : rendre l'apprentissage des pratiques protocolaires plus facile et ludique pour les étudiants en maïeutique
- <b>enjeux pour le client</b> : veut permettre aux utilisateurs (étudiants) d'appendre plus facilement des pratiques médicales tout en jouant à un jeu
### Objectifs :
- <b>livrables attendus</b> : 
    - plug-in moodle fonctionnel avec dépôt d'un fichier csv conforme par le professeur et possibilité pour les étudiants d'y jouer. Le jeu se déroulera seulement textuellement : les étudiants devront répondre en écrivant dans la console prévue pour avancer dans leur histoire. L'histoire est composée du joueur avec son inventaire, des lieux liés entre eux et potentiellement avec des personnages et des objets. Les personnages ont des états et potentiellement des objets. Chaque lieu peut être fermé et requiert un objet pour le dévérouiller.
    - possibilité de sauvegarder, récupérer des indices, calcul de score, création/dépôt de map, traductions
- <b>Product Breakdown Structure</b> : ![Trello](./images/trello.png)
- <b>Hiérarchie des objectifs</b> : Commencer par le 1er livrable attendu puis le 2ème. Dans le 2ème, le calcul du score, la map sont optionnels.
### Processus de validation :
- les critères sont la validation des éléments des livrables

## Organisation du projet :

### Démarche et planning

- <b>Work Breakdown Structure</b> :
```plantuml
@startwbs
* Création d’un moteur de génération de jeu sérieux textuel
** Phase de pré-étude
*** Définition des fonctionnalités/contraintes
*** Définition du déroulement d'une partie
*** Création des diagrammes
**** Création du diagramme de classes
**** Création du diagramme de contexte
**** Création de la vue logique
*** Formation Moodle
*** Formation PHP
*** Installation de l'espace de travail
*** Définition des taches

** Sprint 1
*** Définition syntaxe du fichier d'entrée
*** Création des squelettes de classes
*** Mise en place de l'intégration continue (Github actions)
*** Création du parseur de fichier d'entrée
*** Gestion des entrées utilisateur
*** Jouer la partie
**** Gestion des déplacements
**** Gérer interface joueur
**** Affichage de l'inventaire
**** Définition des chemins possibles

** Sprint 2
*** Création des vues moodle
**** Création vue professeur
**** Création vue utilisateur (étudiant)
*** Gestion de sauvegardes
**** Permettre de créer une sauvegarde
**** Permettre de charger une sauvegarde
*** Récupération d'indices
***< Calcul de score (optionnel)
***< Gestion de la map visuelle (optionnel)
****< Permettre le dépôt d'une map par le professeur
****< Création automatique de la map
*** Amélioration des entrées clavier
*** Permettre la traduction
*** Créer un parseur de validation de fichier csv
@endwbs
```
- <b>Gantt</b> :
```plantuml

[Edit online] 	

@startgantt
Project starts the 29th of january 2024
saturday are closed
sunday are closed
hide footbox 

2024-01-29 to 2024-02-02 are named [Pré-étude]
2024-01-29 to 2024-02-02 are colored in lightgreen
2024-02-02 to 2024-02-23 are named [Sprint 1]
2024-02-02 to 2024-02-23 are colored in lime
2024-02-23 to 2024-03-14 are named [Sprint 2]
2024-02-23 to 2024-03-14 are colored in green

/' sprint 1 '/
[Rdv présentation client] happens the 30th of january 2024
[Rdv complément client] happens the 31st of january 2024
[Installation de l'espace de travail] requires 1 days
[Formation Moodle] requires 3 days
[Formation PHP] requires 3 days
[Installation de l'espace de travail] ->[Formation Moodle]
[Installation de l'espace de travail] ->[Formation PHP]
[Définition du déroulement d'une partie] requires 1 days
[Définition des fonctionnalités/contraintes] requires 1 days
[Définition des taches] requires 2 days
[Définition du déroulement d'une partie] -> [Définition des taches]
[Définition des fonctionnalités/contraintes] -> [Définition des taches]
[Création du diagramme de classes] requires 1 days
[Création du diagramme de contexte] requires 1 days
[Création de la vue logique] requires 1 days
[Définition des taches] -> [Création du diagramme de classes]
[Définition des taches] -> [Création du diagramme de contexte]
[Définition des taches] -> [Création de la vue logique]

/' sprint 1->2 '/
[Formation Moodle] -> [Mise en place de l'intégration continue (Github actions)]
[Formation PHP] -> [Mise en place de l'intégration continue (Github actions)]
[Création du diagramme de classes] -> [Mise en place de l'intégration continue (Github actions)]
[Création du diagramme de contexte] -> [Mise en place de l'intégration continue (Github actions)]
[Création de la vue logique] -> [Mise en place de l'intégration continue (Github actions)]
[Formation Moodle] -> [Définition syntaxe du fichier d'entrée]
[Formation PHP] -> [Définition syntaxe du fichier d'entrée]
[Création du diagramme de classes] -> [Définition syntaxe du fichier d'entrée]
[Création du diagramme de contexte] -> [Définition syntaxe du fichier d'entrée]
[Création de la vue logique] -> [Définition syntaxe du fichier d'entrée]

/' sprint 2 '/
[Rdv MPI] happens the 13rd of february 2024
[Mise en place de l'intégration continue (Github actions)] requires 2 days
[Création des squelettes de classes] requires 4 days
[Mise en place de l'intégration continue (Github actions)] -> [Création des squelettes de classes]
[Définition syntaxe du fichier d'entrée] requires 4 days
[Création du parseur de fichier d'entrée] requires 8 days
[Définition syntaxe du fichier d'entrée] -> [Création du parseur de fichier d'entrée]
[définition des chemins possibles] requires 2 days
[Création du parseur de fichier d'entrée] -> [définition des chemins possibles]
[Gérer interface joueur] requires 2 days
[Création du parseur de fichier d'entrée] -> [Gérer interface joueur]
[Gestion des entrées utilisateur] requires 4 days
[Création des squelettes de classes] -> [Gestion des entrées utilisateur]
[Gestion des déplacements] requires 3 days
[Gestion des entrées utilisateur] -> [Gestion des déplacements]
[Affichage de l'inventaire] requires 3 days
[Gestion des entrées utilisateur] -> [Affichage de l'inventaire]


[Rdv mi-projet] happens the 23rd of february 2024
[Soutenance projet] happens the 15th of march 2024


@endgantt

```

### Resources
### Organisation et communication
### Risques
### Indicateurs pilotage