# Description Fonctionnelle Machine Laravel
--------------------------------------------------------------------------------------------------------
## Boisson:

|Nom table SQL   |Nom Modele   |View   |Nom controleur  |Methodes|Url  |Http  |Action|
|-------------|----------|-------------|--------------|------------------|---|----|--------|
|boissons|Boisson|boissons.blade|**Boissons**Controller|**store**|localhost/1|**Post**|Nouvelle création Boisson
|boissons|Boisson|boissons.blade|**Boissons**Controller|**Destroy**|localhost/boisson/{id}|**Delete**|Supprimer Boisson 
|boissons|Boisson|boissons.blade|**Boissons**Controller|**Edit**|localhost/boisson/{id}|**Put**|Modifier Boisson
|boissons|Boisson|boissons.blade|**Boissons**Controller|**index**|localhost/1|**Get**|tri alphabetique boissons
|boissons|Boisson|boissons.blade|**Boissons**Controller|**nomdown**|localhost/za|**Get**|tri alphabetique décroissant
|boissons|Boisson|boissons.blade|**Boissons**Controller|**prixup**|localhost/prixup|**Get**|tri prix croissant
|boissons|Boisson|boissons.blade|**Boissons**Controller|**prixdown**|localhost/prixdown|**Get**|tri prix decroissant
|boissons|Boisson|detailsBoissons.blade|**detailsBoissons**Controller|**index**|/details/boisson/{id}|**Get**|permet de lister les boissons en fonction de leur id.
-----------------------------------------------------------------------------------------------------------------------
## Ingredient:

|Nom table SQL   |Nom Modele   |View   |Nom controleur  |Methodes|Url  |Http  |Action|
|-------------|----------|-------------|--------------|------------------|---|----|--------|
|ingredients|Ingredient|ingredients.blade|**Ingredients**Controller|**index**|localhost/2|**Get**|affiche la liste des ingredients
|ingredients|Ingredient|ingredients.blade|**Ingredients**Controller|**Store**|localhost/2|**Post**|Nouvelle création ingredient
|ingredients|Ingredient|ingredients.blade|**Ingredients**Controller|**destroy**|localhost/ingredients/{id}|**Delete**|Permet de supprimer un ingredient
|ingredients|Ingredient|ingredients.blade|**Ingredients**Controller|**edit**|/modif/ingredient/{id}|**Put**|permet de modifier un ingredient
|ingredients|Ingredient|detailsIngredients.blade|**detailsIngredients**Controller|**index**|details/ingredients/{id}|**Get**|liste les ingredients sur la vue details.
-----------------------------------------------------------------------------------------------------------------------
## Recette:

|Nom table SQL   |Nom Modele   |View   |Nom controleur  |Methodes|Url  |Http  |Action|
|-------------|----------|-------------|--------------|------------------|---|----|--------|
|recettes|Recette|recette.blade|**Recettes**Controller|**index**|localhost/4|**Get**|liste des boissons
|recettes|Recette|recette.blade|**Recettes**Controller|**show**|/liste/boissons/{id}|**Get**|affiche la recette de la boisson via son id sur details recette
|recettes|Recette|detailsRecette.blade|**Recettes**Controller|**store**|/liste/boissons/{id}|**Post**|affiche sur la page recette les infos du formulaire (ajout recette)
|recettes|Recette|detailsRecette.blade|**Recettes**Controller|**destroy**|/liste/boissons/{id}|**delete**|supprime la recette entiere
|recettes|Recette|detailsRecette.blade|**Recettes**Controller|**destroyIngredient**|/liste/boissons/{id}|**delete**|supprime la recette ligne par ligne
-----------------------------------------------------------------------------------------------------------------------
## Vente:

|Nom table SQL   |Nom Modele   |View  |Nom controleur  |Methodes|Url  |Http |Action|
|-------------|----------|-------------|--------------|------------------|---|----|--------|
|ventes|Vente|vente.blade|**Ventes**Controller|**show**|localhost/5|**Get**|Affiche les ventes avec les infos saisies dans le formulaire commande.
|ventes|Vente|vente.blade|**Ventes**Controller|**destroyVente**|5/ventes/{id}|**delete**|Supprime les ventes en fonction de l'id.
|ventes|Vente & Boisson|bienvenue.blade|**welcome**Controller|**indexVente**|localhost/bienvenue|**Get**|Récupere les données pour les champs du formulaire.
|ventes|Vente|vente.blade|**welcome**Controller|**store**|localhost/bienvenue|**Post**|Nouvelle vente qui renvoie les infos sur la page liste vente.