
# 🖼️ Frontend – Interface utilisateur (React.js)

## 🎯 Objectif
Développement de l’interface utilisateur pour la gestion de produits et de panier d’achat dans une application web e-commerce.

---

## 📌 Technologies utilisées
- React.js
- React Router DOM
- Axios (pour communication avec l’API FastAPI)
- Bootstrap ou CSS personnalisé
- Context API ou useState (pour état local)

---

## 🛠️ Tâches à réaliser dans cette branche `feature/frontend`

| Composant / Page        | Description                                                                 |
|-------------------------|-----------------------------------------------------------------------------|
| `App.js`                | Configuration des routes de navigation                                      |
| `Navbar.jsx`            | Barre de navigation avec lien vers Accueil, Produits, Panier, Connexion     |
| `HomePage.jsx`          | Page d’accueil avec message d’introduction                                 |
| `ProductList.jsx`       | Liste des produits récupérés depuis l’API (`/produits`)                    |
| `ProductDetail.jsx`     | Affichage des détails d’un produit sélectionné                              |
| `Panier.jsx`            | Affichage du panier avec option de modifier ou supprimer des articles       |
| `Login.jsx`             | Formulaire de connexion (login utilisateur/admin)                           |
| `Register.jsx`          | Formulaire d’inscription                                                    |
| `AdminPanel.jsx`        | Interface conditionnelle pour administrateur (accessible selon le rôle)     |

---

## 🔁 Flux de données principal
1. L’utilisateur se connecte via `Login.jsx` → récupère un token JWT.
2. Les produits sont chargés avec Axios depuis `/produits` et affichés dans `ProductList.jsx`.
3. L’utilisateur ajoute des produits à son panier (géré via état local ou global).
4. Le panier est visible dans `Panier.jsx` avec possibilité de validation.
5. Si l’utilisateur est admin, accès à `AdminPanel.jsx` pour gérer les produits.

---

## ✅ Bonnes pratiques
- Utiliser des `useEffect()` pour les appels API
- Centraliser les appels dans un fichier `api.js` (facultatif mais recommandé)
- Stocker le token JWT dans `localStorage`
- Cacher les routes réservées à l’admin si l’utilisateur est simple
- Respecter une structure de composants claire (`components/`, `pages/`, `styles/`)

---

## 📂 Arborescence recommandée

```
frontend/
├── src/
│   ├── components/
│   │   ├── Navbar.jsx
│   │   └── ProductCard.jsx
│   ├── pages/
│   │   ├── HomePage.jsx
│   │   ├── ProductList.jsx
│   │   ├── ProductDetail.jsx
│   │   ├── Panier.jsx
│   │   ├── Login.jsx
│   │   ├── Register.jsx
│   │   └── AdminPanel.jsx
│   ├── App.js
│   └── index.js
├── public/
├── package.json
└── README.md
```

---

Rédigé pour la branche : `feature/frontend`