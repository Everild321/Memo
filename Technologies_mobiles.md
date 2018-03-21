
## Développement d’une application mobile native.


![schema langage natif](http://www.mobizel.com/wp-content/uploads/2015/04/natif_generique_blanc.png)

	un SDK contient du code, permettant de concevoir une interface ou une partie d’une interface numérique
	(web, mobile, jeux, logiciels de recherches, widget météo…). 
	Ce code est conçu avec le langage de programmation correspondant au terminal (ordinateur, téléphone, tablette…)
	et au système de navigation ciblés.
Autrement dit, pour réaliser une application mobile pour iPhone par exemple, il faudra utiliser le SDK mobile iOS qui contient des fichiers de code entiers “tout prêts” qui permettent d’utiliser les fonctions natives du téléphone (GPS, bluetooth, appareil photo…) et qui proposent des éléments graphiques standards iOS.



### Trois étapes de conception

1 – **Rédaction du code source**

	Dans un premier temps, un développeur rédige le code source de la future application dans un langage approprié.

|Système d'exploitation| Langages|IDE(environnement de dev)|
|----------------------|---------|-------------------------|
|ios(Apple) |Objective C & Swift | Xcode|
|Android |Java | Android Studio ou eclipse|
|Windows Phone | C Sharp | visual Studio|

	Définition IDE : **Integrated Development Environment** (en français « environnement de développement »), 
	est un logiciel qui rassemble un certain nombre d’outils permettant de développer d’autres logiciels.

2 – **Compilation du code source**

	La compilation a un rôle primordial car les logiciels fonctionnent avec du code binaire qui 
	est trop complexe pour être conçu tel quel. 
	Il faut donc rédiger un code plus simple “human readable” (le code source) 
	qui va passer dans un compilateur et être transformé en code binaire “machine readable”. 
	Les IDE contiennent un compilateur.

3 – **Génération d’un code binaire natif**

	Le compilateur transforme le code source en code binaire et génère un fichier

|Système d'exploitation| extension de fichier|
|----------------------|---------|
|ios(Apple) | .ipa | 
|Android | .apk | 
|Windows Phone | .appx | 

## Développement d’une application mobile native iOS, Android et Windows Phone
![schema appli mobile native](http://www.mobizel.com/wp-content/uploads/2015/04/natif_ios_blanc.png)

## Différence entre Webapp, application hybride, native... 
![schema](http://www.mobizel.com/wp-content/uploads/2015/02/top.png)

### Interfaces accessibles depuis un navigateur web

	Webapp :
	Il s’agit d’un logiciel applicatif pouvant être exécuté soit :
	– depuis un navigateur web (webapp desktop). 
	Ils se présentent comme un logiciel de bureau, par exemple : les messageries web ou Pixlr
	– depuis un smartphone (webapp mobile), Exemple de webapp : Djuced

	Site mobile :
	C’est une interface accessible depuis un navigateur via une URL et
	optimisée pour une consultation mobile : 
	hiérarchie du site, ergonomie orientée tactile, médias adaptés à l’écran, etc. 
	

### Interfaces accessibles depuis les app'stores
   Il existe deux façons de développer une application mobile :

	Par du développement natif :
	Il est spécifique au système d’exploitation souhaité : pour développer une application iOS 
	il faudra utiliser le langage Objective C, pour Android Java et pour Windows Phone le langage C#. 

	Par du développement cross-platform :
	développement qui va « générer » plusieurs applications mobiles 
	en même temps pour des systèmes d’exploitations différents.

-----------------------------------------------------------------------------------------------------------------------------


![image npm](https://partners.npmjs.com/weekly/weekly32/weekly-header-grace-hopper.png)

## NPM : Package manager et task runner.

C'est le **plus grand registre de logiciels au monde**, avec environ **3 milliards de téléchargements par semaine**. 
Le registre contient plus de **600 000 paquets** (blocs de construction de code). 
Les développeurs open-source de tous les continents utilisent npm pour partager et emprunter des paquets. 
Les packages sont structurés pour vous permettre de suivre les dépendances et les versions.

**NPM** était à l’origine le package manager pour Node.js. 
Cependant, son rôle s’est aujourd’hui élargit pour devenir le **package manager du JavaScript** tout court.
Aussi bien en **front** qu’en **back**, de plus en plus de modules et bibliothèques utilisent aujourd’hui **NPM**. 
On en fait même un **task manager** grâce aux scripts qu’il permet d’exécuter. 
Cela permet d’avoir un seul outil pour l’ensemble de nos process.

**node.js** = 

	Node.js est une plateforme logicielle libre et événementielle 
	en JavaScript orientée vers les applications réseau qui doivent pouvoir monter en charge.

**Task manager** = 

	Gestionnaire de tâches, outil présent sur des systèmes d'exploitation qui permet 
	d'afficher les applications et processus en cours d'exécution, de les arrêter, 
	modifier leurs priorités, de basculer d'un programme à un autre, 
	d'accéder aux fonctions de démarrage et d'extinction, et de contrôler des informations de performances.

1.npm se compose de trois composants distincts:

	* le site Web
	* le registre
	* l'interface de ligne de commande (CLI)



-----------------------------------------------------------------------------------------------------------------------------


![image vue.js](https://softwareengineeringdaily.com/wp-content/uploads/2015/12/vuejs.jpg)
 
**VueJs a été créé en 2014** par Evan You, inspiré d'AngularJS.
 C'est une **librairie** qui permet de créer des **interfaces web interactives** en se reposant sur le principe des composants webs.
 Il propose un système de **data-binding** réactif capable de détecter automatiquement les changements d'états du composant.
 **(Il s'agit d'un moyen de lier la partie vue à la partie logique,les éléments de votre code HTML seront liés à votre contrôleur JavaScript. )**
 **point forts:**

	 léger: 23ko
	 performant: Framework le plus rapide du marché
	 simple: Facile pas besoin de bibliotheques externes ni de plugins, code source tres lisible.
	 	(1 journée suffit pour apprendre à s'en servir)


----------------------------------------------------------------------------------------------------------------------------

![image cordova](https://cordova.apache.org/static/img/artwork/cordova_logo_dark_gray_large.png)

Apache Cordova est un **framework de développement mobile open-source**. 
Il vous permet d'utiliser les technologies Web standard 
- HTML5, CSS3 et JavaScript pour le développement multiplateforme. 
Les applications s'exécutent dans des enveloppes ciblées sur chaque plate-forme 
et s'appuient sur des liaisons API conformes aux normes pour accéder aux capacités 
de chaque périphérique telles que les capteurs, les données, l'état du réseau, etc.


![schema](https://www.samirkamble.com/wp-content/uploads/2017/02/cordova-application-flow-chart.png)

1.Apache Cordova est un compilateur qui a son propre SDK (Fonctionnalité native de l'appareil: appareil photo, GPS...)

2.les OS ont chacun leur propre IDE (sert à interpreter la compilation Cordova.)
exemple: Android studio pour Android

# Single PAge App

![schema single page](http://www.wavemaker.com/8/learn/wp-content/uploads/Single_Page_appvsTraditional_app.png)

**Web app qui a une seule page**, la partie MVC est pour partie déportée côté client.
C'est le **JAvascript qui s'occupe du routing** en fonction de l'url (tout se passe côté client).
Réecrit de maniere dynamique la page en cours plûtot que de recharger des pages entieres à partir d'un serveur.
**tout le code (HTML, JS +CSS) est récupéré avec un seul chargement de page.**

# GLOSSAIRE

|Glossaire| Définition	|
|---------|-------------|
|Xcode | Environnement de développement pour macOS, ainsi que pour iOS, watchOS et tvOS.| 
|Objective-C| Langage de programmation orienté objet réflexif*, extension du C qui se distingue par sa distribution dynamique des messages, principalement utilisé dans les systémes d'exploitation Apple|
|reflexif|*capacité d'un programme à examiner, et éventuellement à modifier, ses propres structures internes de haut niveau lors de son exécution.*| 
|Android Studio| Environnement de développement d'application Android | 
|Eclipse| IDE, kit de developpement ecrit en Java  		|
|Java| Langage de programmation orienté objet, Java permet de développer des applications client-serveur.|
|SDK | Kit de developpement informatique, ensemble d'outils utilisés pour le développement d'un logiciel destiné à une plateforme déterminée (Linux, Windows, Android, etc.). composé, a minima, d'un traducteur capable de traduire le langage de programmation en langage machine, d'un éditeur de liens en mesure de relier, en un fichier exécutable, différents éléments et de bibliothèques de routines. |
|PhoneGap  |  framework destiné à faciliter la création d'applications mobiles pour différentes plateformes - Android, iOS, Windows Phone. Développé par Adobe Systems, il est basé sur Apache Cordova et distribué sous licence open-source, Les applications qui en résultent sont hybrides, ce qui signifie qu'elles ne sont ni vraiment natives, ni purement basées sur les langages HTML, CSS et JavaScript.|
|React|  bibliothèque JavaScript libre développée par Facebook depuis 2013. Le but principal de cette bibliothèque est de faciliter la création d'application web monopage, via la création de composants dépendant d'un état et générant une page HTML à chaque changement d'état. React est une bibliothèque qui ne gère que l'interface de l'application, considéré comme la vue dans le modèle MVC  |
|Angular | AngularJS3 est un framework JavaScript libre et open source développé par Google. Il permet de développer des pages web.             |
|Ionic   | Basé initialement sur AngularJS et Apache Cordova2, Ionic permet de créer un code multisupport en utilisant des outils Web comme HTML, CSS, JavaScript, afin de générer des applications iOS, Android, Chrome, Windows Phone et bien d'autres.           |
|App native | Une application native est une application mobile qui est développée spécifiquement pour un des systèmes d’exploitation utilisé par les smartphones et tablettes (iOS, Android, etc.) Permet généralement d’utiliser toutes les fonctionnalités liées au système d’exploitation visé (GPS, accéléromètre, appareil photo, etc.) et permet également de proposer des applications généralement plus riches que les web applications en HTML5. Une fois téléchargées et installées certaines applications peuvent par ailleurs être utilisées sans connexion Internet. ne peut être distribuée que par l’intermédiaire des plateformes d’applications (voir Android Market et App Store) qui contrôlent sa nature et ses contenus et qui prélèvent une partie du prix de vente lorsqu’elle est payante.         |
|App hybride|Une application hybride est une application utilisant le navigateur web intégré du support (Smartphone ou tablette) et les technologies Web (HTML, CSS et Javascript) pour fonctionner sur différents OS (iOS, Android, Windows Phone, etc.). Une telle application utilise les fonctionnalités natives des Smartphones et peut être distribuée sur les plateformes d’applications telles que l'AppStore... |
|webApp| logiciel applicatif hébergé sur un serveur et accessible depuis un navigateur Internet. Elle a une ergonomie et des fonctionnalités spécifiques adaptées aux contraintes des terminaux mobiles et ne peut pas fonctionner sans connexion Internet.               |
|compilateur|terme utilisé pour désigner un programme qui transforme un code source écrit dans un langage de programmation (le langage source) en un autre langage informatique (appelé langage cible)1. Pour qu'il puisse être exploité par une machine, le compilateur traduit le code source, écrit dans un langage de haut niveau d'abstraction, facilement compréhensible par l'humain, vers un langage de plus bas niveau, un langage d'assemblage ou langage machine|
|API | Application Programming Interface, est une interface pour les applications, car un logiciel n’a pas de mains ni d’yeux pour interagir avec les interfaces physiques ! |
|Restful | Une API compatible REST, ou « RESTful », est une interface de programmation d'application qui fait appel à des requêtes HTTP pour obtenir (GET), placer (PUT), publier (POST) et supprimer (DELETE) des données.| 
|Schema|![schema](https://www.supinfo.com/articles/resources/213817/5642/1.png) |
| Stores : Play Itunes| Magasin d'applications |
|Task Runner | outil qui permet d’automatiser les tâches répétitives, Grunt est le plus populaire des Tasks Runners. Historiquement c’est l’un des plus anciens et il dispose d’un nombre de modules important pour résoudre les problématiques.|
|Dépendance  |           |
|json| JavaScript Object Notation (JSON) est un format de données textuelles dérivé de la notation des objets du langage JavaScript. Il permet de représenter de l’information structurée comme le permet XML par exemple|

## Différences entre Jquery et VueJS

**Jquery** = Bibliotheque Javascript, créée pour faciliter l'ecriture javascript.
Permet la manipulation du DOM.

**Vuejs** = Framework MVC, on peut
utiliser des templates HTML directement dans le DOM
(permet à des scripts d'examiner et de modifier le contenu du navigateur web)
Les composants peuvent être déclarés simplement dans un fichier Javascript et attachés à des templates dans notre HTML sous la forme de fichiers .vue
on ne manipule pas le dom a la main. a travers nos data.


## Promesses 
une promesse est un objet qui est renvoyé et auquel on attache des callbacks plutôt que de passer des callbacks à une fonction. Ainsi, au lieu d'avoir une fonction qui prend deux callbacks en arguments :

	faireQqc(successCallback, failureCallback);

On aura une fonction qui renvoie une promesse et on attachera les callbacks sur cette promesse :

	let promise = faireQqc();
	promise.then(successCallback, failureCallback);
ou encore :

	faireQqc().then(successCallback, failureCallback);

Cette dernière forme est ce qu'on appelle un appel de fonction asynchrone. Cette convention possède différents avantages dont le premier est le chaînage.

Transformer une action en promesse
Afin de pouvoir prendre les commandes aussi vite que possible, le cabanon du Burger utilise un système de sonnerie. Quand un client passe une commande en caisse, la personne au comptoir vous tend un plateau sur lequel est posé un bipeur en échange du paiement.
![schema burger](https://d33wubrfki0l68.cloudfront.net/ded6763744b8ec6b1b645e38ebaf73a73194299b/1aa64/assets/img/2017/03/promise-burger-party-2.png)


Le plateau est une promesse de la part du cabanon du Burger, ils y déposeront leur délicieux burger une fois qu’il sera prêt, le bipeur est un indicateur de l’état de la commande. Quand le bipeur ne sonne pas, ça veut dire que la commande est en attente - l’équipe en cuisine s’affaire à préparer votre commande. Quand le bipeur passe au rouge et sonne, ça veut dire que la commande est traitée.

Attardons nous plus précisément sur ce que veut dire traitée. Cela ne veut pas dire « prête ». Cela signifie que la commande a été traitée en cuisine et qu’on prévient le client pour lui demander ce qu’il veut faire. Vous avez surement envie (en tant que client) d’aller chercher votre commande au comptoir, mais dans certains cas, il se peut que vous décidiez de partir car l’attente est trop longue. Ça depend de vous.

Regardons ce que vous avons jusque ici dans le code. Quand vous appelez la fonction commander, elle « retourne une promesse » (elle vous donne un plateau avec un bipeur). Une valeur en retour (un burger) devrait arriver sur votre plateau une fois que la promesse a été tenue et une fonction de callback est appelée. On va en parler plus en détail dans la prochaine partie !

![schema function](https://d33wubrfki0l68.cloudfront.net/1920d3102906e38117241852f199b7999f49d974/634aa/assets/img/2017/03/promise-burger-party-3.png)

Ajout des gestionnaires de promesse
On dirait que le bipeur sonne, allons au comptoir pour récupérer notre commande. Il y a deux scénarios possibles à ce moment là.

![schema ok/pas ok](https://d33wubrfki0l68.cloudfront.net/17bbfed893602da194664bb7ce94019f9471f1fa/88edf/assets/img/2017/03/promise-burger-party-4.png)

1. La commande est honorée
Youpi ! Votre burger est prêt, l’équipe en cuisine vous tend un burger fraîchement préparé. La promesse d’un bon burger a été tenue !

2. La commande est rejetée
On dirait que la cuisine est à cours de steaks pour burger, la promesse d’un burger a été rejetée. Demandez à vous faire rembourser !

## Requetes HTTP
Il existe quatre types de **requêtes HTTP** couramment utilisées - **GET**, **POST**, **PUT**, et **DELETE**.
Dans cette leçon, nous serons seulement écrire GETet POSTdemandes. 
**GET** Les demandes reçoivent des informations d'autres sites en envoyant une requête . 
**POST** les demandes peuvent changer les informations sur un autre site et recevront des informations ou des données en réponse.

Une **GET demande** est comme une recherche. Si vous accédez à Google et recherchez quelque chose, on remarque que tous nos termes de recherche sont ajoutés à l'URL, comme ceci:

	https://www.google.com/#q=pizza+near+union+square

Cette URL dit "Google, s'il vous plaît récupére une liste de pizza près de Union Square." Il n'apporte aucune nouvelle information à Google.


![schema Get](https://s3.amazonaws.com/codecademy-content/courses/intermediate-javascript-requests/diagrams/Asset+1.svg)

1.Sur la première ligne, nous créons un **objet XMLHttpRequest**Nous faisons cela en tapant **new**, le type d'objet, XMLHttpRequest(). 
C'est ce qu'on appelle le nouvel opérateur.
L'objet est enregistré dans un constappelé xhr

2.Sur la ligne suivante, nous sauvegardons l'URL vers laquelle nous allons faire notre demande dans un **const** appel **url**.

3.Nous mettons le **responseType** de l' **xhr** objet à **'json'**

4.**onreadystatechange** est un gestionnaire d'événements appelé chaque fois que la valeur de la **readyState**propriété change. Nous le mettons égal à une fonction anonyme. Cette fonction va gérer la réponse à notre demande.

5.On verifie si le readyStatede notre xhrobjet est égal à XMLHttpRequest.DONE. Si cela se traduit par true, le code dans le bloc s'exécute.

6.Ensuite, nous appelons la **.open()**méthode sur notre **xhr**objet et lui passons deux arguments - **'GET'**(le type de requête) et**url**, l'URL que nous interrogeons. **.open()**crée et structure la demande. Il indique à la requête quelle méthode utiliser **GET**ou **POST** quelle URL utiliser pour la requête.

7.Finalement, nous appelons la **.send()**méthode sur notre **xhr**objet et ne lui transmettons aucun argument. En effet, les données envoyées dans les **GET** demandes sont envoyées dans le cadre de l'URL. L'appel de la **.send()**méthode envoie l' **xhr** objet avec ses informations pertinentes à l'URL de l'API.


Une **POST demandes** introduit de nouvelles informations sur un autre site Web. Au lieu d'envoyer cette information dans l'URL de la requête, elle est envoyée dans le corps de la requête.

![schema Post request](https://s3.amazonaws.com/codecademy-content/courses/intermediate-javascript-requests/diagrams/Asset+2.svg)

### Rappel

dans une **POST requête**, les informations sont envoyées au serveur dans le corps de la requête. Cette information est créée et enregistrée dans la dataconstante et envoyée à l'API en tant qu'argument transmis à la .send()méthode.

Les deux premières lignes de cette requête sont identiques aux deux premières lignes de la **GET**requête. 
La troisième ligne est nouvelle. 
Les données que nous voulons envoyer à notre **API** doivent être correctement formatées. 
Les propriétés et les valeurs particulières envoyées dépendront de l'API que vous utilisez et des informations que vous souhaitez envoyer et récupérer.

L'objet contenant ces données est transmis à la **JSON.stringify()** méthode, qui formatera l'objet sous forme de chaîne. Ceci est enregistré dans un const data.

Tout le reste reste le même jusqu'aux deux dernières lignes. Lorsque nous appelons la **.open()** méthode sur l' **xhr** objet, nous passons l'argument **'POST'** au lieu de **'GET'**. Enfin, nous passons la datachaîne à la **.send()méthode.**