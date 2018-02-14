# Le fonctionnement d'un nom de domaine (DNS, Zone DNS, A record, MX Record).
-------------------------------------------------------------------------------
### 3 bases à comprendre:

		1.Lorsque nous surfons sur un site web  https://www.infomaniak.ch, infomaniak.ch est le nom de domaine.
		2.Chaque nom de domaine posséde des DNS(Domain Name System), lesquels indiquent où se trouve la zone DNS du nom de domaine.
		3.la zone DNS permet ensuite de confier la gestion de différents services liés au nom de domaine à différents prestataires. 
		Pour un nom de domaine unique, il est par exemple possible de confier l'hébergement Web un prestataire X (via le A Record) 
		et l'hébergement Mail à un prestataire Y (via le MX Record).

### Sur le plan administratif

		chaque nom de domaine est réservé et géré par un registrar (bureau d'enregistrement)
		les DNS d'un nom de domaine se configurent auprès du registrar qui gère le nom de domaine.
		la zone DNS peut être prise en charge par le registrar ou un autre prestataire.
		l'hébergement Web et l'hébergement Mail peuvent être pris en charge par n'importe quel hébergeur.				   

![schema](https://www.infomaniak.com/proxy/aHR0cDovL3N0b3JhZ2UtbWFzdGVyLmluZm9tYW5pYWsuY2gvZmFxL2NvbnRlbnQtaW1hZ2VzLzEzLTAzLTIwMTUvNTUwMmY3Y2FkNmFlOC5wbmc=)

		un enregistrement MX (MX record) permet de faire pointer un nom de domaine 
		(ex.: votre-site.com) vers un serveur de mail


		un enregistrement A (A record) permet de faire pointer un nom de domaine 
		(ex.: votre-site.com) ou un sous-domaine (ex.: exemple.votre-site.com) 
		vers un serveur Web qui a une adresse IP statique	                      

* Registrar : Bureau d'enregistrement, est une sociéte ou une association gérant la réservation de noms de domaine internet.

* DNS: Permet de pointer notre nom de domaine vers l'hebergeur, le serveur ou l'espace d'hebergement.

## ETAPES:

		1.Achat d'un nom de domaine sur gandi (https://www.gandi.net/fr).
		2.Sur gandi dans l'onglet DNS Records, nous avons crée 4 sous domaines avec nos prénoms via un enregistrement A.


# Installation Virtualhost:

**Étape 1** - Création de la structure de répertoire:
* La première étape que nous allons prendre est de créer une structure de répertoire qui contiendra les données du site que nous servirons aux visiteurs.
* Notre document racine , le répertoire de haut niveau qu'Apache considère pour trouver du contenu à diffuser, sera défini sur des répertoires individuels dans le /var/wwwrépertoire. Nous allons créer un répertoire pour chacun des hôtes virtuels que nous allons configurer.

		 mkdir -p /var/www/astrid.com                                                                                      

**Etape 2** - On est allé copier notre dossier machine a café perso dans ce dossier avec la commande suivante.

		cp -r /var/www/html/Machine_BANDANAS/machine_cafe_Abossy/ /var/www/astrid.com/

**Etape 3** - Créer de nouveaux fichiers hôtes virtuels
 Les fichiers hôtes virtuels spécifient la configuration réelle de nos hôtes virtuels et dictent comment le serveur Web Apache répondra aux diverses demandes de domaine.
		
 1.On se place dans le dossier /etc

			root@ilot6:/# cd /etc/apache2/sites-available

 2.J'ouvre mon nouveau fichier astrid.conf

			root@ilot6:/etc/apache2/sites-available# nano astrid.conf

 3.Ensuite on modifie les paramètres avec nos données, Cet hôte virtuel correspond à toutes les demandes effectuées sur le port 80, le port HTTP par défaut. 

		<VirtualHost *:80>

		        ServerName astrid/mcbandanas.online
		        DocumentRoot /var/www/astrid.com/machine_cafe_Abossy/fonctions_recette/machine_html.php

		        ErrorLog ${APACHE_LOG_DIR}/error.log
		        CustomLog ${APACHE_LOG_DIR}/access.log combined

		</VirtualHost>

* **Étape 4** - Activation des nouveaux fichiers d'hôte virtuel

* 1.Activer le premier site:

		root@ilot6:/etc/apache2/sites-available# a2ensite astrid.conf

* 2.Lancer le service 

		root@ilot6:/etc/apache2/sites-available# service apache2 restart

* **Étape 5** - Test

		http://astrid.mcbandanas.online/



# Installer mon projet Laravel sur le serveur

1.Dans Mon wamp64 ouvrir Gitbash

astrid.bossy@PC-DG-CAMPUS-21 MINGW64 /c/wamp64/www/Machine_BANDANAS/machine_cafe_Abossy (master)

	$ git pull //pour récuperer l'ancienne version.

	$git add

	$git commit -m"projet laravel Astrid"

	$git push 

2.Sur mon bash côte serveur
	
	root@ilot6:/var/www/html/Machine_BANDANAS# git pull



# Installer Composer

**1.se connecter via SSH à votre hébergement**
		
		ssh root@51.15.134.133
	
**2.dans le terminal, saisir la commande suivante:**

		cd mcafe_laravel

**3.dans le terminal, saisir la commande suivante:**

		mkdir .composer

**4.dans le terminal, saisir la commande suivante:**

	curl -sS https://getcomposer.org/installer | php -d allow_url_fopen=On

	php composer.phar

	php composer.phar update

**5.Composer est maintenant disponible sur votre hébergement**


# Installer les droits sur le projet Laravel
  
  1.On se place dans le dossier de notre projet Laravel:

		machine_cafe_Abossy  mcafe_laravel
		root@ilot6:/var/www/astrid.com# cd mcafe_laravel/
		root@ilot6:/var/www/astrid.com/mcafe_laravel# ls
		app      bootstrap      composer.lock  config    package.json    phpunit.xml  readme.md  routes      storage  vendor
		artisan  composer.json  composer.phar  database  PHP_Formulaire  public       resources  server.php  tests    webpack.mix.js

  2.On va donner les droits a notre dossier storage:

		root@ilot6:/var/www/html/Machine_BANDANAS/machine_cafe_Abossy/astrid.com/mcafe_laravel# 
		chmod -R a+w /var/www/html/Machine_BANDANAS/machine_cafe_Abossy/astrid.com/mcafe_laravel/storage/
  
**a+w = droit d'ecriture pour tous.**

  3.on ouvre le dossier storage:

		root@ilot6:/var/www/astrid.com/mcafe_laravel# ls -al

**ls -al=permet d'afficher tous les fichiers même cachés.**
  
  
  4.On va copier et renommer le fichier .env.example

		root@ilot6:/var/www/astrid.com/mcafe_laravel# cp .env.example .env

  5.Application Key (On va génerer une nouvelle Key)
  	Après avoir installé Laravel on va définir notre clé d'application sur une chaîne aléatoire.
  	On utilise la commande suivante. 
**Sert à proteger les formulaires**

		root@ilot6:/var/www/astrid.com/mcafe_laravel# php artisan key:generate



# Mod_Rewrite & Allow Override

1.Le module mod_rewrite est déjà "pré-installé" avec Apache sous Ubuntu. Vous pouvez vérifiez si c'est le cas en exécutant la commande:

	ls -l /usr/lib/apache2/modules/

et si vous voyez le fichier "mod_rewrite.so", c'est que ce module est "pré-installé".

2.Ensuite, la commande suivante crée un lien logique entre ce module et les fichiers de modules que comprend votre serveur Apache (ils sont placés dans le dossier /etc/apache2/mods-available/)
		
	sudo a2enmod rewrite

3.Maintenant, ouvrez le fichier apache2.conf :

	sudo gedit /etc/apache2/apache2.conf

et rajoutez, à la fin de ce dernier, le code suivant afin de bien s'assurer que le module sera activé :

	<ifModule mod_rewrite.c>
	RewriteEngine On
	</ifModule>


Finalement, redémarrez votre serveur Apache et le tour est joué !

	sudo /etc/init.d/apache2 restart

### Afficher notre Projet sur le browser (Allow Override)

1.Importer puis exporter ma BDD laravel sur phpmyadmin dans le dossier machine_laravel_astrid sur le phpmyadmin de notre serveur.

2.modifier le fichier .env en ajoutant 

		DB_CONNECTION=mysql
		DB_HOST=127.0.0.1
		DB_PORT=3306
		DB_DATABASE=machine_laravel_astrid
		DB_USERNAME=ilot6
		DB_PASSWORD=bandanas

		root@ilot6:/var/www/astrid.com/mcafe_laravel# service apache2 restart

3.Ouvrir le fichier astrid.conf

	root@ilot6:/etc/apache2/sites-available# nano astrid.conf

4.Modifier ce fichier 

	 ServerName astrid.mcbandanas.online
        DocumentRoot /var/www/html/Machine_BANDANAS/machine_cafe_Abossy/astrid.com/mcafe_laravel/public
   **/public** on fait pointer sur public, c'est à cet endroit qu'il y a le fichier index qui lance Laravel. 
        <Directory /var/www/html/Machine_BANDANAS/machine_cafe_Abossy/astrid.com>
        Options Indexes FollowSymLinks
        AllowOverride All
        Require all granted
        </Directory>


5.Composer install (à chaque fois que l'on ajoute un nouveau projet laravel)

6.TEST

	http://astrid.mcbandanas.online/1


# Installer la connection securisée Https

	1.apt-get install python-certbot-apache -t stretch-backports
	2.certbot --authenticator webroot --installer apache
	3.Nom de la webroot:  /var/www/astrid.com/mcafe_laravel/public/

# Installer une clé SSH

key qui permet de se connecter au serveur sans mot de passe.

1.Ouvrir un Bash sur notre local p

	$ ssh-keygen

Une clé a été générée dans notre dossier .ssh présent sur le disque /p

	$ .. /p//.ssh/id_rsa.pub. //repertoire du dossier ssh

	$ nano id_rsa.pub	


2.Copier la clé publique
Nous allons placer la clé sur le virtual server.

	$ ssh-copy-id root@51.15.134.133

3.La clé est generée.


# Probleme de Migration

en cas de problemes avec les migrations si le message suivant s'affiche
		
		Doctrine\DBAL\Driver\PDOMySql\Driver' not found

il faut ouvrir le fichier composer.json et copier la ligne suivante.

	"doctrine/dbal":"~2.3" 	