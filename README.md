# 🖥️ Outil de Reconnaissance des Caractéristiques Machine — Local & Réseau

Projet universitaire — Systèmes d’Exploitation  
Année universitaire : 2024/2025  

---

## 📌 Description

Ce projet consiste à développer une solution capable de :

- Identifier **les caractéristiques d'une machine** (OS, CPU, RAM, batterie, périphériques) en **local**.
- Scanner et détecter ces mêmes informations à **distance** via une communication client-serveur utilisant des **sockets TCP**.

---

## ⚙️ Fonctionnalités

- 📡 **Reconnaissance locale**
  - Système d'exploitation.
  - Modèle et fréquence du processeur.
  - Mémoire vive (RAM).
  - Périphériques connectés.
  - État de la batterie.

- 🌐 **Reconnaissance à distance**
  - Scan réseau pour détecter la machine cible.
  - Connexion TCP sécurisée (port par défaut : `12345`).
  - Transmission des informations système.
  - Affichage structuré des données reçues.

- 🔄 **Automatisation**
  - Création automatique d'une **tâche planifiée** au démarrage :
    - `Task Scheduler` sous Windows.
    - `cron` sous Linux.
    - `launchd` sous MacOS.

---

## 🏗️ Architecture Technique

| Élément                          | Technologies utilisées                |
|----------------------------------|---------------------------------------|
| Communication réseau            | `socket` (TCP)                        |
| Identification système          | `platform`, `psutil`                  |
| Gestion de la mémoire et CPU     | `psutil`                              |
| Détection des périphériques      | `psutil`                              |
| Automatisation du démarrage      | Task Scheduler / Cron / Launchd       |

---

## ⚠️ Limitations

- ⏳ **Latence lors de la récupération des infos CPU**  
  (due à la profondeur des interrogations matérielles par `psutil`).

- 🔐 **Absence d'authentification / chiffrement**  
  Ce point reste une limite de sécurité sur réseau ouvert.

- 🧱 **Dépendances réseau**  
  La reconnaissance distante suppose que :
  - Le port soit ouvert (`12345` par défaut).
  - Aucune règle de pare-feu ne bloque les échanges.

---

## 🚀 Améliorations possibles

- Intégration d'un **chiffrement SSL/TLS** pour sécuriser les échanges.
- Mise en place d'un **système d'authentification**.
- Ajout d'un **système de logs**.
- Optimisation de la gestion des requêtes CPU.

---

## 🏁 Conclusion

Ce projet constitue une solution fiable et efficace pour collecter des informations système, en local ou à distance, dans un environnement réseau. Il peut être utilisé pour la surveillance, l’audit ou la gestion automatisée des machines, et peut être enrichi pour répondre à des contraintes de sécurité plus strictes.

---

## 💼 Licence

Projet réalisé dans un cadre pédagogique, librement réutilisable et modifiable sous une licence open-source à définir.
