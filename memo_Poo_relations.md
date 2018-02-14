# Définir les relations

Les relations sont définies comme des méthodes sur nos classes de **Models**.
Les relations servent de puissants constructeurs de requêtes.

## Un par un 
Une relation un à un est une relation basique.
ex: un user peut être associé à un phone.

```php
	 class User extends Model
{
    /**
     * Get the phone record associated with the user.
     */
    public function phone()
    {
        return $this->hasOne('App\Phone');
    }
}
```

## Définir l'inverse de la relation 
Nous allons définir une relation sur le phone model qui nous permettra d'accéder au User qui appartient au telephone.
Nous utiliserons la methode belongsTo

```php
	class Phone extends Model
{
    /**
     * Get the user that owns the phone.
     */
    public function user()
    {
        return $this->belongsTo('App\User');
    }
}


```


## Comment lier nos Models
Dans l'exemple de ma machine à cafe je vais lier mon model Boisson et mon model Ingredient à mon model Recette.

```php
use App\Recette;

class Ingredient extends Model
{
    protected $table = 'ingredients';
    protected $primaryKey = 'id';

    public function recette()
    {
        return $this->hasmany('App\Recette');
    }
```

* Je fais de même pour le model Boisson.
* Ensuite j'ouvre mon model Recette et je vais lui donner une relation avec ces 2 Models.

```php
use App\Boisson;
use App\Ingredient;

class Recette extends Model
{
    protected $table = 'recettes';
    protected $primaryKey = 'idRecette';


    public function ingredient()
    {
        return $this->belongsTo('App\Ingredient','idIngredient');
        
    }

    public function boisson()
    {
        return $this->belongsTo('App\Boisson','idBoisson');
    }

}
```

* Une fois que les relations sont créées, je vais créer mes functions sur le RecettesController.php
* Je n'oublie pas de lier mes models à mon controller.

```php
use App\Boisson;
use App\Ingredient; //je lie mon controller aux differents models que j'utilise.
use App\Recette;
```

```php
class RecettesController extends Controller
{
    public function index(){
    $afficheBoissons= Boisson::all();

    return view('recette',compact('afficheBoissons'));
    }

// permet d'afficher la liste des boissons sur ma page recette.

public function show($id){
    $relations= Recette::whereIdboisson($id)->get();
    return view('detailsRecettes',compact('relations'));

    }
// permet d'afficher mes relations d'apres le model Recette en fonction de l'id
    

     
}

```


# Mise en place de l'Authentification
Laravel fournit un moyen rapide d'échafauder toutes les routes et vues dont nous avons besoin pour l'authentification en utilisant une simple commande:

    Php artisan make:auth

Installera :

    1.une vue de mise en page. 
    2.des vues d'enregistrement et de connexion, ainsi que des routes pour tous les points d'extrémité d'authentification. 
    3.Un HomeController pour gérer les demandes post-connexion au tableau de bord de notre application.

Les vues seront disponible dans le répertoire
resources->views->auth