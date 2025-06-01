
# 🛍️ Projet – Gestion de Produits en Ligne (React + FastAPI)

## 📌 Présentation
Ce projet consiste à développer une application web de gestion de produits avec :
- Un système d'authentification (login/logout)
- Un panier d'achat
- Une interface d'administration pour gérer les produits et les utilisateurs

---

## 👥 Répartition des tâches par collaborateur

| Collaborateur       | Tâche                          | Description                                                                                  | Branche de travail       |
|---------------------|--------------------------------|----------------------------------------------------------------------------------------------|---------------------------|
| Alejandro Zambrano  | Frontend (React)               | Création des composants React, connexion API, affichage des produits                         | `feature/frontend`        |
| Alejandro Zambrano  | Gestion du panier              | Interface utilisateur pour le panier, ajout/suppression de produits                          | `feature/panier`          |
| Alejandro Zambrano  | UML & Documentation            | Diagrammes de classe, séquence, cas d'utilisation, structure du projet                       | `main` (documentation)    |
| Collaborateur       | Backend (FastAPI)              | API REST, endpoints `/produits`, `/panier`, `/login`, connexion à la base de données         | `feature/backend`         |
| Collaborateur       | Authentification & JWT         | Login/logout, génération et vérification des tokens JWT                                      | `feature/backend`         |
| Collaborateur       | Interface d'administration     | Ajout, modification, suppression des produits et gestion des utilisateurs                    | `feature/admin`           |

---

## 🌿 Branches Git

| Branche              | Description                          |
|----------------------|---------------------------------------|
| `main`               | Version stable du projet              |
| `feature/frontend`   | Interface React (Alejandro)           |
| `feature/backend`    | API FastAPI (Collaborateur)           |
| `feature/panier`     | Gestion du panier (Alejandro)         |
| `feature/admin`      | Interface admin (Collaborateur)       |

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

### 🛠️ Travailler et pousser :
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

