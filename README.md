
###  Aspects fonctionnelles (15 points)


#####  TLDR; Une application de gestion d'allocation et de restitution de matériel.


Il doit y exister 2 types d'utilisateurs : Administrateur et Employée
- Un administrateur a tous les privilèges sur les matériels : Ajout, Suppression, Modification, Listing ...
- Un Employée peut seulement allouer un matériel pour une durée donnée, et le rendre par la suite.

L'application contiendra donc une table User qui comprend les informations : username, password, role ...
(Pour but de simplification, insérer les utilisateurs par script **sql** lors du lancement de l'application, )


Chaque type de matériel se voit avoir une quantité de stock : 5 tables toutes allouées veut dire que la prochaine allocation ne sera pas possible.

#### Scénario nominal 1:
Un utilisateur ayant le rôle employée se connecte à l'application en fournissant le couple (username, password).
Si la connexion est réussie, alors on lui affiche le menu :

1. Chercher un matériel;
1. Allouer un matériel;
1. Rendre un matériel;
1. Afficher la liste des matériels alloués par lui même
1. Afficher la liste de tous les matériels

et d'après son choix on effectue les traitements nécessaires;
####  Scénario nominal 2 :
Un utilisateur ayant le rôle administrateur se connecte à l'application en fournissant le couple (username, password).
Si la connexion est réussie, alors on lui affiche le menu :
1. Chercher un matériel;
1. Créer un nouveau matériel;
1. Supprimer un matériel;
1. Modifier les informations d'un matériel
1. Marquer un matériel indisponible
1. Allouer un matériel;
1. Rendre un matériel;
1. Afficher la liste des matériels alloués par lui même
1. Afficher la liste des matériels alloués par chaque utilisateur
1. Afficher la liste de tous les matériels
et d'après son choix on effectue les traitements nécessaires;

####  Scénario non-nominal 1 :
Un utilisateur fournit un couple (username, password) qui est erroné
1. Lui afficher un message d'erreur convenable;
1. Lui proposer de ressaisir ses informations ou bien quitter l'application.

####  Scénario non-nominal 2 :
Un utilisateur veut allouer un matériel non disponible ou épuisé
1. Lui afficher un message d'erreur convenable;
1. Lui réafficher le menu initial correspondant;


### Aspects techniques (15 points)

1. Foker le repo suivant, https://github.com/BelmoMusta/DEVEOIR-TP-GI4  pour soumission de travail, créer un PR sur github dont le titre sera votre nom complet;
1. Créer les tables nécessaires, et aussi les relations entre elles;
1. Respecter la décomposition des couches : dao, service, controller ....;
1. Prévoir les beans spring nécessaire, et les injecter aux bons endroits;
1. Utiliser JdbcTemplate avec les mappers nécessaires;
1. Externaliser, à la limite du possible, les messages en dur sur des fichiers properties et les charger au démarrage;
1. Prévoir un schéma d'héritage entre les entités;
1. Utiliser le pattern publisher-listener uniquement pour la création et la modification des entités;
1. Un point pour un code réfactoré x
1. un point pour un code clean ( nommage, structure, **SOLID**, ...etc)


### Bonus : 10 points
1. Hasher les mots de passes des utilisateurs en utilisant un algorithme asymétrique  (**bCrypt** par exemple)
1. Utilser **l'AOP** pour gérer l'authentification;
1. Utiliser une table de rôles : un utilisateur peut avoir plusieurs rôles à la fois;
1. créer des test unitaires avec **Junit**.
