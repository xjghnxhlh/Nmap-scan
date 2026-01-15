# 🔍 Nmap & Tests de Vulnérabilités — Tutoriel VPS (Usage légal uniquement)

Ce dépôt contient un guide complet pour installer Nmap sur un VPS Linux,
et effectuer des tests de vulnérabilités basiques dans un cadre 100% légal et contrôlé.

---

## ⚠️ Avertissement légal

- Ce tutoriel est strictement destiné à un usage éthique et légal.
- Scanner uniquement des serveurs que vous possédez ou pour lesquels vous avez une autorisation explicite.
- Toute utilisation abusive engage votre responsabilité pénale.

---

## 📋 Sommaire

1. Pré-requis VPS  
2. Installation de Nmap  
3. Commandes de scans basiques  
4. Identification des vulnérabilités simples  
5. Bonnes pratiques  
6. Nettoyage et sécurité  
7. Ressources complémentaires  

---

## 1️⃣ Pré-requis VPS

- Système recommandé : Ubuntu 20.04/22.04 ou Debian 10/11  
- Accès root ou utilisateur avec droits sudo  
- Connexion SSH active  

---

## 2️⃣ Installation de Nmap

Se connecter à votre VPS via SSH, puis lancer :

sudo apt update  
sudo apt install -y nmap

Vérifier l’installation :

nmap --version

---

## 3️⃣ Commandes de scans basiques

### Scanner une IP ou un domaine pour détecter les ports ouverts

nmap 192.168.1.10

ou

nmap example.com

### Scan complet des ports TCP (1-65535)

nmap -p- 192.168.1.10

### Scan avec détection des versions des services

nmap -sV 192.168.1.10

### Scan agressif (plus complet, avec détection OS)

nmap -A 192.168.1.10

---

## 4️⃣ Identification des vulnérabilités simples

Nmap permet aussi de lancer des scripts NSE (Nmap Scripting Engine) pour détecter vulnérabilités :

### Scanner avec scripts vulnérabilités basiques

nmap --script vuln 192.168.1.10

### Scanner pour trouver des failles SSH courantes

nmap --script ssh-auth-methods,sshv1 192.168.1.10

---

## 5️⃣ Bonnes pratiques

- Toujours scanner uniquement vos machines ou celles pour lesquelles vous avez l’autorisation  
- Commencer par un scan simple, augmenter la complexité progressivement  
- Analyser les résultats en détail, vérifier les services exposés  
- Ne pas lancer de scans agressifs sur des serveurs en production sans validation  
- Utiliser des outils complémentaires (Wireshark, Metasploit) uniquement dans un lab  

---

## 6️⃣ Nettoyage & sécurité après tests

- Fermer les services non nécessaires  
- Mettre à jour le système et les logiciels  
- Configurer un firewall (UFW, nftables) pour limiter les accès  
- Surveiller les logs pour détecter des accès suspects  

---

## 7️⃣ Ressources complémentaires

- https://nmap.org/book/man.html  
- https://nmap.org/book/nse.html  
- https://linuxsecurity.expert/tutorials/  

---

## 📢 Disclaimer

Ce projet est à but éducatif uniquement.  
L’auteur ne peut être tenu responsable en cas d’usage illégal.  

---

## Licence

MIT License - Libre à vous d’adapter et partager ce tutoriel dans un cadre légal.

---

Bonne exploration sécurisée ! 🔐
