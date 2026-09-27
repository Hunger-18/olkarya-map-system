<div align="center">

<img src="icon-512.png" alt="Olkarya" width="110" />

# 🐉 Olkarya

**Le compagnon de table ultime pour Maître du Jeu.**

Gestion multi-campagnes, battlemap temps réel pour OBS, tracker d'initiative,
dés 3D et bot Discord — dans une seule application desktop.

[![Version](https://img.shields.io/badge/version-1.0.5-8b5cf6)](https://github.com/Hunger-18/olkarya-map-system/releases)
[![Plateforme](https://img.shields.io/badge/platform-Windows%20(x64)-3b82f6)](https://github.com/Hunger-18/olkarya-map-system/releases)
[![Mise%20à%20jour](https://img.shields.io/badge/mise%20à%20jour-automatique-10b981)](https://github.com/Hunger-18/olkarya-map-system/releases)
[![Code](https://img.shields.io/badge/code-vibe%20cod%C3%A9-ff69b4)](https://github.com/Hunger-18/olkarya-map-system)

</div>

---

## 📖 Sommaire

- [✨ Présentation](#-présentation)
- [🌊 Projet vibecodé](#️-projet-vibecodé)
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
- un **bot Discord** hébergé : dés 3D à l'écran, initiative, jets de mort, musique —
  il tourne sur un serveur distant, pas sur ton PC.

> ### 🌊 Projet vibecodé
>
> Olkarya a été **conçu et écrit en « vibe coding »** : le code est produit puis
> itéré en boucle avec une IA, à partir d'une idée et d'un besoin de table —
> sans cahier des charges, sans revue de code et sans suite de tests.
>
> Concrètement : **ça fonctionne, mais attends-toi à des bugs**, à des
> comportements inattendus et à un code hétérogène. Chaque version est vérifiée
> à la main avant livraison, jamais par des tests automatisés.
>
> → Lis [Projet vibecodé](#️-projet-vibecodé) avant de l'utiliser pour une vraie campagne.

---

## 🌊 Projet vibecodé

Olkarya est un **projet vibecodé** (*vibe coding*) : il a été entièrement
conçu et écrit en itérant avec une IA.

| | |
|---|---|
| 🧠 **Comment** | Une idée de table → prompt → code généré → testé en jeu → corrigé → rebouclé |
| 🚫 **Ce qui n'existe pas** | Cahier des charges, revue de code, tests automatisés |
| ✅ **Ce qui existe** | Un logiciel qui tourne, utilisé chaque semaine en session |
| ⚠️ **Conséquence** | Des bugs, des comportements inattendus, un code hétérogène |

### Ce que ça veut dire pour toi

- **Sauvegarde `%APPDATA%\olkarya-map-system`** avant une grosse session.
- **Teste sur une campagne jetable** avant de migrer ta campagne principale.
- **Signale les bugs** ([issues](https://github.com/Hunger-18/olkarya-map-system/issues)) :
  ils sont attendus, et les retours utiles.
- **Rien n'est garanti** : ni stabilité, ni sauvegarde, ni sécurité. À utiliser
  comme un outil de jeu, pas comme un logiciel critique.

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
- Initiative et jets de mort depuis Discord, avec détection du nom du token.
- Contrôle de la musique de la campagne.
- **Multi-serveurs** : un seul bot hébergé sert plusieurs MJ, chacun avec son
  ID de serveur, sa clé et son lien OBS.

### 🔗 Comment ça se passe

Ton PC ne fait **que demander** au bot hébergé (jamais l'inverse) :

```
Ton PC (application)  ──requête──▶  Bot hébergé  ──▶  Discord
       ▲                                    │
       └────── initiative / mort / musique ──┘
```

Tu n'as **rien à ouvrir** sur ton PC : ni port entrant, ni tunnel. En revanche,
il faut que ton pare-feu Windows autorise les connexions sortantes vers Internet.

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
5. **Bot Discord** (optionnel) : ouvre le panneau Discord du hub et renseigne
   - l'**ID de ton serveur Discord**,
   - la **clé secrète** fournie par l'administrateur du bot.

   Le bot n'est pas installé chez toi : il tourne **sur un serveur distant**, ce
   qui lui permet de servir plusieurs MJ en même temps. Ta clé est stockée
   uniquement sur ta machine.

---

## 📺 Overlay OBS

Deux sources navigateur à ajouter — l'application te fournit les deux liens
tout prêts dans la modale **« Liens OBS »** du hub.

### 1️⃣ La carte (vue joueurs)

1. **Sources** → **+** → **Navigateur**
2. **URL** : `http://localhost:3000/obs`
3. **Largeur / hauteur** : adapte à la résolution de ton stream
4. **OK**

Affiche la battlemap avec tokens et brouillard de guerre, plus le **tracker
d'initiative** flottant.

### 2️⃣ Les dés 3D (bot hébergé)

1. **Sources** → **+** → **Navigateur**
2. **URL** : le lien de dés donné par la modale (`…/index.html?guild=…&token=…`)
3. **OK**

Affiche les dés 3D lancés depuis Discord. Cette page est servie par le **bot
distant**, pas par ton application.

> 🔒 Ce lien contient ta clé : **ne le partage pas publiquement** (ni dans le
> chat de ton stream, ni dans une description de vidéo).

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
| Le bot ne répond pas | Vérifie l'ID de serveur et la clé dans le panneau Discord du hub. |
| Pas de dés 3D à l'écran | La source dés pointe-t-elle bien sur le lien `…/index.html?guild=…&token=…` ? |
| L'initiative Discord arrive pas | L'app interroge le bot hébergé toutes les 3 s : vérifie ta connexion sortante et l'ID de serveur. |
| Les joueurs ne voient rien | L'URL OBS doit pointer vers `http://localhost:3000/obs`. |
| La musique ne joue pas | Formats supportés : MP3, OGG, WAV, FLAC, M4A, AAC, OPUS, WEBM. |
| « Mes campagnes ont disparu » | Elles sont dans `%APPDATA%\olkarya-map-system`. |

---

## ❓ FAQ

**Mes données partent-elles sur Internet ?**

Tes **fiches, notes, cartes et images ne quittent jamais ton PC** : l'application
tourne en local (`localhost:3000`) et n'envoie rien nulle part.

En revanche, si tu actives le bot Discord, ta machine **contacte le bot
hébergé** pour lui demander de lancer les dés, transmettre l'initiative et les
jets de mort, et piloter la musique. Ces échanges contiennent des noms de
personnages, des jets et des noms de fichiers audio.

👉 Le bot hébergé est un **service tiers** : son administrateur voit ces
échanges. Si ça ne te va pas, n'active pas le bot — tout le reste fonctionne
sans.

**Le bot est installé sur mon PC ?**

Non. Il tourne sur un serveur distant, ce qui lui permet de servir plusieurs MJ.
Tu n'as donc **rien à installer ni à lancer** côté bot, et **aucun port à
ouvrir** sur ton PC.

**Puis-je jouer sans Discord ?**
Oui. La battlemap, les fiches et l'initiative fonctionnent sans le bot. Le bot
ajoute seulement les dés 3D, l'initiative et la musique depuis Discord.

**Puis-je jouer à distance / en streaming ?**
Oui, c'est l'usage principal : l'overlay est une page web, et chaque MJ a son
propre lien et sa propre clé.

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
