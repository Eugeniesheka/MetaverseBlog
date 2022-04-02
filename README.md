# MetaUnivers



Il s’agit de développer une application web permettant à une communauté de cryptophiles
d'échanger sur les cryptomonnaies du métavers (https://cryptoast.fr/metaverse-comprendre-mondesvirtuels-blockchains-nfts/). Les membres de la communauté inscrits dans l'application peuvent créer
des annonces pour promouvoir des cryptomonnaies. Ils peuvent aussi émettre un avis sur les
différentes cryptomonnaies disponibles dans l'application

## Informations 

Les instructions ci-dessous vous permettront de déployer et utiliser facilement notre application sur une machine ne disposant pas  de Symfony et 
Composer.

### Prerequis 

une version Symfony 4.4 et  une version php 7.4.*

Installation sur Windows
```
 Pour une installation facile de PHP, de MySQL sur Windows installez Xampp  sur https://www.apachefriends.org/fr/download.html.
(a) Installation de Composer :
Télécharger et installer composer à partir de https://getcomposer.org/Composer-Setup.exe

(b) Installation de l'utilitaire Symfony :
Télécharger et installer l'utilitaire Symfony à partir de https://get.symfony.com/cli/setup.exe


```
Installation sur Mac OS 
```
Pour une installation facile de PHP, de MySQL  sur Mac OS installez Mamp sur https://www.mamp.info/en/downloads/. 
(a) Installation de Composer :
Exécuter les commandes suivantes dans un terminal :

php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
php -r "if (hash_file('sha384', 'composer-setup.php') ===
'756890a4488ce9024fc62c56153228907f1545c228516cbf63f885e036d37e9a59d27d63f46af1d4
d07ee0f76181c7d3') { echo 'Installer verified'; } else { echo 'Installer corrupt';
unlink('composer-setup.php'); } echo PHP_EOL;"
php composer-setup.php --install-dir=/usr/local/bin --filename=composer
php -r "unlink('composer-setup.php');"

(b) Installation de Composer :
Exécuter les commandes suivantes dans un terminal :



curl -sS https://get.symfony.com/cli/installer | bash


```
### Deployer l'application 

vous devriez premierement vider tout les caches en utilisant la commande :  
```
php bin/console cache:clear

composer dump 

composer install
```
Vous devriez configurer dans le fichier .env les informations relatives à votre base de données

par exemple : 
```
DATABASE_URL="mysql://db_user:db_password@127.0.0.1:3306/db_name"
```
Ensuite vous devrez créer votre base de donnée en exécutant la commande 
```
php bin/console doctrine:database:create --if-not-exists
```

Ensuite vous pouvez telécharger les fixtures en faissant :

```
php bin/console doctrine:fixtures:load
```

## Lancement de l'application 

vous pouvez lancez l'application en exécutant : 

a) En exécutant dans un terminal la commande suivante de la console :
```
php bin/console list
```
ou soit 
b) En lançant le serveur interne de php avec la commande suivante :
```
php -S localhost:8000 -t public
et en essayant dans un navigateur le lien suivant : http://127.0.0.1:8000 ou le lien qui vous sera proposé
```

## Auteurs

* **Eugénie Sheka **  - (https://github.com/Eugeniesheka)
* **Halim El outanie **  - https://github.com/halim2001)


## A savoir 

* Certains bout des codes ont étaient récuperé du tp4 de dev web et ont été adapté au besoin
