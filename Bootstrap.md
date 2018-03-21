# Bootstrap

Framework: 

	Ensemble de composants structurés, sert à créer les bases et organiser le code informatique.
	Systeme de grille simple et efficace pour mettre en ordre l'aspect visuel d'une page web.


## Organisation de la grille

1.Mise en page basée sur une grille de 12 colonnes 

	Row -> Représente une rangée.

2.Il faut définir le nombre de colonnes pour chaque element (max 12)
 
	 ex: col-xs-1 ou col-sm-1 ou col-md-1
	 ou col-lg-1 
	 col-xs-2 ...

 3.Valeur de réference:

	XS :Smartphone (<768px) 
	Sm :Tablette (>=768px)
	md :Petit ecran(>=992px)
	LG :grand ecran (>=1200px) 

## Html:

	<div class="row">
		<div class="col-sm-4">largeur 4</div>
			<div class="col-sm-8">largeur 8</div>
	</div>																							   

![schema bootstrap](https://dospuntocero.cl/wp-content/uploads/2016/01/grilla-simple.jpg);

## Container

* Container: Contient et centre la grille qui s'adapte en fonction de l'ecran
* Container-fluid: Permet à la grille d'occuper toute la largeur.

![schema container-fluid](http://www.diliaranasirova.com/assets/DiliarasBlog/tutorials/Bootstrap/Bootstrap10.jpg);