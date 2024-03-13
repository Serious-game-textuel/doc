# Plan de Test
## 1. Objectifs du plan de test :
    Avec les tests,nous voulons vérifier la fonctionnalité du plugin. Nous voulons nous assurer que le plugin fonctionne correctement et qu'il répond aux exigences spécifiées dans le cahier des charges. Nous voulons également identifier et corriger les éventuels problèmes ou défauts avant le lancement du produit.
    Nous allons faire des tests pour chaque éventualités du scénario template pour qu'une utilisation normale du plugin soit possible.
    Ainsi pour chaque Classes conçernant le plugin, nous allons faire des tests unitaires pour vérifier que chaque méthode fonctionne correctement.
    Nous allons également faire des tests d'intégration pour vérifier que les différentes classes du plugin fonctionnent correctement ensemble.
    Nous allons également faire des tests de validation pour vérifier que le plugin répond bien aux exigences spécifiées dans le cahier des charges.


## 2. Stratégie de test :
   - **Approche de test :** Nous allons utiliser une combinaison de tests manuels et automatisés pour couvrir toutes les fonctionnalités du plugin avec PHPUnit.
   - **Critères d'acceptation :** Un test est réussi si le plugin répond aux exigences spécifiées dans le cahier des charges et qu'il n'y a donc pas d'erreur imprévue.

## 3. Plan de test :
#### Scénario de test:
##### Test de la classe Action:
1. **Test des conditions réussies :**
   - **Description :** Vérifiez si les conditions sont correctement évaluées et que les réactions appropriées sont déclenchées.
   - **Étape(s) :** Exécutez le testdoconditions() avec des conditions valides et vérifiez que les réactions sont correctement effectuées.

2. **Test des conditions non satisfaites :**
   - **Description :** Vérifiez que les réactions ne sont pas déclenchées lorsque les conditions ne sont pas satisfaites.
   - **Étape(s) :** Exécutez le testdoconditions() avec des conditions invalides et assurez-vous qu'aucune réaction indésirable n'est effectuée.

3. **Test des conditions complexes :**
   - **Description :** Vérifiez si les conditions complexes impliquant des opérateurs logiques fonctionnent correctement.
   - **Étape(s) :** Créez des conditions avec des combinaisons d'opérateurs logiques (ET, OU) et assurez-vous que les réactions sont correctement déclenchées ou non selon les cas.

4. **Test de réactions multiples :**
   - **Description :** Vérifiez si les réactions multiples sont correctement exécutées en réponse à une seule condition.
   - **Étape(s) :** Créez une condition qui déclenche plusieurs réactions et vérifiez que toutes les réactions appropriées sont effectuées.

5. **Test de l'état final des entités :**
   - **Description :** Vérifiez que les entités (personnages, lieux, objets) ont l'état attendu après l'exécution des réactions.
   - **Étape(s) :** Exécutez le testdoconditions() et vérifiez que les entités ont les objets attendus et les états corrects après l'exécution des réactions.

6. **Test de réactions multiples avec des conditions alternatives :**
   - **Description :** Vérifiez si les réactions sont correctement déclenchées lorsque des conditions alternatives sont fournies.
   - **Étape(s) :** Créez des conditions alternatives et vérifiez que les réactions appropriées sont déclenchées en fonction de la satisfaction des conditions.

7. **Test avec des conditions vides :**
   - **Description :** Vérifiez le comportement lorsque la liste des conditions est vide.
   - **Étape(s) :** Exécutez le test avec une action contenant une liste vide de conditions et assurez-vous qu'aucune réaction n'est déclenchée.

8. **Test avec des réactions multiples conflictuelles :**
   - **Description :** Vérifiez le comportement lorsque des réactions multiples entrent en conflit.
   - **Étape(s) :** Créez des réactions conflictuelles et vérifiez que seul le comportement attendu est effectué en fonction des priorités définies.

9. **Test de réactions avec des conditions complexes et des opérateurs logiques :**
   - **Description :** Vérifiez si les réactions sont correctement déclenchées avec des conditions complexes impliquant des opérateurs logiques.
   - **Étape(s) :** Créez des conditions complexes avec des opérateurs logiques et assurez-vous que les réactions sont déclenchées selon les attentes.

##### Test de la classe App:
1. **Test de l'initialisation des propriétés de l'application :**
   - **Description :** Vérifiez si le constructeur initialise correctement les propriétés de l'application.
   - **Étape(s) :** Créez une instance de la classe App et vérifiez si les propriétés telles que le jeu, les entités de départ, les objets, les personnages et les lieux sont correctement initialisées.

2. **Test des objets de départ :**
   - **Description :** Vérifiez si les objets de départ sont correctement chargés et associés aux entités appropriées.
   - **Étape(s) :** Exécutez le testgetsetgame() et assurez-vous que les objets associés aux personnages et aux lieux de départ sont corrects.

3. **Test des caractéristiques des objets :**
   - **Description :** Vérifiez si les caractéristiques des objets sont correctement initialisées.
   - **Étape(s) :** Vérifiez que les noms, descriptions et états des objets sont corrects pour chaque objet testé.

4. **Test des caractéristiques des personnages :**
   - **Description :** Vérifiez si les caractéristiques des personnages sont correctement initialisées.
   - **Étape(s) :** Vérifiez que les noms, descriptions, états, inventaires et lieux des personnages sont corrects pour chaque personnage testé.

5. **Test des caractéristiques des lieux :**
   - **Description :** Vérifiez si les caractéristiques des lieux sont correctement initialisées.
   - **Étape(s) :** Vérifiez que les noms, états, inventaires et indices des lieux sont corrects pour chaque lieu testé.

6. **Test des états initiaux des entités :**
   - **Description :** Vérifiez si les entités ont les états initiaux attendus après l'initialisation.
   - **Étape(s) :** Vérifiez les états initiaux des objets, personnages et lieux pour chaque entité testée.

7. **Test des associations d'objets avec des entités :**
   - **Description :** Vérifiez si les objets sont correctement associés aux personnages et lieux appropriés.
   - **Étape(s) :** Vérifiez que les objets de départ sont correctement associés aux personnages et lieux correspondants.

8. **Test des associations de personnages avec des lieux :**
   - **Description :** Vérifiez si les personnages sont correctement associés aux lieux de départ.
   - **Étape(s) :** Vérifiez que les personnages ont les lieux de départ appropriés après l'initialisation.

9. **Test de la création d'instances sans fichier CSV valide :**
   - **Description :** Vérifiez le comportement lorsque le fichier CSV passé au constructeur n'est pas valide.
   - **Étape(s) :** Essayez de créer une instance de l'application avec un fichier CSV incorrect et assurez-vous qu'une exception appropriée est levée.

10. **Test de l'accès au jeu :**
   - **Description :** Vérifiez si l'accès au jeu à partir de l'application est possible.
   - **Étape(s) :** Exécutez le testgetsetgame() et assurez-vous que l'objet de jeu retourné est correct.

##### Test de la classe Condition:

1. **Test pour une condition de noeud avec conditions filles vraies** :
   - Créez deux conditions de feuille, chacune avec une entité qui satisfait la condition.
   - Créez une condition de nœud avec ces deux conditions et le connecteur "et".

2. **Test pour une condition de noeud avec une condition fille fausse** :
   - Créez deux conditions de feuille, l'une avec une entité qui satisfait la condition et l'autre avec une entité qui ne satisfait pas la condition.
   - Créez une condition de nœud avec ces deux conditions et le connecteur "et".

3. **Test pour une condition de noeud avec un connecteur "ou" et des conditions filles fausses** :
   - Créez deux conditions de feuille, chacune avec une entité qui ne satisfait pas la condition.
   - Créez une condition de nœud avec ces deux conditions et le connecteur "ou".

4. **Test pour une condition de feuille avec un item non présent** :
   - Créez une condition de feuille avec une entité de personnage et un item.

5. **Test pour une réaction qui déplace un personnage vers une nouvelle localisation** :
   - Créez un personnage et une nouvelle localisation.
   - Ajoutez une réaction qui déplace le personnage vers cette nouvelle localisation.

6. **Test pour une réaction qui ajoute un statut au personnage** :
   - Créez un personnage.
   - Ajoutez une réaction qui ajoute un nouveau statut au personnage.

7. **Test pour une réaction qui retire un statut du personnage** :
   - Créez un personnage avec un statut existant.
   - Ajoutez une réaction qui retire ce statut du personnage.

8. **Test pour une réaction qui ajoute un item à une localisation** :
   - Créez une localisation.
   - Ajoutez une réaction qui ajoute un nouvel item à cette localisation.

9. **Test pour une réaction qui retire un item d'une localisation** :
   - Créez une localisation avec un item existant.
   - Ajoutez une réaction qui retire cet item de la localisation.
##### Test de la classe Entity:
1. **Test de création d'un personnage non-joueur (NPC) :**
   - Vérifier si le NPC est une instance de la classe `Npc_Character`.
   - Vérifier si la description du NPC est correcte.
   - Vérifier si le nom du NPC est correct.
   - Vérifier si les status du NPC sont correctement initialisés.

2. **Test de création d'un personnage joueur (Player Character) :**
   - Vérifier si le personnage joueur est une instance de la classe `Player_Character`.
   - Vérifier si la description du personnage joueur est correcte.
   - Vérifier si les status du personnage joueur sont correctement initialisés.

3. **Test de création d'un objet (Item) :**
   - Vérifier si l'objet est une instance de la classe `Item`.
   - Vérifier si la description de l'objet est correcte.
   - Vérifier si le nom de l'objet est correct.
   - Vérifier si les status de l'objet sont correctement initialisés.

4. **Test de création d'un emplacement (Location) :**
   - Vérifier si l'emplacement est une instance de la classe `Location`.
   - Vérifier si le nom de l'emplacement est correct.
   - Vérifier si les status de l'emplacement sont correctement initialisés.

5. **Test de modification des status :**
   - Ajouter un nouveau status à un NPC et vérifier s'il est correctement ajouté.
   - Supprimer un status existant d'un NPC et vérifier s'il est correctement supprimé.
   - Supprimer un status non existant d'un NPC et vérifier que les status restent inchangés.
   - Ajouter un nouveau status à un personnage joueur et vérifier s'il est correctement ajouté.
   - Supprimer un status existant d'un personnage joueur et vérifier s'il est correctement supprimé.
   - Supprimer un status non existant d'un personnage joueur et vérifier que les status restent inchangés.
   - Ajouter un nouveau status à un objet et vérifier s'il est correctement ajouté.
   - Supprimer un status existant d'un objet et vérifier s'il est correctement supprimé.
   - Supprimer un status non existant d'un objet et vérifier que les status restent inchangés.
   - Ajouter un nouveau status à un emplacement et vérifier s'il est correctement ajouté.
   - Supprimer un status existant d'un emplacement et vérifier s'il est correctement supprimé.
   - Supprimer un status non existant d'un emplacement et vérifier que les status restent inchangés.

##### Test de la classe Game:
1. **Test de récupération du nombre de morts :**
   - Créer un jeu avec un nombre de morts initial de zéro.
   - Vérifier si la méthode `get_deaths` retourne zéro.

2. **Test d'incrémentation du nombre de morts :**
   - Créer un jeu avec un nombre de morts initial de zéro.
   - Ajouter une mort en appelant la méthode `add_death`.
   - Vérifier si la méthode `get_deaths` retourne un après l'ajout de la mort.

3. **Test de récupération de la liste des actions :**
   - Créer un jeu sans aucune action.
   - Vérifier si la méthode `get_actions` retourne une liste vide.

4. **Test d'ajout d'une action à la liste des actions :**
   - Créer un jeu sans aucune action.
   - Ajouter une action à la liste en appelant la méthode `add_action`.
   - Vérifier si la méthode `get_actions` retourne une liste contenant une action après l'ajout.

5. **Test de récupération de la liste des locations visitées :**
   - Créer un jeu sans aucune location visitée.
   - Vérifier si la méthode `get_visitedlocations` retourne une liste vide.

6. **Test d'ajout d'une location à la liste des locations visitées :**
   - Créer un jeu sans aucune location visitée.
   - Ajouter une location à la liste en appelant la méthode `add_visitedlocation`.
   - Vérifier si la méthode `get_visitedlocations` retourne une liste contenant cette location après l'ajout.

7. **Test de récupération de l'heure de début du jeu :**
   - Créer un jeu avec une heure de début spécifique.
   - Vérifier si la méthode `get_start_time` retourne l'heure de début correcte.

8. **Test de définition de l'heure de début du jeu :**
   - Créer un jeu avec une heure de début initiale.
   - Définir une nouvelle heure de début en appelant la méthode `set_start_time`.
   - Vérifier si la méthode `get_start_time` retourne la nouvelle heure de début définie.

##### Test de la classe Inventory:
1. **Test de création de l'inventaire :**
   - Créer une application.
   - Créer plusieurs objets de type Item.
   - Créer un inventaire avec ces objets.
   - Vérifier si l'inventaire est une instance de la classe Inventory.

2. **Test de vérification de la présence d'un item dans l'inventaire :**
   - Créer une application.
   - Créer plusieurs objets de type Item.
   - Créer un inventaire avec certains de ces objets.
   - Vérifier si la méthode `check_item` retourne vrai pour un objet présent dans l'inventaire et faux pour un objet non présent.

3. **Test de récupération d'un item par son identifiant :**
   - Créer une application.
   - Créer plusieurs objets de type Item.
   - Créer un inventaire avec certains de ces objets.
   - Vérifier si la méthode `get_item` retourne l'objet correspondant à un identifiant donné et null pour un identifiant invalide.

4. **Test d'ajout et de suppression d'items de l'inventaire :**
   - Créer une application.
   - Créer plusieurs objets de type Item.
   - Créer un inventaire vide.
   - Ajouter des items à l'inventaire et vérifier si la liste des items dans l'inventaire est correcte après chaque ajout.
   - Tenter de retirer des items qui ne sont pas dans l'inventaire et vérifier si la liste reste inchangée.

##### Test de la classe LocationEN et FR:
1. **Test de réalisation des conditions :**
   - Créer une application.
   - Accéder à la localisation actuelle dans le jeu.
   - Vérifier si les différentes actions disponibles dans cette localisation fonctionnent correctement en termes de réponses fournies.
   - Vérifier si les actions spécifiques telles que "Take Fishing rod", "Examine Fishing rod", "Use Fishing rod", etc., donnent les résultats attendus.
   - Vérifier si les changements d'état des emplacements se produisent correctement après l'exécution des actions.
   - Vérifier si les indices (hints) sont correctement chargés pour la localisation.
   - Tester les transitions vers d'autres localisations en vérifiant si les changements de localisation se produisent correctement après l'exécution des actions.

2. **Test de demande de description :**
   - Créer une application.
   - Accéder à la localisation actuelle dans le jeu.
   - Vérifier si la description de la localisation est correcte et cohérente.
   - Vérifier si la description peut être demandée plusieurs fois et si elle reste inchangée.

3. **Test des déplacements :**
   - Créer une application.
   - Accéder à la localisation actuelle dans le jeu.
   - Tester les déplacements vers des localisations non accessibles, des localisations inexistantes et des localisations fermées.
   - Vérifier que les déplacements vers des localisations valides se produisent correctement.

4. **Test des objets :**
   - Créer une application.
   - Accéder à la localisation actuelle dans le jeu.
   - Tester la récupération d'objets présents dans la localisation en vérifiant qu'un objet ne peut être récupéré qu'une seule fois.
   - Vérifier que les objets récupérés sont correctement ajoutés à l'inventaire du joueur.

##### Test de la classe Reaction:
1. **Test de la classe Character_Reaction :**
   - Créer une application avec une configuration de jeu.
   - Créer des objets anciens et nouveaux pour la réaction.
   - Créer un personnage fictif et une nouvelle localisation.
   - Créer une réaction de type Character_Reaction.
   - Vérifier si la réaction est correctement instanciée.
   - Vérifier si les méthodes get_character(), get_new_location() et get_new_item() renvoient les valeurs attendues.

2. **Test de la classe Location_Reaction :**
   - Créer une application avec une configuration de jeu.
   - Créer des objets anciens et nouveaux pour la réaction.
   - Créer une localisation fictive.
   - Créer une réaction de type Location_Reaction.
   - Vérifier si la réaction est correctement instanciée.
   - Vérifier si les méthodes get_location() et get_new_item() renvoient les valeurs attendues.

##### Test de la classe Util:
1. **Test de la méthode `has_array_duplicate` avec des chaînes de caractères :**
   - Créer plusieurs chaînes de caractères avec et sans doublons.
   - Vérifier que la méthode retourne true pour les tableaux contenant des doublons et false sinon.

2. **Test de la méthode `has_array_duplicate` avec des objets :**
   - Créer plusieurs objets Item avec et sans doublons.
   - Vérifier que la méthode retourne true pour les tableaux contenant des doublons et false sinon.

3. **Test de la méthode `check_array` avec des chaînes de caractères :**
   - Créer plusieurs tableaux de chaînes de caractères avec différents types de valeurs.
   - Vérifier que la méthode ne lance pas d'exception pour les tableaux contenant uniquement des chaînes de caractères et lance une exception sinon.

4. **Test de la méthode `check_array` avec des objets :**
   - Créer plusieurs tableaux d'objets Item avec différents types de valeurs.
   - Vérifier que la méthode ne lance pas d'exception pour les tableaux contenant uniquement des objets Item et lance une exception sinon.

5. **Test de la méthode `clean_array` avec des chaînes de caractères :**
   - Créer plusieurs tableaux de chaînes de caractères avec différents types de valeurs.
   - Vérifier que la méthode retourne un tableau sans doublons et sans les valeurs non conformes.

6. **Test de la méthode `clean_array` avec des objets :**
   - Créer plusieurs tableaux d'objets Item avec différents types de valeurs.
   - Vérifier que la méthode retourne un tableau sans doublons et sans les valeurs non conformes.

## 4. Environnement de test :
   Il faut un environnement de test qui ressemble le plus possible à l'environnement de production donc avoir un moodle installée localement avec le plugin installé et PHPunit installé.

## 5. Exécution des tests :
   Pour lancer un test, il suffit de lancer la commande suivante dans le terminal :
    /var/www/html/moodle/vendor/bin/phpunit /var/www/html/moodle/mod/monplugin/nom_du_fichier_de_test.php

## 6. Évaluation des résultats :
   Ces tests marchaient jusqu'à la portation dans la base de données mais ne sont plus fonctionnels car ils ne sont pas adaptés à la nouvelle version du plugin.
   Ainsi il faudra les adapter pour qu'ils soient fonctionnels.

