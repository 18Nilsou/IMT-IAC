# IMT-IAC - Infrastructure as Code avec Ansible

> Nils Saadi INFRES 17 DL - IMT Mines Alès - 2025

## À propos

Ce dépôt contient l'ensemble des comptes-rendus des ateliers pratiques réalisés dans le cadre du cours **Infrastructure as Code (IaC)** à IMT Mines Alès. Les exercices portent sur l'apprentissage d'**Ansible**, un outil d'automatisation de la gestion de configuration et du déploiement d'infrastructures.

Chaque atelier est documenté avec :
- Les objectifs pédagogiques
- L'énoncé du challenge
- La solution détaillée avec les commandes exécutées
- Les observations et conclusions

## Structure du projet

```
IMT-IAC/
│
├── Installer-Ansible/
│   ├── Challenge-1.md          # Installation via dépôt officiel Ubuntu
│   ├── Challenge-2.md          # Installation via PPA tiers
│   └── Challenge-3.md          # Installation via PIP et Virtualenv
│
├── Authentification/
│   └── A-vous-de-jouer.md      # Configuration de l'authentification SSH
│
├── Configuration-de-base/
│   └── A-vous-de-jouer.md      # Configuration d'un projet Ansible
│
├── Idempotence/
│   └── A-vous-de-jouer.md      # Comprendre l'idempotence dans Ansible
│
└── README.md                    # Ce fichier
```

## Contenu des ateliers

### Installer-Ansible/

Trois méthodes d'installation d'Ansible sur différentes distributions Linux :

- **Challenge-1** : Installation via le dépôt officiel Ubuntu → `ansible 2.10.8`
- **Challenge-2** : Installation via PPA tiers → `ansible [core 2.17.14]`  
- **Challenge-3** : Installation via PIP et Virtualenv sur Rocky Linux → `ansible [core 2.15.13]`

**Compétences** : Gestion de paquets, environnements virtuels Python, comparaison des méthodes d'installation.

---

### Authentification/

Configuration de l'authentification SSH par clé pour Ansible sur un environnement avec 1 Control Host et 3 Target Hosts (Ubuntu 22.04).

**Points clés** :
- Configuration DNS locale (`/etc/hosts`)
- Génération et distribution de clés SSH (`ssh-keygen`, `ssh-copy-id`)
- Validation avec le module `ping` d'Ansible

**Compétences** : Sécurisation SSH, gestion de clés, authentification automatisée.

---

### Configuration-de-base/

Mise en place d'une configuration Ansible professionnelle complète.

**Éléments configurés** :
- Fichier `ansible.cfg` avec inventaire et journalisation
- Fichier d'inventaire `hosts` avec groupes et variables
- Élévation des privilèges avec `sudo`
- Tests de connectivité et de permissions

**Compétences** : Structuration de projet, inventaires, variables d'hôtes, gestion des privilèges.

---

### Idempotence/

Expérimentation du principe d'idempotence à travers l'installation/désinstallation de paquets et la manipulation de fichiers.

**Tests réalisés** :
- Modules idempotents : `package`, `copy`, `file` →  Pas de modification si l'état est déjà atteint
- Module non-idempotent : `command` →  Retourne toujours `CHANGED`

**Compétences** : Compréhension de l'idempotence, utilisation appropriée des modules Ansible, fiabilité des playbooks.

---

## 🎓 Concepts clés abordés

### Ansible
- Architecture Control Host / Target Hosts
- Modules et commandes ad-hoc
- Inventaires et groupes d'hôtes
- Variables et configuration
- Idempotence

### Administration système
- Gestion de paquets multi-distributions
- Configuration SSH avancée
- Élévation de privilèges avec sudo
- Journalisation système

### Infrastructure as Code (IaC)
- Déclaration de l'état souhaité
- Automatisation reproductible
- Gestion de configuration
- Versionning de l'infrastructure

### Bonnes pratiques
- Organisation des projets
- Sécurisation des accès
- Documentation des configurations
- Tests et validation

## 📖 Ressources

Les ateliers sont basés sur la formation :
- **Source** : [Formations Microlinux - Ansible par la pratique](https://formations.microlinux.fr/ansible/)
- **Auteur de la formation** : Nicolas Kovacs (Microlinux)

## 📝 Licence

Ce projet est un travail académique réalisé dans le cadre du cours IaC à IMT Mines Alès.

---

<div align="center">
  
**IMT-IAC** - Infrastructure as Code avec Ansible  
IMT Mines Alès - 2025

</div>
