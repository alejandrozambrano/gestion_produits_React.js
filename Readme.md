
# 🧺 Panier – Gestion du panier d’achat

## 🎯 Objectif
Développement de la fonctionnalité "panier d'achat" pour l’utilisateur. Permettre d'ajouter, modifier, supprimer et valider des produits dans le panier.

---

## 📌 Technologies utilisées
- React.js pour l’interface utilisateur
- Axios pour communiquer avec l’API backend
- FastAPI pour les endpoints liés au panier
- SQLite (ou PostgreSQL) pour stocker les lignes du panier
- JWT pour authentifier les actions

---

## 🛠️ Tâches à réaliser dans cette branche `feature/panier`

| Élément                 | Description                                                                 |
|-------------------------|-----------------------------------------------------------------------------|
| `Panier.jsx`            | Affichage du panier avec tous les produits ajoutés                         |
| `Ajouter au panier`     | Bouton depuis `ProductList.jsx` qui appelle l’API pour ajouter un article  |
| `Modifier quantité`     | Interface pour augmenter / diminuer la quantité dans `Panier.jsx`          |
| `Supprimer article`     | Option pour retirer un produit du panier                                   |
| `Valider commande`      | Bouton pour finaliser l’achat et créer une commande                        |
| `API /panier/...`       | Endpoints POST, PUT, DELETE, validation (FastAPI)                          |

---

## 🔁 Exemple de flux

1. L’utilisateur clique sur “Ajouter au panier” → appel POST `/panier/ajouter`
2. L’élément est visible dans `Panier.jsx` avec sa quantité et son prix total
3. Il peut modifier ou supprimer chaque produit
4. En cliquant sur “Valider le panier” → appel API POST `/panier/valider`
5. Une commande est créée côté backend

---

## 🌿 Endpoints Backend associés

```
POST   /panier/ajouter
PUT    /panier/modifier/{id}
DELETE /panier/supprimer/{id}
POST   /panier/valider
```

Chaque endpoint nécessite un token JWT valide.

---

## 🧠 À noter

- Le panier peut être stocké côté frontend temporairement (useState, Context) ou géré uniquement via l’API.
- Lors de la validation du panier, une commande est créée avec un timestamp et les lignes de produits.

---

## 📂 Exemple d’arborescence

```
frontend/
├── pages/
│   └── Panier.jsx
backend/
├── routes/
│   └── panier.py
```

---

## ✅ Bonnes pratiques

- Vérifier si un produit est déjà dans le panier avant de l’ajouter
- Afficher un message de confirmation après chaque action
- Utiliser des Toasts ou modals pour les retours utilisateurs
- Gérer les erreurs API proprement (ex: stock insuffisant)

---

Rédigé pour la branche : `feature/panier`


