# LARAVEL
Framework PHP

## Mise en oeuvre:
* **1.Configuration des extensions nécessaires pour PHP.**

le fichier de configuration de php -> php.ini (dans Wamp)
     il est necessaire de décommenter les lignes.

        ;extension = php_mbstring.dll

        ;extension = php_openssl.dll

        Permet d'activer les extensions Mbstring et Openssl requises pour Laravel et Composer.

        Pour celà, il faut aller dans le wamp php -> extensions php et vérifier si c'est bien coché.

* **2.Installation de Composer** 

        getcomposer.org/download

        Telecharger Composer-setup.exe, vérifier le chemin (C:\PHP\php.exe)

* **3.Ouvrir la commande windows**

        php --version

        composer --version

* **4.Création de notre 1er Projet Laravel**

        Dans le Bash -> 
        composer create-project --prefer-dist

        laravel/laravel nomduDossier

        cd 'dossier'

        php artisan serve

        le site est accessible (http://127.0.0.1:8000) 

# Installation Debugbar

        composer require barryvdh/laravel-debugbar --dev
--dev = S'installe uniquement sur l'outil developpement.

        Pour désinstaller la Debugbar côté client 
        root@ilot6:/var/www/astrid.com/mcafe_laravel# composer install --no-dev

# Routes
Le systeme des routes nous permet de faire correspondre un morceau de code aux différentes Urls de notre application.
dans le fichier routes -> web.php
```php
Route::get('/',function(){
    return view('welcome');
});
```
**View = Représentation des données**

## Comment créer d'autres Routes

```php
Route::get('/',function(){
    return view('welcome');
});

Route::get('1',function(){
    return view('boisson');
});


```

On peut utiliser un paramètre pour une route qui accepte des éléments variables:

```php
Route::get('{n}',function($n){
    return 'je suis à la page'.$n.'!';

    ->where ('n', '[1-5]'); //contrainte pour accepter que certaines valeurs
});
```

## Route nommée:

Il est parfois utile de nommer une route, par exemple pour génerer une Url ou pour effectuer une redirection.

```php
Route::get('/',['as'=>'home',function(){
    return 'je suis à la page d\'accueil';

}]);
```

# les Controllers

* Les contrôleurs peuvent regrouper la logique de gestion des requêtes associée dans une classe unique. 
* Les contrôleurs sont stockés dans le 
répertoire.app/Http/Controllers

La tâche d'un contrôleur est de réceptionner une requête
(qui a déjà été triée par une route) et de définir la réponse appropriée.

![schema rôle du controller](https://sdz-upload.s3.amazonaws.com/prod/upload/img22.JPG)


## Pour créer un contrôleur:

Nous allons utiliser Artisan (Boite à outil Laravel)
dans la console on entre:

    php artisan make:controller welcomeController 

## Liaison avec les Routes:
Dans le fichier web.php (dossier Routes)

    Route::get('/','welcomeController@index');

Dans le controller la methode **show** permettra de générer la vue.

# Créer un Formulaire via Laravel
-----------------------------------------------------------
Afin d’afficher le formulaire HTML, nous avons besoin de créer une nouvelle route avec une nouvelle vue.

```php
<?php
Route::get('/inscription', function () {
    return view('inscription');
});

?>
```

```php

@extends('layout')

@section('contenu')
    <form action="/inscription" method="post">
        <input type="email" name="email" placeholder="Email">
        <input type="password" name="password" placeholder="Mot de passe">
        <input type="password" name="password_confirmation" placeholder="Mot de passe (confirmation)">
        <input type="submit" value="M'inscrire">
    </form>
@endsection


```

Le formulaire HTML est très classique. Je le redirige vers l’URL /inscription avec une méthode HTTP POST.

Lorsque nous essayons de valider ce formulaire, nous obtenons une erreur de type MethodNotAllowedHttpException.

-------------------------------------------------------------------------
# Ajout d’une nouvelle route pour traiter le formulaire
L’URL /inscription existe déjà dans notre fichier routes/web.php mais la route existante ne répond qu’aux requêtes de type GET. Or, notre formulaire envoie une requête de type POST. Pour créer une route répondant au type POST, rien de plus simple :

```php
Route::post('/inscription', function () {
    return 'Formulaire reçu';
});

```
Lorsque nous renvoyons à nouveau le formulaire, une nouvelle erreur s’affiche « This page has expired due to inactivity ».

-------------------------------------------------------------------------
# Le problème du CSRF
Le CSRF est un type d’attaque très répandu sur le web. Laravel nous protège par défaut de ces attaques dans nos formulaires. Mais pour prévenir Laravel que notre formulaire est sécurisé, nous avons besoin d’ajouter une ligne dans notre HTML :

```php

@extends('layout')

@section('contenu')
    <form action="/inscription" method="post">
        {{ csrf_field() }}

        <input type="email" name="email" placeholder="Email">
        <input type="password" name="password" placeholder="Mot de passe">
        <input type="password" name="password_confirmation" placeholder="Mot de passe (confirmation)">
        <input type="submit" value="M'inscrire">
    </form>
@endsection


```

Via la ligne csrf_field(), Laravel va ajouter un champ caché à notre formulaire (de type hidden) contenant une chaîne de caractères aléatoires. Et ce champ va lui permettre de protéger notre formulaire automatiquement contre les attaques de type CSRF.

En entrant à nouveau les données dans notre formulaire, cette fois ci tout fonctionne !

# Récupération des données envoyées

Nous pouvons récupérer les données envoyés par le visiteur via la méthode PHP traditionnelle :

```php
Route::post('/inscription', function () {
    return 'Votre email est ' . $_POST['email'];
});

```

Nous pouvons également utiliser la méthode Laravel qui permet de récupérer non seulement les paramètres de type GET, les paramètres des URLs mais aussi les paramètres de type POST : la fonction request().

```php
Route::post('/inscription', function () {
    return 'Votre email est ' . request('email');
});

```


![schema get/post](https://s3-eu-west-1.amazonaws.com/sdz-upload/prod/upload/img41.PNG)


* **1** : le client envoie la requête de demande du formulaire qui est transmise au contrôleur par la route (non représentée sur le schéma),
* **2** :le contrôleur crée la vue « infos »,
* **3** :la vue « infos » crée le formulaire,
* **4** :le formulaire est envoyé au client,
* **5** :le client soumet le formulaire, le contrôleur reçoit la requête de soumission par l’intermédiaire de la route (non représentée sur le schéma),
* **6** :le contrôleur génère la réponse,
* **7** :la réponse est envoyée au client.

# Connection à la base de donnée
Pour la gestion de l’environnement, Laravel fait usage d’un package tiers : .Env
 Quand on installe Laravel avec Composer on va trouver à la racine le fichier .env avec ce contenu 

```php
APP_ENV=local
APP_KEY=
APP_DEBUG=true
APP_LOG_LEVEL=debug
APP_URL=<a href="http://localhost">http://localhost</a>

DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=homestead
DB_USERNAME=homestead
DB_PASSWORD=secret

BROADCAST_DRIVER=log
CACHE_DRIVER=file
SESSION_DRIVER=file
QUEUE_DRIVER=sync

REDIS_HOST=127.0.0.1
REDIS_PASSWORD=null
REDIS_PORT=6379

MAIL_DRIVER=smtp
MAIL_HOST=mailtrap.io
MAIL_PORT=2525
MAIL_USERNAME=null
MAIL_PASSWORD=null
MAIL_ENCRYPTION=null

PUSHER_APP_ID=
PUSHER_KEY=
PUSHER_SECRET=

```

La Partie qui nous interesse est la DB_(DataBase):

* 1.Ouvrir le Fichier .env

* 2.Compléter les infos DB_
    * DB_CONNECTION=mysql
    * DB_HOST=127.0.0.1
    * DB_PORT=3306
    * DB_DATABASE= **nom de la BDD**
    * DB_USERNAME= **Identifiant**
    * DB_PASSWORD= **Password**

* 3.Ouvrir les fichiers Controller.
On va les connecter à la base.
```php

public function index(){
        $boissons = DB::select('select * from boissons');

        return view('boissons',compact('boissons'));
    }

}
```
* On définit une variable $boissons qui va prendre pour valeur 
le select de la DB(database) avec la requête que l'on souhaite.
* on retourne la vue fichier.blade(ici boissons.blade)
ainsi que le résultat de la variable boissons que l'on précede d'un compact.

* 4.On modifie les fichiers.blade:
```php
@foreach($boissons as $keys)
     {{$keys-> Nom}}:{{$keys-> Prix}} cts


@endforeach

```

# Exécution de requêtes SQL brutes

Une fois que nous avons configuré notre connexion à la BDD, nous pouvons exécuter des requêtes à l'aide de la **DB** façade. La **DB** façade fournit des méthodes pour chaque type de requête: **select, update, insert, delete, et statement**.

## Exécution d'une requête de sélection
-----------------------------------------------------------
```php
<?php

namespace App\Http\Controllers;

use Illuminate\Support\Facades\DB;
use App\Http\Controllers\Controller;

class UserController extends Controller
{

    public function index()
    {
        $users = DB::select('select * from users where active = ?', [1]);

        return view('user.index', ['users' => $users]);
    }

}
```

* Le premier argument passé à la **select** méthode est la requête SQL brute.
* le second argument est toute liaison de paramètre qui doit être liée à la requête. 
* Typiquement, ce sont les valeurs des **where** contraintes de la clause. 
* La liaison de paramètres fournit une protection contre l'injection SQL.


* La **select** méthode retournera toujours un **array** des résultats. 
* Chaque résultat dans le tableau sera un **StdClass** objet PHP , vous permettant d'accéder aux valeurs des résultats:

```php
foreach ($users as $user) {
    echo $user->name;
}

```   

## Utilisation de liaisons nommées
----------------------------------------------------------
Au lieu d'utiliser **?** pour représenter vos liaisons de paramètres, on peut exécuter une requête en utilisant des liaisons nommées:
```php
$results = DB::select('select * from users where id = :id', ['id' => 1]);

```

# Générer des migrations
----------------------------------------------------------
* 1.J'ai crée une Nouvelle base de donnée sur mon phpmyadmin.
* 2.J'ai ouvert le fichier .env dans lequel j'ai renseigné le nom de ma nouvelle base de donnée.
* 3.j'ai géneré un nouveau model à l'aide de la commande suivante (le -m permet de créer mon fichier de migration).

```php
php artisan make:model Boisson -m
```

* 4.dans mon fichier Migrations je retrouve bien ma table 

        2018_01_24_153904_create_boissons_table.php

* 5.Dans ma public function up() j'ajoute mes tables
Nom, Prix....
```php
public function up()
    {
        Schema::create('boissons', function (Blueprint $table) {
            $table->increments('idBoissons');
            $table->string('code',3);
            $table->string('Nom');
            $table->integer('Prix');
            $table->timestamps();
        });
    }
```

* 6.Pour deposer toutes les tables et créer la migration, on utilise la commande 

```php
php artisan migrate

```
* 7.Mon model crée avec la table se retrouve dans le dossier app.

* 8.les tables figurent sur ma nouvelle base de données.