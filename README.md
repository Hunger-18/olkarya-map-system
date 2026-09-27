<div align="center">

<img src="icon-512.png" alt="Olkarya" width="110" />

# 🐉 Olkarya

**Le compagnon de table ultime pour Maître du Jeu.**

Gestion multi-campagnes, battlemap temps réel pour OBS, tracker d'initiative,
dés 3D et bot Discord — dans une seule application desktop.

[![Version](https://img.shields.io/badge/version-1.0.5-8b5cf6)](https://github.com/Hunger-18/olkarya-map-system/releases)
[![Plateforme](https://img.shields.io/badge/platform-Windows%20(x64)-3b82f6)](https://github.com/Hunger-18/olkarya-map-system/releases)
[![Mise%20à%20jour](https://img.shields.io/badge/mise%20à%20jour-automatique-10b981)](https://github.com/Hunger-18/olkarya-map-system/releases)

</div>

---

## 📖 Sommaire

- [✨ Présentation](#-présentation)
- [🧩 Fonctionnalités](#-fonctionnalités)
- [⬇️ Téléchargement](#️-téléchargement)
- [🚀 Premiers pas](#-premiers-pas)
- [📺 Overlay OBS](#️-overlay-obs)
- [💾 Tes données](#-tes-données)
- [🛠️ Dépannage](#️-dépannage)
- [❓ FAQ](#-faq)
- [📄 Licence](#-licence)

---

## ✨ Présentation

Olkarya est un logiciel de gestion de campagne pour jeux de rôle sur table
(D&D 5e), pensé pour le MJ qui joue en direct.

Il regroupe tout ce dont un MJ a besoin pour mener ses sessions, en local,
sans compte ni service externe :

- un **hub** pour créer et organiser ses campagnes (et one-shots) ;
- une **interface de campagne** complète : notes, joueurs, PNJ, créatures, cartes,
  tokens, documents, musique, initiative ;
- une **battlemap temps réel** synchronisée entre la vue MJ et la vue joueurs (OBS) ;
- un **bot Discord** intégré : dés 3D à l'écran, initiative, jets de mort, musique.

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

Notes · 🧙 Joueurs · 👹 PNJ · 🐺 Créatures · 🗺️ Cartes · 🪙 Tokens ·
📎 Documents · ⚔️ Initiative · 🎵 Musique · ⚙️ Configuration

### 🗺️ Battlemap

- Grille personnalisable (jusqu'à 1000 × 1000), tokens, brouillard de guerre, murs et lumières.
- Paliers multi-étages avec murs, lumières et brouillard indépendants.
- Zones d'effet, mesure de distance, pings, point d'apparition.
- **Caméra MJ** et **caméra joueurs** séparées (réglage `Zoom OBS` 50 %–200 %).
- Synchronisation bidirectionnelle des PV : **initiative ↔ fiches ↔ tokens**.

### 🎲 Bot Discord

- `/roll`, `/av`, `/desav`, `/death-save` — dés 3D animés affichés dans l'overlay OBS.
- Initiative depuis Discord avec détection du nom du token.
- Contrôle de la musique de la campagne.
- Multi-serveurs Discord : chaque serveur a son propre lien OBS.

### ⬆️ Mises à jour automatiques

L'application vérifie les nouvelles versions au démarrage. Si une version plus
récente est disponible, elle te propose le téléchargement et l'installation
automatique (avec sauvegarde et retour arrière en cas de problème).

---

## ⬇️ Téléchargement

1. Va sur la page des versions :
   **[github.com/Hunger-18/olkarya-map-system/releases](https://github.com/Hunger-18/olkarya-map-system/releases)**
2. Télécharge le fichier `olkarya-map-system-<version>-win.zip`.
3. Décompresse-le où tu veux (dossier `Olkarya Map System`).
4. Lance `olkarya-map-system.exe`.

> ⚠️ **Au tout premier lancement**, les données de l'application sont
> automatiquement copiées vers `%APPDATA%\olkarya-map-system` (voir
> [Tes données](#-tes-données)). Ensuite, plus rien à faire.

**Prérequis** : Windows 10/11 64 bits. Aucun installation, aucun compte,
tout fonctionne en local.

---

## 🚀 Premiers pas

1. **Lance l'application** → le hub s'ouvre dans ton navigateur.
2. **Crée une campagne** (ou un one-shot).
3. **Entre dans la campagne** et utilise les modules via la barre latérale.
4. **Battlemap** : importe une carte, place les tokens, prépare le brouillard.
5. **Bot Discord** : démarre-le depuis le panneau Discord du hub.
   - Au **premier lancement**, une fenêtre de configuration s'ouvre :
     renseigne le **Token** et le **Client ID** de ton application Discord
     ([Discord Developer Portal](https://discord.com/developers/applications)),
     puis valide.
   - Le token est stocké **uniquement sur ta machine**, jamais dans un build.

---

## 📺 Overlay OBS

La vue joueurs se lit dans OBS pendant que tu joues la carte de ton côté.

1. **Sources** → **+** → **Navigateur**
2. **URL** : `http://localhost:3000/obs`
3. **Largeur / hauteur** : adapte à la résolution de ton stream
4. **OK**

L'overlay affiche :

- la battlemap (vue joueurs) avec tokens et brouillard de guerre ;
- le **tracker d'initiative** flottant ;
- les **dés 3D** lancés depuis Discord.

> ℹ️ Le bot doit être démarré (panneau Discord du hub) pour les dés 3D
> et la musique.

---

## 💾 Tes données

Toutes tes données — campagnes, fiches, images importées, banque de tokens,
configuration du bot — sont stockées **en dehors** de l'application, dans :

```
%APPDATA%\olkarya-map-system\
├── data\      # JSON des campagnes et des fiches
└── assets\    # cartes, tokens, fichiers, musique
```

Conséquence : **tes données survivent** à toute mise à jour, à la suppression
du dossier de l'application et à sa réinstallation. Sauvegarde ce dossier et
tu as une copie de tout.

---

## 🛠️ Dépannage

| Problème | Solution |
|----------|----------|
| L'app ne s'ouvre pas | Vérifie que le port `3000` est libre, puis relance. |
| Le bot ne démarre pas | Panneau Discord du hub → vérifie token / Client ID. |
| Pas de dés 3D à l'écran | Le bot doit tourner (port `4005`). |
| Les joueurs ne voient rien | L'URL OBS doit pointer vers `http://localhost:3000/obs`. |
| La musique ne joue pas | Formats supportés : MP3, OGG, WAV, FLAC, M4A, AAC, OPUS, WEBM. |
| « Mes campagnes ont disparu » | Elles sont dans `%APPDATA%\olkarya-map-system`. |

---

## ❓ FAQ

**Les données sont-elles envoyées sur Internet ?**
Non. L'application et le bot tournent en local, sur ta machine. Seul le bot
Discord se connecte à Discord, uniquement si tu l'utilises.

**Puis-je jouer sans Discord ?**
Oui. La battlemap, les fiches et l'initiative fonctionnent sans le bot. Le bot
ajoute les dés 3D, l'initiative et la musique depuis Discord.

**Puis-je jouer à distance / en streaming ?**
Oui, c'est l'usage principal : tu lances le bot en « hébergé », chaque MJ
configure le lien OBS de son propre Map System.

**Comment sont mises à jour mes cartes et tokens ?**
Ils ne sont pas dans l'application : ils restent dans ton dossier `%APPDATA%`,
donc aucune mise à jour ne peut les écraser.

---

## 📄 Licence

Logiciel distribué gratuitement, développé pour le streaming D&D. Aucune
licence open source n'est définie. Les bibliothèques utilisées (Electron,
Express, Socket.IO, Discord.js, Babylon.js…) restent sous leurs licences
respectives.

---

<div align="center">

*Bon jeu, et bonne route sur le continent d'Olkarya !* 🎲✨

</div>
