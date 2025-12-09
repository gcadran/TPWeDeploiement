
# Déploiement Web – Angular & Node.js




 Auteur **Guilherm CADRAN**

---

## Objectif du projet

Déployer une application **Angular** (front) et **Node.js** (back) sur une machine virtuelle Ubuntu 20.04 à l’ISTIC, avec :

- Installation et configuration de Node.js, PostgreSQL, Nginx, Fail2ban, UFW
- Déploiement du backend (API RealWorld) et du frontend (build Angular prod)
- Configuration d’un reverse proxy Nginx
- Sécurisation de la VM
- Accès HTTP local via `/etc/hosts`

---

## Résumé du déploiement

1. **Création de la VM Ubuntu 20.04**
2. **Installation des dépendances** : Node.js, PostgreSQL, Nginx, Fail2ban, UFW
3. **Déploiement du backend Node.js** (API RealWorld)
4. **Migration Prisma** et création de la base `realworld`
5. **Déploiement du frontend Angular** (build de production)
6. **Configuration du reverse proxy Nginx**
7. **Tests des routes** :
	- `/` : Frontend Angular
	- `/api` : Backend Node.js
8. **Sécurisation** : activation de Fail2ban et UFW

---

## Difficultés rencontrées

### 1. Version d’Angular différente du TP
- Le TP demandait une ancienne version, le repo officiel était plus récent (fichiers déplacés, commandes différentes).

### 2. Connexion SSH obligatoire
- VM ISTIC : connexion uniquement par clé SSH (pas de mot de passe). Problème de clé mal configurée → recréation de la VM.

### 3. Mauvais choix d’image (Debian au lieu d’Ubuntu)
- Problèmes de paquets, MongoDB non installable, PostgreSQL à configurer manuellement. 

### 4. VM non accessible depuis Internet
- Impossible d’utiliser Let’s Encrypt (pas d’accès public). Site disponible uniquement en HTTP local.

---

## État final du projet

- [x] Front Angular déployé
- [x] API Node.js fonctionnelle
- [x] PostgreSQL configuré
- [x] Nginx opérationnel (reverse proxy + fichiers statiques)
- [x] Fail2ban + UFW activés
- [ ] HTTPS (Let’s Encrypt impossible)

---

## Sécurité

- **Fail2ban** : protection contre les tentatives de brute-force
- **UFW** : pare-feu activé, ports ouverts uniquement nécessaires

---

## Remarques

- Projet déployé et fonctionnel en local sur la VM ISTIC
- Non accessible publiquement (pas de HTTPS possible)

---

## Licence

Ce projet est réalisé dans le cadre du Master 1 IL – ISTIC Rennes.