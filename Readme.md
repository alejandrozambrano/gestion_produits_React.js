
# 🛍️ Projet – Gestion de Produits en Ligne (React + FastAPI)

## 📌 Présentation
Ce projet consiste à développer une application web de gestion de produits avec :
- Un système d'authentification (login/logout)
- Un panier d'achat
- Une interface d'administration pour gérer les produits et les utilisateurs

---

## 👥 Répartition des tâches par collaborateur

| Collaborateur       | Tâche                          | Description                                                                                  | Branche de travail        |
|---------------------|--------------------------------|----------------------------------------------------------------------------------------------|---------------------------|
| Alejandro Zambrano  | Frontend (React)               | Création des composants React, connexion API, affichage des produits                         | `feature/frontend`        |
| Alejandro Zambrano  | Gestion du panier              | Interface utilisateur pour le panier, ajout/suppression de produits                          | `feature/panier`          |
| Alejandro Zambrano  | UML & Documentation            | Diagrammes de classe, séquence, cas d'utilisation, structure du projet                       | `main` (documentation)    |
| Yaakoub El Mouttaqui| Backend (FastAPI)              | API REST, endpoints `/produits`, `/panier`, `/login`, connexion à la base de données         | `feature/backend`         |
| Yaakoub El Mouttaqui| Authentification & JWT         | Login/logout, génération et vérification des tokens JWT                                      | `feature/backend`         |
| Yaakoub El Mouttaqui| Interface d'administration     | Ajout, modification, suppression des produits et gestion des utilisateurs                    | `feature/admin`           |

---

## 🌿 Branches Git

| Branche              | Description                           |
|----------------------|---------------------------------------|
| `main`               | Version stable du projet              |
| `feature/frontend`   | Interface React (Alejandro)           |
| `feature/backend`    | API FastAPI (Yaakoub El Mouttaqui)    |
| `feature/panier`     | Gestion du panier (Alejandro)         |
| `feature/admin`      | Interface admin (Yaakoub El Mouttaqui)|

---

## 🚀 Procédure de travail Git recommandée

### 🔁 Avant de commencer :
```bash
git checkout main
git pull origin main
```

### 🌿 Créer une branche :
```bash
git checkout -b feature/nom-de-ta-tâche
```

###
# ⚙️ Backend – API REST (FastAPI + SQLite)

## 🎯 Objectif
Développement de l’API backend de l’application e-commerce pour gérer les produits, le panier, l’authentification et les comptes utilisateurs.

---

## 📌 Technologies utilisées
- Python 3.11+
- FastAPI
- SQLite (ou PostgreSQL selon les besoins)
- JWT (Json Web Token) pour l’authentification
- Pydantic (validation de schémas)
- Swagger UI pour la documentation automatique

---

## 🛠️ Tâches à réaliser dans cette branche `feature/backend`

| Module                  | Description                                                                 |
|-------------------------|-----------------------------------------------------------------------------|
| `main.py`               | Point d’entrée de l’application FastAPI                                     |
| `models.py`             | Modèles SQLAlchemy pour Produit, Utilisateur, Panier                        |
| `schemas.py`            | Schémas Pydantic pour validation de données                                 |
| `routes/produits.py`    | Endpoints CRUD : `/produits`                                                |
| `routes/panier.py`      | Endpoints : `/panier` (ajout, modif, suppression, validation commande)      |
| `routes/auth.py`        | Login, génération et vérification de token JWT                              |
| `routes/utilisateurs.py`| Création et gestion des comptes utilisateurs (admin / client)               |
| `database.py`           | Connexion à la base SQLite + création des tables                            |

---

## 🔐 Authentification (JWT)
- Lors du login, un token est généré et retourné au frontend.
- Le token est requis dans le header (`Authorization: Bearer <token>`) pour accéder aux routes protégées.
- Les rôles (`admin`, `client`) seront pris en compte pour restreindre l’accès à certaines routes.

---

## 🌿 Endpoints à implémenter

### Produits
```
GET    /produits
POST   /produits         # admin
PUT    /produits/{id}    # admin
DELETE /produits/{id}    # admin
```

### Panier
```
POST   /panier/ajouter
PUT    /panier/modifier/{id}
DELETE /panier/supprimer/{id}
POST   /panier/valider
```

### Authentification
```
POST   /login
POST   /register
```

### Utilisateurs (admin uniquement)
```
GET    /utilisateurs
DELETE /utilisateurs/{id}
```

---

## ✅ Bonnes pratiques
- Protéger les routes sensibles avec `Depends(get_current_user)`
- Utiliser les rôles pour différencier admin vs utilisateur
- Centraliser les messages d’erreur
- Tester les réponses HTTP : 200, 201, 400, 401, 404

---

## 📂 Arborescence recommandée

```
backend/
├── main.py
├── models.py
├── schemas.py
├── database.py
├── routes/
│   ├── produits.py
│   ├── panier.py
│   ├── auth.py
│   └── utilisateurs.py
├── .env
├── requirements.txt
└── README.md
```

---

Rédigé pour la branche : `feature/backend` 🛠️ Travailler et pousser :
```bash
git add .
git commit -m "Ajout de la fonctionnalité X"
git push origin feature/nom-de-ta-tâche
```

### ✅ Pull Request :
- Créer une Pull Request **vers `main`**
- Attendre la validation avant de faire le merge

---

## 📁 Structure du projet

```
gestion_produits_React.js/
├── frontend/          # React App
├── backend/           # API FastAPI
├── diagrammes/        # Diagrammes UML
├── README.md
└── .gitignore
```

---

## 🔒 Bonnes pratiques

- Ne jamais travailler directement sur `main`
- Une branche par fonctionnalité
- Des commits clairs
- Des PR revues avant intégration