
# 🛡️ Interface d'administration – Gestion des produits et utilisateurs

## 🎯 Objectif
Développement de la partie "administration" de l’application, permettant à un administrateur de :
- Gérer les produits (ajouter, modifier, supprimer)
- Gérer les comptes utilisateurs
- Accéder à une interface sécurisée réservée aux admins

---

## 📌 Technologies utilisées
- FastAPI (backend)
- JWT pour sécuriser l'accès
- React (interface admin dans `AdminPanel.jsx`)
- SQLite ou PostgreSQL
- Axios pour appels API côté frontend

---

## 👤 Accès réservé aux administrateurs

- Lors de l’authentification, un **token JWT** est généré avec le rôle de l'utilisateur (`admin` ou `client`)
- Toutes les routes d'administration sont protégées et ne sont accessibles que si :
  - Le token est valide
  - Le rôle est `admin`

---

## 🛠️ Tâches à réaliser dans cette branche `feature/admin`

| Tâche                              | Description                                                                 |
|------------------------------------|-----------------------------------------------------------------------------|
| Vérification du rôle dans JWT      | Décoder le token JWT et vérifier `role: admin` avant d'autoriser l'accès    |
| Interface `AdminPanel.jsx`         | Affichage conditionnel pour l’admin dans l'interface React                  |
| Gestion des produits (API)         | Ajouter / Modifier / Supprimer produits depuis `/produits`                 |
| Gestion des utilisateurs (API)     | Liste des utilisateurs, suppression (endpoint `/utilisateurs`)              |
| Composant de liste (frontend)      | Afficher les utilisateurs sous forme de tableau dans l’interface admin     |

---

## 🔐 Sécurité attendue

- Toute route API d’administration doit être protégée par `Depends(get_current_admin)`
- Le frontend ne doit afficher le panneau admin que si `role === 'admin'`
- Les erreurs doivent être claires : 401 Unauthorized ou 403 Forbidden

---

## 📂 Exemple d’arborescence pour admin

```
frontend/
├── pages/
│   ├── AdminPanel.jsx           # Interface conditionnelle pour admin
│   └── UsersList.jsx            # Liste des utilisateurs
backend/
├── routes/
│   └── admin.py (ou utilisateurs.py)
```

---

## ✅ Bonnes pratiques

- Ne jamais exposer de données sensibles dans les réponses
- Limiter les droits aux utilisateurs classiques
- Garder une séparation claire entre logique admin et logique utilisateur

---

Rédigé pour la branche : `feature/admin`

