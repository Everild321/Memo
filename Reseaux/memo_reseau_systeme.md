# RESEAU & SYSTEME

**LINUX**
Linux est un système d’exploitation (comme windows).
c’est une interface qui fait et qui simplifie la liaison entre l’utilisateur, la machine et les applications installées dessus.
Linux est apprécié pour sa stabilité, flexibilité et sa gratuité, plusieurs versions existent.

**DEBIAN**
est la seule distribution qui soit gérée par des développeurs indépendants plutôt que par une entreprise. C'est une des distributions les plus populaires.
Un autre gros avantage de Debian est le gestionnaire de paquets apt-get. C'est un programme qui gère tous les logiciels installés et qui nous permet de les désinstaller en un rien de temps. D'autre part, tous les logiciels sont centralisés en un même endroit, ce qui fait que nous n'avons pas à parcourir tout le Web pour retrouver un programme.  

--------------------------------------------------------------

# Expliquer ce qu'est un serveur Web

Un **serveur web** est spécifiquement un *serveur multi-service* utilisé pour publier des *sites web* sur *Internet* ou un *intranet*. 
L'expression « serveur Web » désigne également le logiciel utilisé sur le serveur pour exécuter les requêtes HTTP. 

![schema serveur web](https://i.ytimg.com/vi/msB9AvJ4bTM/hqdefault.jpg)

    • Sert à stocker des fichiers.

    • pouvoir répondre à la requête d’un ordinateur en demandant une page web.

    • envoyer un fichier à un ordinateur grâce au protocole http et https.

# Installer un environnement web (apache, mysql, php) 

**1.Mettre à jour les logiciels installés**
Mettre à jour la liste des dépôts et des paquets installés :
apt-get update && apt-get upgrade
Attention: mettre à jour régulièrement (environ 1fois/semaine)


**2.Installer MySQL**
Pour installer MySQL, saisissez la commande suivante :

	apt-get install mysql-server mysql-client
L'outil de gestion des paquets nous invite à définir le mot de passe du compte root de la base. 
On peut créer d'autres comptes utilisateurs après avoir installé phpMyAdmin.

**3.Installer Apache2**
Pour installer Apache 2, exécuter la commande suivante :

	apt-get install apache2 apache2-doc

**3.3 Tester le fonctionnement d' Apache 2**
Vérifiez le bon fonctionnement du serveur apache en visitant l'adresse de votre serveur, par exemple http://<adresse_ip_de_mon_serveur>
La page de bienvenue comme ci-dessous doit s'afficher.
![image accueil apache2](https://www.karolak.fr/images/blog/apache-worker.png)

ou depuis le serveur avec la commande lynx

	apt -get install lynx
lynx http://51.15.134.133

**4.Installer php7**
Pour installer php7, la commande est la suivante :

	apt-get install php php-mysql libapache2-mod-php


# LES COMMANDES LINUX

**pwd** voir ou on se situe sur la machine (répertoire, dossier)
Cette commande affiche tout simplement le chemin absolu du dossier dans lequel on se trouve.

**Clear** nettoie votre fenêtre de terminal en reléguant tout le texte au dessus (donc accessible avec un scroll) et vous laissant donc face à une fenêtre clean. Bien utile de temps à autre pour y voir plus clair. 

**nano** créer un fichier texte.

**Cd** change directory (changer de dossier)

**Ls** lire le contenu d’un répertoire.

**Cat** affiche le contenu d’un fichier.
**Ctrl O** pour enregistrer
**Ctrl X** pour sortir 

**Ctrl C** pour revenir sur la commande bash

**Rm** effacer un fichier

**mv** déplacer un fichier 

**mkdir**  créer un dossier 

**wc** word count, permet de compter le nombre de lignes, de mots et de caractères dans un fichier texte. Les options sont-lpour line (nombre de ligne),-w pour word (nombre de mots) et -m pour le nombres de lettres. Il y a aussi l’option -c pour avoir la taille du fichier en bits. Pour l’utiliser, on fourni simplement en paramètre l’adresse du fichier texte : 

**grep** permet d’effectuer des recherches par expressions régulières.
Dans sa forme la plus simple, grep permettra d’afficher la ligne contenant un mot clef .

*Ex:*

grep B My_team/*.player = grep recherche Dossier /*Fichier


Par défaut grep tient compte de la casse.
Pour que grep renvoie toutes les lignes on utilise l’option 

**-i** 
grep -i

**-n** permet de connaître les numeros des lignes.
	grep -n mot fichier.md

**-v** pour connaître toutes les lignes qui ne contiennent pas un mot donné,

**-r** rechercher dans tous les fichiers et sous dossiers.

**-c** compte le nombre de lignes contenant la chaîne
	grep -c mot fichier.md

**-x** ligne correspondant exactement à la chaîne(mot pour mot)




**Find** commande de recherche par excellence pour retrouver des fichiers, mais aussi pour effectuer des operations sur chacun des fichiers trouvés.

Find ne va pas lire dans une BDD mais au contraire parcourir tout notre disque.

*Ex:* find -name «christian.player» 