# GIT & GITHUB

**Git** est un logiciel de contrôle de version, ce qui signifie qu’il gère les modifications d’un projet sans écraser n’importe quelle partie du projet.

**GitHub** fournit une interface visuelle pour vous aider à gérer localement vos projets avec les contrôles de version. Deuxièmement, créer un compte sur GitHub.com apporte les contrôles de versions à vos projets web, et leur confère des fonctionnalités de réseaux sociaux.

**Ligne de Commande** : 
Le programme de l’ordinateur que nous utilisons pour entrer des commandes Git.(Git Bash)

**Dépôt** : 
Un répertoire ou de l’espace de stockage où vos projets peuvent vivre. Parfois les utilisateurs GitHub raccourcissent ça en « repo ». Il peut être local sur un répertoire de votre ordinateur, ou ce peut être un espace de stockage sur GitHub ou un autre hébergeur en ligne. À l’intérieur d’un dépôt, Vous pouvez conserver des fichiers de code, des fichiers texte, des images.

**Contrôle de Version**:
Git conserve des « instantanés » de chaque point dans l’historique d’un projet, de sorte que vous ne pouvez jamais le perdre ou l’écraser.

**Commit** : C’est la commande qui donne à Git toute sa puissance. Quand vous « committez », vous prenez un « instantané », une « photo » de votre dépôt à ce stade, vous donnant un point de contrôle que vous pouvez ensuite réévaluer ou restaurer votre projet à un état précédent.

**Branche** : Habituellement, elles se « débranchent » du projet principal avec leurs propres versions complètes des modifications qu’elles ont chacune produites de leur côté. Après avoir terminé, il est temps de « fusionner » cette branche pour la ramener vers la branche « master », le répertoire principal du projet.


## Liste des commandes git

**init** : 
Crée un dossier git vide, ou (ré)initialise un dossier déjà existant

**status** :
Récupère l'état actuel du dossier git
Voir quels fichiers sont à l’intérieur, quelles sont les modifications à commiter, et sur quelle branche du repository on est en train de travailler.

**add**: 
cela porte de nouveaux fichiers à l’attention de Git. Après avoir ajouté des fichiers, ils sont inclus dans les « instantanés » du dépôt Git.

**commit**: 
la commande la plus importante de Git. Après avoir effectué toute sorte de modification, on entre ça afin de prendre un “instantané” du dépôt. Généralement cela s’écrit sous la forme git commit -m “Message ici“. Le -m indique que la section suivante de la commande devrait être lue comme un message.

**log**:
Affiche  tous les changements enregistrés (les commit)
Historique du projet.

**remote add origin**:
Ajoute au dossier git un "repository" distant, et le lie a udossier 'origin'

**push** :
envoie sur le repo distant les modifications enregistrées dans le dernier commit.

**push -u origin master**:
-u permet de se rappeler, das ce contexte d'utilisation, quels sont les paramètres de la fonction push :
	origin : l'élément à push (notre repo local)
	master : le nom de la 'branch' dans laquelle nous allons push notre élément

**pull** :
récupère les changements du repo distant sur notre repo local

**pull origin master**:
'pull' dans origin ce qui vient de master

**diff**:
Montre les différences entre l'état actuel de notre repo local et un état 'committé'

**diff HEAD**:
Précise que l'état auquel on veut comparer est le dernier commit

**reset**:
inverse de add sur un élément. Si c'est un élément qui a été 'add' au présent commit, il ne le sera plus.

**checkout** :
remet l'élément à l'état du précédent commit

**checkout <BranchName>**:
change de "branch" de travail, on travaille désormais sur la branch <BranchName>

**branch <NewBranchName>**:
crée une "branch" sur notre "arbre". On crée ainsi un nouveau contexte, indépendant de la branch "master", dans lequel nous allons travailler. on poura les merge éventuellement plus tard

**branch**:
Liste l'ensemble des branch actuellement disponibles.

**rm**:
remove -> supprime de notre repo local le(s) élément(s).

**merge <BranchToMerge>**:
fusionne la branch dans laquelle on travaille avec la branch <BranchToMerge>

**branch -d <BranchToDelete>**:
supprime la branch <BranchToDelete>

![schema](https://cdn.dribbble.com/users/138252/screenshots/2389144/github_dri.png)