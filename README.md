# 🐺 WereFriends

> Une application mobile pour jouer **aux Loups-Garous de Thiercelieux** sans avoir besoin d'un maître du jeu et enfin ne plus avoir a sacrifier un ami à chaque partie.


![Project Status](https://img.shields.io/badge/status-active-success.svg)
![Flutter](https://img.shields.io/badge/flutter-3.27.1+-blue.svg)
![React](https://img.shields.io/badge/dart-3.6.0+-blue.svg)

## 📖 À propos

**WereFriends** est une solution mobile conçue pour résoudre le dilemme éternel des soirées jeux entre amis : "Qui fait le maître du jeu ?". L'application permet à un groupe d'amis de créer un salon, de choisir les paramètres de la partie et de jouer aux Loups-Garous de Thiercelieux tous ensemble en s'amusant (ou en se trahisant).

Le projet combine un backend asynchrone performant avec un service de gestion de la partie dédié et une interface utilisateur moderne en temps réel.

### ✨ Fonctionnalités Clés

*   **🕵️ Scraping Intelligent** : Extraction automatisée des watchlists depuis **Letterboxd** (SensCritique prochainement) en utilisant **HTTP direct** et **BeautifulSoup4** pour une performance maximale.

*   **🤝 Salons Temps Réel** : Système de "rooms" propulsé par des **WebSockets** pour une synchronisation instantanée entre les participants.
*   **🧠 Algorithmes de Matching** : Calcul dynamique de l'**intersection** (films communs à tous) ou de l'**union** (tous les films disponibles) du groupe.
*   **📺 Intégration Streaming** : Filtrage intelligent par plateforme de streaming (Netflix, Prime, Disney+, etc.) et par région géographique.
*   **🚀 Stack Moderne** : Backend asynchrone (FastAPI), Microservice isolé (Flask), et Frontend ultra-rapide (Vite/React 19).

## 🎥 Visualisation

<div align="center">
  <img src="miscellaneous/cinematch_demo.gif" alt="CineMatch Demo" width="100%">
</div>

> [!TIP]
> 🌐 **Site Démo** : [cinematch.beclay.fr](https://cinematch.beclay.fr)
>
> 🔒 **Note** : Le code source sera rendu **public prochainement**.


---

## 🛠 Architecture Technique

Le projet adopte une architecture micro-services orchestrée par Docker pour une séparation claire des responsabilités.

### Backend Services (`/services`)
*   **Framework** : [FastAPI](https://fastapi.tiangolo.com/) (Asynchrone, haute performance).
*   **Base de données** : PostgreSQL avec [SQLAlchemy](https://www.sqlalchemy.org/).
*   **Temps réel** : WebSockets pour la gestion des salons et des membres.
*   **Sécurité** : Sessions par cookies HttpOnly.

### Scraper Service (`/scraper`)
*   **Framework** : [Flask](https://flask.palletsprojects.com/) (Microservice léger).
*   **Moteurs d'extraction** : 
    *   [Playwright](https://playwright.dev/) : Pour la navigation complexe.
    *   [BeautifulSoup4](https://www.crummy.com/software/BeautifulSoup/) : Pour le parsing HTML rapide.

### Frontend (`/frontend`)
*   **Framework** : [React 19](https://react.dev/)
*   **Build Tool** : [Vite](https://vitejs.dev/)
*   **UI/UX** : Lucide React pour les icônes, Canvas-confetti pour les célébrations de "Match".

### Infrastructure
*   **Conteneurisation** : Docker & Docker Compose.
*   **Gestionnaire de Paquets** : [uv](https://docs.astral.sh/uv/) pour une gestion éclair des dépendances Python.

---

## 🎮 Guide d'Utilisation

1.  **Créer un Salon** : Générez un code de salon unique depuis l'accueil.
2.  **Rejoindre** : Partagez le code avec vos amis.
3.  **Importer sa Watchlist** : Entrez votre nom d'utilisateur **Letterboxd**.

4.  **Configurer les Filtres** : Une fois dans la room, filtrez les résultats par plateforme de streaming (Netflix, Disney+, etc.) et par pays pour ne voir que ce qui est disponible pour vous.
5.  **Swiper et Matcher** : Indiquez vos préférences en swipant les films. L'application mettra en évidence les "Matchs" parfaits où tout le monde a swipé à droite !


---

## 📁 Structure du Projet

```
.
├── api/                    # Backend FastAPI (Logique rooms & auth)
│   ├── app.py              # Point d'entrée
│   ├── routers/            # Endpoints (films, rooms, websockets)
│   └── services/           # Logique métier (matching algorithm)
├── scraper/                # Microservice de scraping (Flask)
│   ├── services/           # Scrapers Letterboxd & SensCritique
│   └── app.py              # API du scraper
├── frontend/               # UI React (Vite)
│   ├── src/                # Composants et hooks
│   └── public/             # Assets statiques
├── miscellaneous/          # Assets de démonstration (GIFs, images)
├── deployment/             # Dockerfiles et scripts de déploiement
├── docker-compose.yml      # Orchestration des services
└── pyproject.toml          # Dépendances Python (uv)
```

---

## 👥 Auteur

*   **Taël Baucher** - [TaelBaucher](https://github.com/TaelBaucher)

## 🤝 Contribuer

Ce projet est actuellement en phase de développement privé. Le code ne sera pas rendu public pour l'instant à moins d'un changement de volonté.
