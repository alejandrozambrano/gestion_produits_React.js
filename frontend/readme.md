
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

Rédigé pour la branche : `feature/backend`