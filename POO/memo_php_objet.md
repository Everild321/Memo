# Programmer en orienté Objet en PHP (POO)

* La **POO** (programmation orientée objet) 
est une forme particulière de programmation destinée à **faciliter la maintenance et la réutilisation / adaptation de vos scripts PHP**. 
* Elle consiste à représenter des **objets** (du monde réel ou non) sous une forme d'entités informatiques. 
* On représente généralement un **objet global** par ce que l'on appelle une **classe**. 

* Une **classe** va regrouper un ensemble de **fonctions et de propriétés** pouvant **agir sur l'objet**. 
* Si on prend par exemple une voiture dans le monde réel, on peut modéliser une voiture par une **classe "Voiture"** qui aura comme **propriétés le nombre de roues, le nombre de portes, etc ...**

## Rappel sur les Classes et les Objets

Le PHP orientée objet **permet à votre code de rester souple** en lui permettant d'être seulement défini une fois, mais utilisé de nombreuses fois à de nombreux endroits.


## Classe

Les Classes contiennent la définition des objets.
* une **classe** est une entité regroupant des **variables et des fonctions**.
* **Instancier une classe** c'est se servir d'une classe afin qu'elle nous **créee un objet**.
* **Instance = Objet**
* Pour **créer un Objet** on utilise **new** devant la classe

```php
<?php
      // Créez une classe Person ici :
      class Personnage{
          
      }
      
      // Et créez une instance de la classe appelée $me :
      $perso = new Personnage();

      ?>
 ```

## Appeler les méthodes de l'objet

Pour appeler une méthode(function) d'un objet, on utilise l'operateur
-> qui sert à accéder à un élément de la classe.

```php

 $perso->parler()

``` 

## Accéder à un élément depuis la classe.
```php
 <?php
    class Personnage
    {
      private $force;
      private $experience;
      private $degats,
    }

    $perso= new Personnage; // On crée une instance de la classe Personnage 

``` 

* Dans notre Script, $perso représente l'objet.
* Dans notre méthode nous n'avons pas cette variable pour accéder à notre attribut $experience pour le modifier.

```php
<?php 
  class Personnage 
  {
    private $experience = 50;

      public function afficherExperience()
      {
        echo $this-> experience;
      }

  }
?>
``` 

## Constructeurs 

* construct(), le constructeur sert à construire l'objet.
*  Une fonction constructeur **__construct()** est une fonction spéciale (magique) qui est **appelée automatiquement lorsqu'une instance d'objet est créée avec le mot clé 'new'.** 
* Un constructeur peut avoir n'importe quel nombre de paramètres définis par l'utilisateur.
* Le constructeur est executé dès la création de l'objet et est utilisé pour initialiser l'objet.

```php
    public function --construct($force, $degats)

```

* Initialiser un paramétre
```php
    public function --construct($id)
    {
      $this->id= $id;
      $this->speed= 30;
      $this->life=100;
    }
``` 


## Mutateur ou setter 

```php 
    
```
## Heritage

L'héritage est un moyen pour une classe fille de récupérer les propriétés et les méthodes d'une autre classe (parent).
Nous pouvons faire en sorte qu'une classe PHP puisse hériter d'une autre avec le mot-clé **extends** (étendre).

```php
 <?php
        class Shape {
          public $hasSides = true;
        }
        
        class Square extends Shape {
        
        }
        
        $square = new Square();
        // Ajoutez votre code ici !
        if (property_exists($square,"hasSides")) {
          echo "J'ai des côtés !";
        }
      ?>

 ```

## Ecraser une méthode parente

nous voulons une classe fille (ou sous-classe) pour être en mesure de remplacer une propriété ou une méthode de la classe parente (ou super classe).

```php
    class Shape {
       $sides = true; 
    } 

    class Square extends Shape {
       $sides = 4; 
    } 

```
la classe fille aura toujours priorité sur la version héritée du parent.

```php
 <?php
        class Vehicle {
          public function honk() {
            return "HONK HONK!";
          }
        }
        // Ajoutez votre code ici :
        class Bicycle extends Vehicle {
            public function honk(){
                return "Beep beep!";
            }
           
        }
        $bicycle = new Bicycle();
        echo $bicycle->honk();
        
            ?>
```

## Le mot de la fin : final

En PHP, une classe parent peut empêcher ses enfants de pouvoir écraser certaines de ses méthodes. Cela se fait en utilisant le mot-clé... final.

```php
<?php
        class Vehicle {
          final public function honk() {
            return "HONK HONK!";
          }
        }
        // Ajoutez votre code ici :
        class Bicycle extends Vehicle {
            
        }
        $bicycle = new Bicycle();
        echo $bicycle->honk();
        
     ?>
 ```    

## Les constantes de classe et l'opérateur de résolution de portée

Parfois nous voulons des propriétés qui ne changent pas. 
Celles-ci sont précédées du mot-clé **const** (const pour constant). 
Pour bien les diférencier des variables, lors de la déclaration d'une constante, le signe $ disparaît.
La **valeur** de la constante **doit être une chaine de caractère** ou **un nombre**, mais ne peut pas fournir à une constante le contenu d'une variable ou le résultat de l'appel à une fonction.

PHP permet que nous fixions des constantes au niveau des classes. 
On pourra utiliser cette constante à l'intérieur même de la classe 

Mais PHP nous propose également de pouvoir utiliser la valeur de la constante de classe depuis l'extérieur de la classe, en utilisant la syntaxe suivante : MaClasse::maConstante

```php
<?php
      class Person {
          
      }
      class Ninja extends Person {
        // Ajoutez votre code ici :
        const stealth = "MAXIMUM";
      }
      // ...et ici !
      echo Ninja ::stealth;
      
      ?>

``` 

Pour utiliser les propriétés ou les **méthodes static** d'une classe, il faut utiliser (encore une fois) l'opérateur de résolution de portée **::**

```php
 <?php
        class King {
          // Modifiez le code en ligne 10...
          public static function proclaim() {
            echo "A kingly proclamation!";
          }
        }
        // ...et appelez la méthode :
        echo king :: proclaim();
      ?>                                
```                                        


# Mots clés:

* **class** : Déclaration de classe ;
* **const** : Déclaration de constante de classe ;
* **function** : Déclaration d'une méthode ;
* **public/protected/private** : Accès (par défaut "public" si aucun accès n'est explicitement défini) ;
* **new**: Création d'objet ;
* **self** : Résolution de portée (la classe elle-même) ;
* **parent** : Résolution de portée (la classe "parent") ;
* **static** : Résolution de portée (appel statique) disponible depuis PHP 5.3 et 6.0 ;
* **extends** : Héritage de classe ;
* **implements** : Implémentation d'une interface (dont il faut redéclarer toutes les méthodes).

# Méthodes magiques:

* **__construct()** : Constructeur de la classe ;
* **__destruct()** : Destructeur de la classe ;
* **__set()** : Déclenchée lors de l'accès en écriture à une propriété de l'objet ;
* **__get()** : Déclenchée lors de l'accès en lecture à une propriété de l'objet ;
* **__call()** : Déclenchée lors de l'appel d'une méthode inexistante de la classe (appel non statique) ;
* **__callstatic()** : Déclenchée lors de l'appel d'une méthode inexistante de la classe (appel statique) : disponible depuis PHP 5.3 et 6.0 ;
* **__isset()** : Déclenchée si on applique isset() à une propriété de l'objet ;
* **__unset()** : Déclenchée si on applique unset() à une propriété de l'objet ;
* **__sleep()** : Exécutée si la fonction serialize() est appliquée à l'objet ;
* **__wakeup()** : Exécutée si la fonction unserialize() est appliquée à l'objet ;
* **__toString()** : Appelée lorsque l'on essaie d'afficher directement l'objet : echo $object; ;
* **__set_state()** : Méthode statique lancée lorsque l'on applique la fonction var_export() à l'objet ;
* **__clone()** : Appelés lorsque l'on essaie de cloner l'objet ;
* **__autoload()** : Cette fonction n'est pas une méthode, elle est déclarée dans le scope global et permet d'automatiser les "include/require" de classes PHP.
Enfin, la variable $this utilisée à l'intérieur d'une classe, vaut toujours une référence vers l'objet lui-même


   
|contrôleur  |URL                       | HTTP   |Template(vue)HTML                     |Action            |
|------------|--------------------------| ------ |--------------------------------------|----------------- |
| index      | /recipes                 |  GET   | lister-recipe.html                   |Afficher la liste |
| create     | /recipes/create          |  GET   | ajouter-recipe.html                  |Aff.le formulaire |
| store      | /recipes                 |  POST  | confirmation-sauvegarde-recipe.html  |sauvegarder en bdd|
| show       | /recipes/{recipeID}      |  GET   | afficher-recipe.html                 |Aff.une recette   |
| edit       | /recipes/{recipeID}/edit |  GET   | modifier-recipe.html                 |Aff.formulaire Maj|
| update     | /recipes/{recipeID}      |  PUT   | confirmation-modification-recipe.html|Maj une recette   |
| destroy    |  /recipes/{recipeID}     | DELETE | confirmation-suppression-recipe.html |supprimer 1recette|

# Conclusion

Une classe est un plan dont nous créons des instances d'objets. Une classe contient principalement des propriétés et des méthodes.
Les variables et les fonctions sont appelées respectivement propriétés et méthodes dans le monde OOP.
Pour créer une instance d'une classe, un nouveau mot-clé est utilisé new MyClass(); 

**$ this**
Fait référence à l'objet courant, utilisé uniquement dans la classe.

**Opérateur d'objet ->**
Utilisé lors de l'appel d'une méthode ou de l'accès à une propriété sur une instance d'objet. 
Il est aussi utilisé avec $this.

## Visibilité
Les mots clés de visibilité ( public, protected, private ) déterminent la façon dont les propriétés / méthodes d'un objet sont accessibles:

* **public** : peut être consulté n'importe où.
* **protected** : peut être consulté par la classe et les sous-classes uniquement.
* **private** : peut être consulté par la classe seulement.
Une propriété doit être définie avec l'un des mots clés de visibilité ci-dessus.

(Une méthode définie sans aucun d'eux aura une visibilité publique par défaut.)


