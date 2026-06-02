# Pterodactyl Egg: Discord.js (Ultimate Canvas Support)

[![Pterodactyl Egg](https://img.shields.io/badge/Pterodactyl-Egg-blue?style=for-the-badge&logo=pterodactyl)](https://pterodactyl.io)
[![Node.js](https://img.shields.io/badge/Node.js-22%20%7C%2020%20%7C%2018-green?style=for-the-badge&logo=node.js)](https://nodejs.org)

Un Egg Pterodactyl hautement optimisé et pré-configuré pour héberger des bots Discord lourds et exigeants basés sur **Discord.js** ou tout autre framework Node.js.

Cet Egg résout le problème classique des dépendances manquantes lors du `npm install` en intégrant nativement les outils de compilation requis et les bibliothèques système pour le traitement d'images et de contenus multimédias.

## ✨ Caractéristiques & Avantages

* **Ultimate Canvas Support :** Plus d'erreurs de compilation avec le module `canvas`. L'Egg installe automatiquement toutes les dépendances système requises (`libcairo2-dev`, `libpango1.0-dev`, `libjpeg-dev`, etc.).
* **Support Audio & Vidéo (FFmpeg) :** Intégration native de `ffmpeg` pour permettre à vos bots de gérer la musique, le traitement audio et les interactions vocales sans configuration supplémentaire.
* **Outils de Compilation Inclus :** Intègre `build-essential` (Python, Make, G++) permettant de compiler sans encombre les modules natifs (C/C++) lors de l'installation de vos paquets Node.
* **Versions de Node.js Flexibles :** Support complet des versions récentes via les images Docker de la communauté (Yolks) :
    * `Node.js 22` (Recommandé)
    * `Node.js 20` (LTS)
    * `Node.js 18`

## 📦 Dépendances Système Pré-installées

Le script d'installation configure automatiquement l'environnement avec les paquets suivants :
* `git` & `curl`
* `ffmpeg` (Audio/Vidéo)
* `build-essential` (Outils de compilation C/C++)
* `libcairo2-dev`, `libpango1.0-dev`, `libjpeg-dev`, `libgif-dev`, `librsvg2-dev` (Rendu graphique pour `canvas`)

## 🚀 Installation de l'Egg sur votre Panel

1. Téléchargez le fichier JSON de l'egg depuis ce dépôt GitHub.
2. Rendez-vous sur le **Panel d'Administration** de votre Pterodactyl.
3. Allez dans la section **Nests** (Nids) et sélectionnez ou créez un Nest adapté (ex: *Voice Servers* ou *Discord Bots*).
4. Cliquez sur **Import Egg** et sélectionnez le fichier JSON téléchargé.
5. Associez l'Egg aux images Docker configurées et sauvegardez.

## ⚙️ Configuration du Serveur

Lors de la création ou de la configuration de votre instance de bot, les variables suivantes sont disponibles :

| Variable | Variable d'Environnement | Valeur par défaut | Description |
| :--- | :--- | :--- | :--- |
| **Fichier Principal du Bot** | `BOT_JS_FILE` | `index.js` | Le nom de votre fichier de démarrage (ex: `index.js`, `bot.js`, `main.js`). |
| **Paquets NPM Additionnels** | `NPM_PACKAGES` | *Vide* | Permet d'installer des paquets globaux spécifiques si nécessaire au démarrage. |

## 🛠️ Processus de Démarrage (Startup)

Au lancement, le conteneur exécute la logique suivante :
1. Vérification de la présence d'un fichier `package.json`.
2. Si présent, exécution automatique de `npm install` pour s'assurer que toutes les dépendances de votre bot sont à jour.
3. Lancement du bot via la commande : `node <Fichier_Principal>`.

---
👤 **Auteur :** [contact@sonorya.be](mailto:contact@sonorya.be)  
⚙️ **Généré pour :** Pterodactyl Panel (Format `PTDL_v2`)