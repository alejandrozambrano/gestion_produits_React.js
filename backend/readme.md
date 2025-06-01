
# 🛒 Module Panier - Plateforme de Gestion de Produits

Ce module gère toutes les fonctionnalités liées au panier d'achat dans notre application web.

## 👥 Collaborateur assigné
- **Nom** : Alejandro Zambrano
- **Branche** : `feature/panier`

---

## 📌 Objectifs du module
- Ajouter des produits au panier
- Modifier la quantité des produits dans le panier
- Supprimer un produit du panier
- Visualiser le contenu du panier
- Valider le panier (création de commande)

---

## 🔁 API REST - Endpoints prévus

| Méthode | Endpoint                      | Description                             |
|---------|-------------------------------|-----------------------------------------|
| `POST`  | `/api/panier/ajouter`         | Ajouter un produit au panier            |
| `PUT`   | `/api/panier/modifier/{id}`   | Modifier la quantité d’un produit       |
| `DELETE`| `/api/panier/supprimer/{id}`  | Supprimer un produit du panier          |
| `GET`   | `/api/panier`                 | Afficher le contenu du panier           |
| `POST`  | `/api/panier/valider`         | Valider le panier et créer la commande  |

---

## 🗃️ Structure prévue

```
panier/
│
├── controllers/
│   └── panierController.py
├── models/
│   └── panierModel.py
├── routes/
│   └── panierRoutes.py
└── README.md
```

---

## ✅ Critères de validation

- Gestion correcte des produits dans le panier
- Réponses JSON bien formatées
- Protection avec JWT (Token dans les headers)
- Tests unitaires validés

---

## 🔐 Authentification requise
Tous les endpoints doivent être protégés via un token JWT :
```
Authorization: Bearer <votre_token>
```