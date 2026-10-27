# 🔍 Nmap & Tests de vulnérabilités — Tutoriel VPS

![License](https://img.shields.io/badge/licence-MIT-blue.svg)
![Usage](https://img.shields.io/badge/usage-%C3%A9ducatif%20%26%20l%C3%A9gal-brightgreen.svg)
![Shell](https://img.shields.io/badge/shell-bash-informational.svg)

Guide complet pour installer **Nmap** sur un VPS Linux et effectuer des tests de
vulnérabilités basiques, dans un cadre **100 % légal et contrôlé**.

> ⚠️ **Avertissement légal**
>
> - Ce tutoriel est strictement destiné à un usage éthique et légal.
> - Ne scannez que des serveurs que vous possédez ou pour lesquels vous avez une
>   autorisation **explicite et écrite**.
> - Toute utilisation abusive engage votre seule et entière responsabilité, y
>   compris pénale.

## 📋 Sommaire

1. [Pré-requis VPS](#1-pré-requis-vps)
2. [Installation de Nmap](#2-installation-de-nmap)
3. [Commandes de scan basiques](#3-commandes-de-scan-basiques)
4. [Identification des vulnérabilités simples](#4-identification-des-vulnérabilités-simples)
5. [Bonnes pratiques](#5-bonnes-pratiques)
6. [Nettoyage & sécurité après tests](#6-nettoyage--sécurité-après-tests)
7. [Ressources complémentaires](#7-ressources-complémentaires)

---

## 1. Pré-requis VPS

- Système recommandé : Ubuntu 20.04/22.04 ou Debian 10/11
- Accès root, ou utilisateur avec droits `sudo`
- Connexion SSH active

## 2. Installation de Nmap

Connectez-vous à votre VPS via SSH, puis installez le paquet :

```bash
sudo apt update
sudo apt install -y nmap
```

Vérifiez l'installation :

```bash
nmap --version
```

## 3. Commandes de scan basiques

**Détecter les ports ouverts sur une IP ou un domaine**

```bash
nmap 192.168.1.10
nmap example.com
```

**Scan complet des ports TCP (1-65535)**

```bash
nmap -p- 192.168.1.10
```

**Scan avec détection des versions de service**

```bash
nmap -sV 192.168.1.10
```

**Scan agressif (plus complet, avec détection de l'OS)**

```bash
nmap -A 192.168.1.10
```

## 4. Identification des vulnérabilités simples

Nmap permet aussi de lancer des scripts NSE (*Nmap Scripting Engine*) pour
repérer certaines vulnérabilités connues.

**Scripts de vulnérabilités de base**

```bash
nmap --script vuln 192.168.1.10
```

**Recherche de failles SSH courantes**

```bash
nmap --script ssh-auth-methods,sshv1 192.168.1.10
```

## 5. Bonnes pratiques

- Ne scannez que vos propres machines, ou celles pour lesquelles vous avez une
  autorisation écrite.
- Commencez par un scan simple, puis augmentez la complexité progressivement.
- Analysez les résultats en détail et vérifiez les services exposés.
- Ne lancez pas de scans agressifs sur des serveurs en production sans
  validation préalable.
- Réservez les outils complémentaires (Wireshark, Metasploit…) à un
  environnement de lab isolé.

## 6. Nettoyage & sécurité après tests

- Fermez les services non nécessaires.
- Mettez à jour le système et les logiciels.
- Configurez un pare-feu (UFW, nftables) pour limiter les accès.
- Surveillez les logs pour détecter les accès suspects.

## 7. Ressources complémentaires

- [Nmap Reference Guide](https://nmap.org/book/man.html)
- [NSE — Nmap Scripting Engine](https://nmap.org/book/nse.html)
- [linuxsecurity.expert — tutoriels](https://linuxsecurity.expert/tutorials/)

---

## 📢 Disclaimer

Ce projet est fourni à but **éducatif uniquement**. L'auteur ne peut être tenu
responsable en cas d'usage illégal ou non autorisé de ce tutoriel.

## 📄 Licence

Distribué sous licence [MIT](LICENSE) — libre à vous d'adapter et de partager
ce tutoriel dans un cadre légal.

---

<p align="center">Bonne exploration sécurisée ! 🔐</p>
