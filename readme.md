# 🚀 GoFuzz for Android

[![Go Version](https://img.shields.io/badge/Go-1.22.0-blue.svg)](https://go.dev/)
[![Platform](https://img.shields.io/badge/Platform-Android-green.svg)](https://www.android.com/)
[![License](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

**GoFuzz** est un outil de test d'intrusion (fuzzer) haute performance écrit en Go. Il est conçu pour s'exécuter nativement sur **Android** afin de scanner des applications web, des APIs et des serveurs HTTP directement depuis un terminal mobile.

---

## 🧐 À propos du projet

Le **fuzzing web** est une technique de test de sécurité consistant à envoyer des volumes massifs de données variables à une application pour identifier :
* 📂 Des répertoires ou fichiers cachés (ex: `.env`, `/admin`, `/backup`).
* 🧪 Des vulnérabilités d'injection (XSS, SQLi).
* ⚠️ Des erreurs de configuration serveur (erreurs 500, fuites de données).



Grâce à la puissance du langage Go, ce projet transforme votre smartphone en une véritable station de scan capable de gérer des centaines de requêtes simultanées.

## ✨ Caractéristiques principales

* **🎯 Cible Web :** Optimisé pour le scan d'URLs, d'APIs REST et de formulaires.
* **📱 Nativement Android :** Compilé en binaires ELF statiques. Fonctionne sans Python, Java ou dépendances externes.
* **⚡ Performance Go :** Utilise les *goroutines* pour un fuzzing asynchrone ultra-rapide sans surcharger le processeur du téléphone.
* **🏗 Multi-Architecture :**
    | Architecture | Cible | Binaire |
    | :--- | :--- | :--- |
    | **ARM64** | Smartphones récents | `gofuzz-arm64-v8a` |
    | **ARMv7** | Anciens appareils | `gofuzz-armeabi-v7a` |
    | **x86_64** | Émulateurs PC | `gofuzz-x86_64` |

---

## 🛠 Installation & Setup

### 1. Téléchargement
Récupérez le binaire correspondant à votre architecture dans l'onglet [Releases](../../releases) de ce dépôt.

### 2. Déploiement via ADB
Connectez votre téléphone en mode Debug USB et utilisez les commandes suivantes :

```bash
# Envoyer le binaire sur le téléphone
adb push gofuzz-arm64-v8a /data/local/tmp/gofuzz

# Accéder au shell Android
adb shell



## 📱 Installation via Termux

Si vous n'utilisez pas ADB, vous pouvez installer et utiliser l'outil directement sur votre téléphone via **Termux**.

### 1. Préparation de l'environnement
Ouvrez Termux et installez les outils nécessaires :
```bash
pkg update && pkg upgrade
pkg install wget
uname -m

# Téléchargement (exemple pour arm64-v8a)


Récupérez le binaire correspondant à votre architecture dans l'onglet [Releases](../../releases) .


---

## ✍️ À propos de l'auteur

Ce projet a été conçu et développé avec passion par **Jonathan L**.

Si vous appréciez cet outil ou si vous souhaitez contribuer à son amélioration, n'hésitez pas à :
* 🌟 Laisser une étoile (**Star**) sur le dépôt pour soutenir le projet.
* 🐛 Signaler des bugs ou proposer des fonctionnalités via les **Issues**.
* 📬 Me suivre sur GitHub pour découvrir mes prochains outils de sécurité.

---
chmod +x gofuzz
./gofuzz --help
