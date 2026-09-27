<div align="center">

<img src="icon-512.png" alt="Olkarya" width="110" />

# 🐉 Olkarya

**Le compagnon de table ultime pour Maître du Jeu.**

Gestion multi-campagnes, battlemap temps réel pour OBS, tracker d'initiative,
dés 3D et bot Discord — dans une seule application desktop.

[![Version](https://img.shields.io/badge/version-1.0.5-8b5cf6)](https://github.com/Hunger-18/olkarya-map-system/releases)
[![Plateforme](https://img.shields.io/badge/platform-Windows-3b82f6)](https://github.com/Hunger-18/olkarya-map-system/releases)
[![Stack](https://img.shields.io/badge/stack-Electron%20%7C%20Express%20%7C%20Socket.IO%20%7C%20Discord.js-10b981)](https://github.com/Hunger-18/olkarya-map-system)
[![Langage](https://img.shields.io/badge/langage-JavaScript-yellow)](https://github.com/Hunger-18/olkarya-map-system)

</div>

---

## 📖 Sommaire

- [✨ Présentation](#-présentation)
- [🧩 Fonctionnalités](#-fonctionnalités)
- [🛠️ Stack technique](#️-stack-technique)
- [🚀 Installation](#-installation)
- [🎮 Utilisation](#-utilisation)
- [📺 Overlay OBS](#️-overlay-obs)
- [🗂️ Structure du dépôt](#️-structure-du-dépôt)
- [📚 Documentation](#-documentation)
- [💾 Données utilisateur](#-données-utilisateur)
- [🛠️ Dépannage](#️-dépannage)
- [📄 Licence](#-licence)

---

## ✨ Présentation

Olkarya regroupe tout ce dont un MJ a besoin pour mener ses sessions, en local,
sans compte ni service externe :

- un **hub** pour créer et organiser ses campagnes (et one-shots) ;
- une **interface de campagne** complète : notes, joueurs, PNJ, créatures, cartes,
  tokens, documents, musique, initiative ;
- une **battlemap temps réel** synchronisée entre la vue MJ et la vue joueurs (OBS) ;
- un **bot Discord** intégré : dés 3D à l'écran, initiative,jets de mort, musique.

---

## 🧩 Fonctionnalités

### 🏰 Hub — gestion des campagnes

| Fonction | Description |
|----------|-------------|
| 📁 Campagnes | Créer, renommer, dupliquer, supprimer |
| ⚡ One-shots | Campagne ponctuelle en un clic |
| 🖼️ Couvertures | Jaquette personnalisée par campagne |
| 📊 Statistiques | Nombre de campagnes, dernière session |
| 🤖 Panneau Bot | Configurer et contrôler le bot Discord |

### 📜 Modules de campagne

Notes · Joueurs · PNJ · Créatures · Cartes · Tokens · Documents ·
⚔️ Initiative · 🎵 Musique · ⚙️ Configuration

### 🗺️ Battlemap

- Grille personnalisable (jusqu'à 1000 × 1000), tokens, brouillard de guerre, murs et lumières.
- Paliers multi-étages avec murs, lumières et brouillard indépendants.
- Zones d'effet, mesure de distance, pings, point d'apparition.
- **Caméra MJ** et **caméra joueurs** séparées (réglage `Zoom OBS` 50 %–200 %).
- Synchronisation bidirectionnelle des PV : **initiative ↔ fiches ↔ tokens**.

### 🎲 Bot Discord

- `/roll`, `/av`, `/desav`, `/death-save` — dés 3D animés affichés dans l'overlay OBS.
- Initiative depuis Discord avec détection du nom du token.
- Contrôle de la musique de la campagne, multi-serveurs Discord avec lien
  OBS dédié par serveur.

### ⬆️ Mises à jour

L'app détecte les releases GitHub au démarrage, télécharge, extrait et applique
la mise à jour au prochain lancement (sauvegarde + rollback automatiques).

---

## 🛠️ Stack technique

| Composant | Rôle |
|-----------|------|
| **Electron** | Application desktop (fenêtre, setup bot, updater) |
| **Express** | Serveur local — `http://localhost:3000` |
| **Socket.IO** | Synchronisation temps réel MJ ↔ vue joueurs |
| **Discord.js v14** | Bot (dés, initiative, musique) — port `4005` |
| **@3d-dice/dice-box** | Rendu des dés 3D (Babylon.js) |
| **electron-builder** | Build Windows (`dist/*.zip`) |

---

## 🚀 Installation

### 🖥️ Utilisateur final

1. Télécharge la dernière release :
   [github.com/Hunger-18/olkarya-map-system/releases](https://github.com/Hunger-18/olkarya-map-system/releases)
2. Décompresse le `.zip` où tu veux (dossier `Olkarya Map System`).
3. Lance `olkarya-map-system.exe`.

> ⚠️ **Première mise à jour seulement** : décompresse **par-dessus** l'ancienne
> installation, sans la supprimer — les données sont importées automatiquement
> vers `%APPDATA%\olkarya-map-system`. Ensuite, plus rien à faire.

### 🧑‍💻 Développement

Prérequis : **Node.js 18+**.

```bash
# Application principale
cd "Olkarya Map System"
npm install
npm run electron     # app desktop complète
npm start            # serveur seul → http://localhost:3000

# Bot Discord
cd "../Olkarya Bot"
npm install
npm start            # bot + dés 3D → port 4005
```

Build d'un exécutable :

```bash
npm run build-exe    # → dist/olkarya-map-system-<version>-win.zip
```

---

## 🎮 Utilisation

1. **Lance l'app** → le hub s'ouvre sur `http://localhost:3000/hub`.
2. **Crée une campagne** (ou un one-shot).
3. **Entre dans la campagne** et utilise les modules via la barre latérale.
4. **Battlemap** : importe une carte, place les tokens, prépare le brouillard.
5. **Bot** : démarre-le depuis le panneau Discord du hub (token + Client ID
   du [Discord Developer Portal](https://discord.com/developers/applications)).

---

## 📺 Overlay OBS

1. **Sources** → **+** → **Navigateur**
2. **URL** : `http://localhost:3000/obs`
3. Largeur / hauteur : adapte à ta résolution de stream.

L'overlay affiche la battlemap (vue joueurs), le tracker d'initiative et les
dés 3D lancés depuis Discord. Le bot doit tourner pour les dés et la musique.

---

## 🗂️ Structure du dépôt

```
Olkarya System Map/
├── Olkarya Map System/        # 👉 Application desktop (Electron)
│   ├── electron/              #   fenêtre principale, setup bot, updater
│   ├── server/                #   Express + Socket.IO (port 3000)
│   ├── hub/                   #   interface hub (multi-campagnes)
│   ├── campaign/              #   interface campagne + modules + battlemap
│   ├── obs/                   #   overlay joueurs pour OBS
│   ├── shared/                #   code partagé (paths, toasts, dossier)
│   └── build/ dist/           #   icônes / builds générés
├── Olkarya Bot/               # 👉 Bot Discord + dés 3D (port 4005)
│   ├── server.js              #   HTTP + WebSocket + bot
│   ├── index.html             #   page des dés (OBS-compatible)
│   └── assets/                #   modèle 3D, thèmes, physique WASM
├── archives/                  # archives de données (non versionné)
└── icon-512.png               # logo du projet
```

Le build Electron embarque le bot Discord via `extraResources` et le démarre
depuis le panneau du hub.

---

## 📚 Documentation

| Document | Contenu |
|----------|---------|
| [📘 Documentation de l'application](Olkarya%20Map%20System/README.md) | Installation, modules, battlemap, OBS, MAJ |
| [🤖 Documentation du bot Discord](Olkarya%20Bot/README.md) | Commandes slash, setup multi-serveurs, overlay |
| [📝 Notes de version](Olkarya%20Map%20System/PATCHNOTES.md) | Ce qui change à chaque release |
| [🔧 Setup Discord](Olkarya%20Bot/DISCORD_SETUP.md) | Création de l'application Discord |
| [📺 Guide OBS](Olkarya%20Bot/OBS_GUIDE.md) | Configuration de l'overlay |
| [🎲 Intégration des dés](Olkarya%20Bot/COMPLETION_SUMMARY.md) | Récapitulatif du système de dés |

---

## 💾 Données utilisateur

Toutes les données (campagnes, fiches, uploads, banque de tokens, config du bot)
vivent **hors de l'application**, dans le dossier utilisateur Windows :

```
%APPDATA%\olkarya-map-system\
├── data\      # JSON des campagnes et des fiches
└── assets\    # cartes, tokens, fichiers, musique
```

Elles survivent à toute mise à jour, suppression ou réinstallation de l'app.

---

## 🛠️ Dépannage

| Problème | Solution |
|----------|----------|
| L'app ne s'ouvre pas | Vérifie que le port `3000` est libre, puis relance. |
| Le bot ne démarre pas | Panneau Discord du hub → vérifie token / Client ID. |
| Pas de dés 3D à l'écran | Le bot doit tourner (port `4005`). |
| Les joueurs ne voient rien | L'URL OBS doit pointer vers `http://localhost:3000/obs`. |
| « Mes campagnes ont disparu » | Tes données sont dans `%APPDATA%\olkarya-map-system`. |

---

## 📄 Licence

Projet personnel pour le streaming D&D. Aucune licence open source n'est encore
définie. Les bibliothèques utilisées (Electron, Express, Socket.IO, Discord.js,
Babylon.js, etc.) restent sous leurs licences respectives.

---

<div align="center">

*Bon jeu, et bonne route sur le continent d'Olkarya !* 🎲✨

</div>
