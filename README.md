E-commerce Project - ZenithCore
Ce projet est une application de commerce électronique développée avec Django. Il permet de gérer un catalogue de produits complet, incluant l'organisation par catégories, la gestion des stocks, et un système d'authentification sécurisé pour les utilisateurs.  

 Fonctionnalités
Gestion du Catalogue : Affichage dynamique des produits et des catégories.

Espace Client : Système complet d'inscription, de connexion et de déconnexion.

Profil Utilisateur : Page de profil sécurisée affichant les informations du compte.

Interface d'Administration : Gestion simplifiée des produits, catégories et utilisateurs via l'admin Django.

Architecture et Mécanismes (MVT)
Le projet suit le pattern Model-View-Template :

Le Modèle (models.py) : Structure de la base de données.

Category : Pour l'organisation des articles.

Product : Détails techniques, prix, stock et images.

Les Vues (views.py) : Logique métier et traitement des requêtes.

Les Templates (templates/) : Affichage dynamique des données.

Le Routage (urls.py) : Liaison entre les URLs et les fonctions de traitement.

Aperçu du Projet
Voici les différentes étapes et interfaces du projet :

1. Architecture du Projet
L'application s'appuie sur une application principale products et une application accounts pour la gestion des utilisateurs.
[Image de l'arborescence du projet Django montrant les dossiers accounts et products]

2. Interface Boutique
Liste des produits : Présentation claire des articles disponibles (ex: composants PC, chaises gaming).

Détails du produit : Fiche complète avec description détaillée, prix en MAD et état du stock.

3. Système d'Authentification
Inscription : Formulaire de création de compte avec validation de sécurité.

Connexion : Accès sécurisé à l'espace client.

Profil : Espace personnel affichant le statut de l'utilisateur (Staff, Superuser).

4. Administration
Interface dédiée pour la gestion du contenu du site.
[Image de l'interface d'administration Django montrant les sections Groups, Users, Category et Products]



Installation et Configuration
Prérequis
Python 3.x

Environnement virtuel activé (myenv)

Librairie Pillow pour les images : pip install pillow

Lancement
Appliquer les migrations : python manage.py migrate

Lancer le serveur : python manage.py runserver

Accéder à l'application : http://127.0.0.1:8000/
1) Architecture du projet 
<img width="945" height="501" alt="image" src="https://github.com/user-attachments/assets/9ebe51a9-ff98-4a5f-a57d-dfcd33d3e16f" />
2) capture de liste de produit
   <img width="945" height="496" alt="image" src="https://github.com/user-attachments/assets/ab8d2ff5-db94-4f3a-821f-b6ab9e09d883" />
3) capture de détails du produit
   <img width="945" height="496" alt="image" src="https://github.com/user-attachments/assets/e694b2a2-4ead-4542-a660-cf0ae05e403c" />
4) capture de la page d'inscription
   <img width="945" height="496" alt="image" src="https://github.com/user-attachments/assets/663b63d4-daca-4391-8560-9472455ad95c" />
5) capture de la page de connexion
   <img width="945" height="494" alt="image" src="https://github.com/user-attachments/assets/7a78ea74-20db-4566-8baa-012fe882fa1e" />
6) capture de la page de profile après connexion
   <img width="945" height="497" alt="image" src="https://github.com/user-attachments/assets/9ae40e18-fa32-43fc-b8b2-7e1fedfca71f" />
7) capture montrant la déconnexion
   <img width="945" height="495" alt="image" src="https://github.com/user-attachments/assets/d22f41cf-5c00-4e29-af42-cff90b8e9d37" />
8) capture de l'interface d'admin django
   <img width="945" height="491" alt="image" src="https://github.com/user-attachments/assets/2734cb08-f8cf-4fa9-ac69-2f627c604684" />
9)Le décorateur @login_required
Dans ce projet, la sécurité des pages sensibles (comme la page Mon Profil) est assurée par le décorateur @login_required.

Son rôle : Il vérifie si l'utilisateur est authentifié avant d'exécuter la fonction de la vue.

Fonctionnement : Si un utilisateur non connecté tente d'accéder à /accounts/profile/, il est automatiquement redirigé vers la page de connexion. Cela garantit que seules les personnes autorisées voient les informations privées.

10) Le tag {% csrf_token %}
Présent dans tous nos formulaires (inscription, connexion), ce tag est une mesure de sécurité cruciale de Django.

Son rôle : Il protège l'application contre les attaques de type CSRF (Cross-Site Request Forgery).

Fonctionnement : Django génère un jeton unique et secret que le navigateur doit renvoyer lors de l'envoi du formulaire. Cela prouve que la requête provient bien de notre site et non d'un site malveillant tentant de simuler une action au nom de l'utilisateur.

11)<img width="945" height="499" alt="image" src="https://github.com/user-attachments/assets/4161b623-1d8f-4f72-aec6-7637919420d8" />
