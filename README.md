<div align="center">
  <h1>🐺 WereFriends</h1>
  <p><i>L'adaptation mobile interactive des "Loups-Garous de Thiercelieux". <br> Simplifiez vos soirées : l'app gère le MJ, vous gérez le bluff.</i></p>
</div>

![Status](https://img.shields.io/badge/Status-En%20D%C3%A9veloppement-green)
![Repository](https://img.shields.io/badge/Repository-priv%C3%A9-orange)

![Flutter](https://img.shields.io/badge/flutter-3.27.1+-blue.svg)
![React](https://img.shields.io/badge/dart-3.6.0+-blue.svg)


> 🔒 **Dépôt Privé & Confidentiel** : Le code source de ce projet n'est pas public. Cette page documente l'avancement technique et les choix d'architecture pour mon portfolio.

---

## 📖 À propos

**WereFriends** revisite le jeu classique de déduction sociale pour le rendre accessible partout. Que vous soyez dans la même pièce ou à distance, l'application automatise le rôle du maître du jeu, gère les phases de nuit et les interactions secrètes.

L'objectif est de supprimer les barrières logistiques pour se concentrer sur l'essentiel : **le débat, le bluff et la trahison.**

---

## ✨ Fonctionnalités Clés

* 🔐 **Authentification** : Accès sécurisé via Email ou Google Sign-In (Firebase Auth).
* 🏠 **Gestion de Lobby** : Création de salons privés avec synchronisation en temps réel.
* 🎭 **Rôles Interactifs** : Distribution automatique et consultation secrète des rôles sur mobile.
* 🗳️ **Système de Vote** : Interface de vote dynamique pour éliminer les suspects durant la phase de jour.
* 🌙 **Cycle Automatisé** : Transition fluide entre les phases de nuit (actions spéciales) et de jour.

---

## 🚀 Étapes du Projet

- [x] **Initialisation** : Configuration Flutter & environnement Firebase.
- [x] **Authentification** : Système complet Login/Register & Social Auth.
- [x] **Lobby** : Création de partie et gestion des membres en temps réel.
- [ ] **Gameplay - Distribution** : Algorithme d'attribution équitable des rôles.
- [ ] **Gameplay - Nuit** : Logique séquentielle pour les Loups, la Voyante et la Sorcière.
- [ ] **Gameplay - Jour** : Système de débats chronométrés et votes.
- [ ] **UI/UX** : Design "Dark/Mystery" et animations avancées.

---

## 📈 Dernières Mises à Jour

> **v1.0.1 — Conception de la phase de jeu** *(05/05/2026)*  
> Finalisation de la logique de transition entre les tours.

> **v0.1.0 — Refonte de l'Architecture** *(28/11/2025)*  
> - Injection de dépendances avec `Provider`.
> - Séparation stricte Services (Métier) / Controllers (UI State).

---

## 🛠 Stack Technique

- **Frontend** : <img src="https://img.shields.io/badge/Flutter-02569B?style=flat-square&logo=flutter&logoColor=white)" />
- **Backend** : <img src="https://img.shields.io/badge/Firebase-FFCA28?style=flat-square&logo=firebase&logoColor=black)" />
- **State Management** : `Provider`
- **Architecture** : Clean Architecture (Models, Services, Controllers).

---

## 📸 Aperçu (non disponible)

<div align="center">
  <table>
    <tr>
      <td><img src="path/to/login.png" height="450"></td>
      <td><img src="path/to/lobby.png" height="450"></td>
      <td><img src="path/to/game.png" height="450"></td>
    </tr>
    <tr>
      <td align="center"><b>Authentification</b></td>
      <td align="center"><b>Lobby Temps Réel</b></td>
      <td align="center"><b>Phase de Jeu</b></td>
    </tr>
  </table>
</div>

---

## 📁 Architecture `lib/`

```text
lib/
├── main.dart           # Point d'entrée
├── ui/                 # Vues (Screens & Widgets)
├── controllers/        # Logique d'interface & État
├── services/           # API, Auth & Flux Firestore
└── models/             # Player, Role, Room models