# TP2 - Movie Time App

## 🚀 Objectifs du Projet

Ce projet a pour but de développer une application permettant de gérer des shows (films, séries, animes) via une interface Flutter, en interagissant avec un backend en temps réel construit avec Node.js et une base de données SQLite. À l'issue de ce TP, vous disposerez d'une application complète qui inclut des fonctionnalités de connexion, d'affichage, d'ajout, de mise à jour et de suppression de shows.

---

## ⚙️ Architecture du Projet

Le projet est divisé en deux parties principales : le **backend** et le **frontend**.

### Backend - Node.js & SQLite

1. **Configuration du projet** : 
   Le backend utilise **Node.js** avec le framework **Express** pour créer une API REST. La base de données est gérée via **SQLite**, une base légère et facile à configurer.

2. **Création du serveur** :
   Un serveur Express est configuré pour gérer les requêtes HTTP (GET, POST, PUT, DELETE) et interagir avec la base de données SQLite pour récupérer, ajouter, modifier ou supprimer des shows.

3. **Routes et API** :
   Des routes sont définies pour gérer les interactions avec les données des shows. L’API permet de récupérer la liste des shows, d'ajouter de nouveaux shows, de modifier les informations existantes ou de supprimer des shows.

4. **Gestion des données** :
   Les shows sont stockés dans une table SQLite. Chaque show possède des attributs comme le titre, la description, la catégorie, et une image.

5. **Lancement du serveur** :
   Le serveur backend peut être démarré avec une simple commande et devient disponible pour accepter les requêtes de l'application frontend.

---

### Frontend - Flutter

L'application mobile est construite avec **Flutter**, permettant une interface utilisateur fluide et réactive. Elle communique avec l'API backend pour récupérer et envoyer des données.

1. **Page de Connexion** :
   Cette page permet à l'utilisateur de s'authentifier en fournissant un email et un mot de passe. Un token d'authentification est généré après une connexion réussie, et il est stocké pour effectuer des requêtes sécurisées pour les autres pages de l'application.

2. **Page d'Accueil** :
   La page d'accueil affiche la liste des shows récupérés depuis l'API backend. Un système de navigation avec un `Drawer` et un `BottomNavigationBar` permet à l'utilisateur de passer d'une section à l'autre (ex. : profil, ajout de show, etc.).

3. **Page de Profil** :
   La page de profil permet à l'utilisateur de voir ses informations personnelles, notamment son nom et son email. L'utilisateur peut également accéder à la page "Modifier le Profil" pour mettre à jour ses informations.

4. **Ajouter un Show** :
   Une page permet à l'utilisateur d'ajouter un nouveau show à la base de données. L'utilisateur peut saisir un titre, une description, une catégorie et une image pour le show, et ces informations sont envoyées au backend via une requête POST.

---
## 🗂 Structure du Projet

Voici la structure des dossiers et fichiers :


```
├── movie_time
│   ├── README.md
│   ├── analysis_options.yaml
│   ├── android
│   ├── build
│   ├── ios
│   ├── lib
│   │   ├── config
│   │   │   └── api_config.dart
│   │   ├── main.dart
│   │   ├── screens
│   │   │   ├── add_show_page.dart
│   │   │   ├── home_page.dart
│   │   │   ├── login_page.dart
│   │   │   ├── profile_page.dart
│   │   │   └── update_show_page.dart
│   │   └── services
│   │       └── auth_service.dart
│   ├── linux
│   ├── macos
│   ├── pubspec.lock
│   ├── pubspec.yaml
│   ├── test
│   ├── web
│   └── windows
└── show-app-backend
    ├── database.js
    ├── package-lock.json
    ├── package.json
    ├── routes
    │   ├── auth.js
    │   └── shows.js
    ├── server.js
    ├── shows.db
    └── uploads
        └── (files)

```

---


## 📋 Tâches à Compléter

Le projet comporte plusieurs tâches à réaliser, dont voici la liste détaillée :

### 1️⃣ **Créer une Page de Mise à Jour (Update Show Page)**

L'objectif est de créer une page permettant de modifier les informations d'un show existant. Cette page doit pré-remplir les champs avec les données actuelles du show (titre, description, catégorie, image). Une fois les modifications apportées, elles doivent être envoyées au backend via une requête PUT pour mettre à jour la base de données.

### 2️⃣ **Rendre la Page d'Accueil Dynamique (Auto-Refresh)**

Une fois un show ajouté ou mis à jour, la page d'accueil doit se rafraîchir automatiquement pour afficher les nouvelles données sans avoir à recharger manuellement l'application. L’objectif est de mettre à jour uniquement la section concernée de la page (par exemple, la liste des shows) pour améliorer l'expérience utilisateur.

### 3️⃣ **Créer une Page de Connexion Fonctionnelle**

La page de connexion doit permettre à l'utilisateur de s'authentifier en utilisant l'API backend. Les utilisateurs doivent entrer leur email et mot de passe. En cas d’échec de la connexion (identifiants incorrects), un message d'erreur doit être affiché. Après une connexion réussie, un token d’authentification sera stocké, permettant à l'utilisateur d'accéder aux fonctionnalités de l'application de manière sécurisée.

---

### 🎥 Vidéos Démonstratives

- **Page d'Accueil**  
  [Cliquez ici pour voir la vidéo](https://github.com/chmichaaa/tp-2-project-movie-time/blob/master/Videos/HomePage.mov)

- **Ajouter un Show**  
  [Cliquez ici pour voir la vidéo]([https://github.com/chmichaaa/tp-2-project-movie-time/blob/master/Videos/Adding-A-Show.mov](https://drive.google.com/file/d/1cRZj27FeuIdgHyqImeUlFRm7LvxzRZoK/view?usp=drive_link))

- **Mise à jour d'un Show**  
  [Cliquez ici pour voir la vidéo](https://github.com/chmichaaa/tp-2-project-movie-time/blob/master/Videos/Editing-Show.mov)

- **Page de Connexion**  
  [Cliquez ici pour voir la vidéo](https://github.com/chmichaaa/tp-2-project-movie-time/blob/master/Videos/Logging-In.mov)


---

## 📌 Conclusion

Ce projet permet de démontrer la capacité à créer une application mobile complète, interagissant avec un backend pour gérer des données en temps réel. L’application offre des fonctionnalités essentielles telles que la gestion des utilisateurs, l’affichage et la gestion des shows (ajout, mise à jour, suppression) et garantit une expérience utilisateur fluide grâce à l’auto-refresh des données.

---

