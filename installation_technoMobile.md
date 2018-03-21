## Démarrer un Projet Mobile

### Installation

1.**Android Studio** https://developer.android.com/studio/index.html​

(va s'installer dans le disque C:programmes/Android/AndroidStudio)

2.**Installer Node.js** https://nodejs.org/en/ (version 8.9.4 LTS)

(va s'installer dans le disque C:programmes/nodejs)

3.**Installer Cordova** http://cordova.apache.org/#getstarted

(La ligne de commande Cordova s'exécute sur Node.js et est disponible sur NPM)

	$ npm install -g cordova

## Create a project

Créez un projet Cordova vide à l'aide de l'outil de ligne de commande. 

Accédez au répertoire dans lequel vous souhaitez créer votre projet et tapez

	$ cordova create MyProject										

## Add a Plateform

Apres avoir créer un projet Cordova, on se place dans notre projet.

	$ cordova platform add browser								

la plateforme va nous permettre de construire notre application.


## Run the app

	$ cordova run browser 										

## Installation de l'environnement (sdk...)
Lien: http://cordova.apache.org/docs/en/latest/guide/platforms/android/index.html#ins 

### Android Platform Guide

**1.Installing the Requirements**

	Java Development Kit (JDK)
	On telecharge Java SE Development Kit 8u161 pour windows x64

**Android SDK**

	Android Studio
	File -> settings -> Android SDK
	cocher Android API 27
		   Android 8.0(Oreo)

**2.Modifier les variables d'environnement systeme.**

	Variables d'environnement...
	Path (Modifier)->(nouvelle)
	C:\Program Files\Java\jdk1.8.0_161\bin  -> Java
	C:\Users\astrid.bossy\AppData\Local\Android\Sdk -> AndroidS

**3.Création d'une nouvelle plateforme Android dans mon dossier MyProject**

	cordova platform add <platform name>. -> android

**4.Run your app**
From the command line. 

	cordova run <platform name>. ->	android							


**5.ouvrir le projet sur Android Studio**

**On choisit dans le file la plateforme android**

	 icone AVD Manager(image tel android)
	 lancer play dans Action de la fenetre pop up.

**6.En cas de probleme avec le Bios**

	 Redémarrer l'ordinateur
	 commande F10
	 Advanced -> systeme Option
	 cocher VTX + VTD (pour accépter les machines virtuelles)

**7.Ouvrir le projet dans l'emulateur d'Android studio**
-> lancer le bash dans le dossier.

	$ cordova run android

le projet s'affiche!

-----------------------------------------------------------------------------------------------------------



## MEMO CORDOVA & VUEJS


## Commandes

|Commandes Cordova| description|
|----------------------|---------|
|cordova create < path > | Pour créer un nouveau Projet < path > = name | 
|cordova platform add < platform name >| ajout/création d'une plateforme ex: Browser et/ou Android | 
|cordova run < platform name > | construit et permet de lancer le projet sur la plateforme choisie | 
|cordova plugin add < plugin name > | permet d'appliquer un plugin à un projet| 

**plugin**:désigne une extension prévue des fonctionnalités que l'application restitue pour communiquer avec la plate-forme native sur lequel il s'exécute. Plugins permettent d'accéder aux fonctionnalités de périphérique et de la plate-forme habituellement non disponible pour les applications web.

|Commandes| description|
|----------------------|---------|
|$ npm run dev | execute un package spécifique contenu dans un script dev du package.json|
|$ npm run build | C'est la commande de plomberie appelée par npm install (installera tous les modules listés comme dépendances de package.json.)  |


## Structure

|Structure d'un projet Cordova| description|
|----------------------|---------|
|Contenu du répertoire "platforms" | Contient les projets générés pour les différentes plateformes au projet|
|Contenu du répertoire "plugins"| les extensions qui permettent a l'application de communiquer avec la plateforme native | 
|Contenu du répertoire "package.json" | Carte d'identitée de notre application qui contient le nom, le numero de version et les différentes dépendances.(packages) | 
|Contenu du répertoire "config.xml" |fichier de config de cordova,  plusieurs aspects du comportement de l'application sont contrôlés avec ce fichier de configuration global.  | 
|Contenu du répertoire "www/index.html" | point d'entrée de mon application.
 

|Structure d'un projet| description|
|----------------------|---------|
|Contenu du répertoire "BUILD" |contient tout le javascript que mon appli a besoin pour fonctionner| 
|Contenu du répertoire "CONFIG"|  | 
|Contenu du répertoire "node_modules" | Dossier qui contient les differents packages(complets) installés | 
|Contenu du répertoire "resources" |Dossier qui contient les differentes configurations d'images(tailles) en fonction des ecrans | 
|Contenu du répertoire "src" | dossier qui contient mes fichiers .vue, .js| 
|Contenu du répertoire "static" |Fichier .gitkeep c'est un fichier nommé que l'on ajoute dans chaque dossier que l'on souhaite garder même vide(par défaut git ne commit pas de dossier vide donc on ajoute ce fichier .gitkeep pour le conserver) on met toutes les images de mon projet pour l'application, fichier static| 
|Contenu du répertoire "www" |repertoire build du repertoire src| 





