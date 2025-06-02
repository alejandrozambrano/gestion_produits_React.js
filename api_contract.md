
# 📑 Contrat d'API – Projet Gestion de Produits

Ce document définit les contrats d’échange entre le frontend et le backend (FastAPI).
Tous les développeurs doivent respecter ces structures pour assurer la compatibilité.

---

## 🔐 Authentification

### `POST /login`
**Demande :**
```json
{
  "email": "user@example.com",
  "mot_de_passe": "123456"
}
```

**Réponse :**
```json
{
  "access_token": "JWT_TOKEN",
  "token_type": "bearer",
  "utilisateur": {
    "id": 1,
    "nom": "Admin",
    "role": "admin"
  }
}
```

---

## 📦 Produits

### `GET /produits`
**Réponse :**
```json
[
  {
    "id": 1,
    "nom": "Clavier Logitech",
    "description": "Clavier sans fil",
    "prix": 29.99,
    "stock": 10
  },
  {
    "id": 2,
    "nom": "Souris HP",
    "description": "Souris optique",
    "prix": 19.99,
    "stock": 5
  }
]
```

---

## 🛒 Panier

### `POST /panier/ajouter`
**Demande :**
```json
{
  "id_utilisateur": 1,
  "id_produit": 2,
  "quantite": 1
}
```

**Réponse :**
```json
{
  "message": "Produit ajouté au panier."
}
```

---

### `GET /panier`
**Réponse :**
```json
[
  {
    "produit_id": 2,
    "nom": "Souris HP",
    "quantite": 1,
    "prix_total": 19.99
  }
]
```

---

## 🧾 Commandes

### `POST /panier/valider`
**Réponse :**
```json
{
  "message": "Commande validée avec succès",
  "commande_id": 15
}
```

---

## 👤 Utilisateurs (admin uniquement)

### `GET /utilisateurs`
**Réponse :**
```json
[
  {
    "id": 1,
    "nom": "Alejandro",
    "email": "admin@site.com",
    "role": "admin"
  },
  {
    "id": 2,
    "nom": "ClientX",
    "email": "client@site.com",
    "role": "client"
  }
]
```

---

📌 Ce contrat doit être respecté dans toutes les branches du projet (frontend, backend, panier, admin).
