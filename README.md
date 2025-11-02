# Kanap #

## Contexte: ##
Construire un site e-commerce en JavaScript pour Kanap, une marque de canapés qui vend ses produits depuis sa boutique exclusivement.

Aujourd’hui, celle-ci souhaiterait avoir une plateforme de e-commerce en plus de sa boutique physique pour vendre ses produits sur Internet.

## Fonctionnalités: ##
Implémentation du site de Kanap de manière dynamique:

- intégrer dynamiquement les éléments de l’API dans les différentes pages web avec JavaScript.

- Mettre en place un plan de test d’acceptation.

- 4 pages ont été mises en place : page d’accueil, page Produit, page Panier
  et la page Confirmation.

- Sur l’ensemble des pages, toutes les parties statiques sont en place, elles sont donc prêtes
  à recevoir le contenu dynamique.

- Intégrer ces éléments dynamiquement grâce à JS et l’API.

- Utiliser les “id” dans différentes balises, pour intégrer les éléments dynamiques.

## MVP – Spécifications fonctionnelles et techniques du site de Kanap: ##

### Architecture générale: ###
L’application web sera composée de 4 pages :

- Une page d’"accueil" montrant (de manière dynamique) tous les articles disponibles
  à la vente.

- Une page “produit” qui affiche (de manière dynamique) les détails du produit
  sur lequel l'utilisateur a cliqué depuis la page d’accueil.

- Depuis cette page, l’utilisateur peut sélectionner une quantité, une couleur,
  et ajouter le produit à son panier.

- Une page “panier”.

  Celle-ci contient plusieurs parties :

  - Un résumé des produits dans le panier, le prix total et la possibilité
    de modifier la quantité d’un produit sélectionné ou bien de supprimer celui-ci.

  - Un formulaire permettant de passer une commande.
  
  - Les données du formulaire doivent être correctes et bien formatées avant d'être renvoyées
    au back-end => par exemple, pas de chiffre dans un champ prénom.

- Une page “confirmation” :

  - Un message de confirmation de commande, remerciant l'utilisateur pour sa commande,
    et indiquant l'identifiant de commande envoyé par l’API.

### Planification de tests: ###
Tests d’acceptation pour l’ensemble des fonctionnalités listées
dans ce document (spécifications fonctionnelles et techniques Kanap).

Plan de test visible dans le dossier P5_TINARD_PIERRE

### Informations complémentaires: ###

#### La page d’Accueil: ####
- Cette page présente l’ensemble des produits retournés par l’API.

- Pour chaque produit, il faudra afficher l’image de celui-ci, ainsi que son nom
  et le début de sa description.

- En cliquant sur le produit, l’utilisateur sera redirigé sur la page du produit
  pour consulter celui-ci plus en détail.

#### La page Produit: ####
- Cette page présente un seul produit ; elle aura un menu déroulant permettant à l'utilisateur
  de choisir une option de personnalisation, ainsi qu’un input pour saisir la quantité.

- Ces éléments doivent être pris en compte dans le panier.

#### La page Panier: ####
- Sur cette page, l’utilisateur va pouvoir modifier la quantité d’un produit de son panier;
  à ce moment, le total du panier devra bien se mettre à jour.

- L’utilisateur aura aussi la possibilité de supprimer un produit de son panier,
  le produit devra donc disparaître de la page.

- Les inputs des utilisateurs doivent être analysés et validés pour vérifier le format 
  et le type de données avant l’envoi à l’API.

- Il ne serait par exemple pas recevable d’accepter un prénom contenant des chiffres,
  ou une adresse e-mail ne contenant pas de symbole “@”.

- En cas de problème de saisie, un message d’erreur devra être affiché en dessous
  du champ correspondant.

- Attention à ne pas stocker le prix des articles en local !

- Les données stockées en local ne sont pas sécurisées et l’utilisateur pourrait
  alors modifier le prix lui-même.

#### La page Confirmation: ####
- Sur cette page, l'utilisateur doit voir s’afficher son numéro de commande.

- Il faudra veiller à ce que ce numéro ne soit stocké nulle part.

#### Le code source: ####
- Celui-ci devra être indenté et utiliser des commentaires en début de chaque fonction
  pour décrire son rôle.

- Il devra également être découpé en plusieurs fonctions réutilisables (nommées).

- Une fonction doit être courte et répondre à un besoin précis.

#### API: ####
- Concernant l’API, des promesses devront être utilisées pour éviter les callbacks.

- Il est possible d’utiliser des solutions alternatives, comme fetch,
  celle-ci englobant la promesse.

- L’API n’est actuellement que dans sa première version.

- La requête post qu’il faudra formuler pour passer une commande
  ne prend pas encore en considération la quantité ni la couleur des produits achetés.

#### Paramètres des API: ####
Chaque API contient 3 paramètres :

- GET / => Retourne un tableau de tous les éléments

- GET /{product-ID}: {product-ID} doit être remplacé par l’id d’un produit

  => Renvoie l'élément correspondant à {product-ID}, identifiant d’un produit

- POST /order => Requête JSON contenant un objet de contact et un tableau de produits

  => Retourne l'objet contact, le tableau produits et orderId (string)

#### Validation des données: ####
- Pour les routes POST, l’objet contact envoyé au serveur doit contenir les champs firstName,
lastName, address, city et email.

- Le tableau des produits envoyé au back-end doit être un array de strings product-ID.

- Les types de ces champs et leur présence doivent être validés avant l’envoi des données
  au serveur.

#### Fonctionnement du panier: ####
- Dans le panier, les produits doivent toujours apparaître de manière regroupée par modèle
  et par couleur.

- Si un produit est ajouté dans le panier à plusieurs reprises, avec la même couleur,
  celui-ci ne doit apparaître qu’une seule fois, mais avec le nombre d’exemplaires ajusté.

- Si un produit est ajouté dans le panier à plusieurs reprises, mais avec des couleurs
  différentes, il doit apparaître en deux lignes distinctes avec la couleur et
  la quantité correspondantes indiquées à chaque fois.


## Contraintes techniques: ##
Pour ce projet, n'utiliser que du code JavaScript pur.

L'utilisation de tout framework ou librairie JavaScript (React, Angular, Vue ou jQuery,
par exemple) est interdite pour ce projet.

## Intallation du projet en local et lancement de la page Kanap: ##
Sur le repository P5_Tinard_Pierre, cliquez sur < > code => (copy url to clipboard):

https://github.com/Shoshin-Dev-Ivy/P5_Tinard_Pierre.git

Dans un éditeur de code, (exemple: VS CODE), ouvrez un terminal:

cd Documents: git clone https://github.com/Shoshin-Dev-Ivy/P5_Tinard_Pierre.git

Ensuite open folder => P5_Tinard_Pierre

Ciblez index.html.

Click droit sur la page index.html => open with Live Server.

Index.html ouvert sur le port 5500 => http://127.0.0.1:5500/front/html/index.html

### Lancement du Back-end, appel à l'API: ###
~/Documents/Github/shoshin-dev-ivy/P5_Tinard_Pierre/back

~/Documents/Github/shoshin-dev-ivy/P5_Tinard_Pierre/back $ npm install

~/Documents/Github/shoshin-dev-ivy/P5_Tinard_Pierre/back $ node server

Listening on port 3000

L'affichage dynamique des éléments est disponible sur la page Kanap.

