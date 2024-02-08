# Installation et configuration pour les tests
Pour utiliser PHPUnit avec Moodle, vous devez suivre les étapes suivantes :

## Installer PHPUnit : 
Si vous ne l’avez pas déjà fait, installez PHPUnit à l’aide de Composer.
Ouvrez un terminal et naviguez jusqu’à la racine de votre projet Moodle, puis exécutez la commande suivante :
composer require --dev phpunit/phpunit:9.5

## Configurer PHPUnit pour Moodle : 
créer un dossier dans /var/ pour receuillir les données de test tels que moodletest ,donner les autorisation:
sudo mkdir /var/moodletest
sudo chmod -R 777 /var/moodletest

puis dans le fichier config.php de moodle ajouter les ligne suivante:
$CFG->phpunit_dataroot = '/var/moodletest';
$CFG->phpunit_prefix = 'phpu_';

Ensuite,Moodle a besoin d’un fichier de configuration PHPUnit spécifique. Heureusement, Moodle fournit un script pour générer ce fichier. Dans le terminal, à la racine de votre projet Moodle, exécutez la commande suivante :
php admin/tool/phpunit/cli/init.php


## Exécuter les tests :
Une fois que vous avez écrit vos tests, vous pouvez les exécuter à l’aide de la commande PHPUnit de Moodle. Dans le terminal, à la racine de votre projet Moodle, exécutez la commande suivante :
vendor/bin/phpunit chemin_du_fichier_de_test comme par exemple: 
vendor/bin/phpunit mod/serioustextualgame/tests/GameTest.php
