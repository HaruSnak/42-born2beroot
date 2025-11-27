<img src="readme/born2beroot.png" alt="born2beroot" width="900"/>

<div align="center">

# Born2BeRoot
### Setting Up Your First Server with Security and Best Practices

[![Contributors][contributors-shield]][contributors-url]
[![Forks][forks-shield]][forks-url]
[![Stargazers][stars-shield]][stars-url]
[![Issues][issues-shield]][issues-url]
[![LinkedIn][linkedin-shield]][linkedin-url]

</div>

---

## 🇬🇧 English

<details>
<summary><b>📖 Click to expand/collapse English version</b></summary>

### 📖 About

**Born2BeRoot** is a project at **42 School** that consists of setting up your first server by following specific rules. Since it is a matter of setting up a server, you will install the minimum of services. For this reason, a graphical interface is of no use here. It is therefore forbidden to install X.org or any other equivalent graphics server. Otherwise, your grade will be 0.

You must choose as an operating system either the latest stable version of Debian (no testing/unstable), or the latest stable version of Rocky. Debian is highly recommended if you are new to system administration. Setting up Rocky is quite complex. Therefore, you don’t have to set up KDump. However, SELinux must be running at startup and its configuration has to be adapted for the project’s needs. AppArmor for Debian must be running at startup too.

You must create at least 2 encrypted partitions using LVM. During the defense, you will be asked a few questions about the operating system you chose. For instance, you should know the differences between aptitude and apt, or what SELinux or AppArmor is. In short, understand what you use!

This project teaches:
- Server setup and configuration
- Partitioning with LVM and encryption
- Security hardening (firewall, SSH, sudo, password policies)
- System monitoring and scripting
- Linux system administration basics

### 🧠 Skills Learned

By completing the Born2BeRoot project, students develop essential skills in Linux system administration:

- **Operating System Installation**: Choosing and installing Debian or Rocky Linux with minimal services
- **Partitioning and Encryption**: Using LVM to create encrypted partitions for security
- **Security Configuration**: Setting up SELinux/AppArmor, firewalls (UFW/firewalld), SSH restrictions
- **User Management**: Creating users, groups, and implementing strong password policies
- **Sudo Configuration**: Configuring sudo with strict rules, logging, and restrictions
- **Scripting**: Writing a bash monitoring script to display system information
- **System Monitoring**: Understanding system resources, connections, and usage statistics
- **Cron Jobs**: Scheduling tasks with cron for automated monitoring
- **Firewall Management**: Configuring UFW or firewalld to secure the server
- **SSH Security**: Disabling root login, changing default ports, and secure access

### 📋 Table of Contents

- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [Project Structure](#project-structure)
- [Configuration](#configuration)
- [Monitoring Script](#monitoring-script)
- [Credits](#credits)

<a name="features"></a>

### ✨ Features

- **Minimal Server Setup** with no graphical interface
- **Encrypted LVM Partitions** for data security
- **Strong Password Policy** with expiration and complexity rules
- **Secure SSH Configuration** on port 4242 with root login disabled
- **Firewall Protection** using UFW (Debian) or firewalld (Rocky)
- **Sudo Hardening** with attempt limits, custom messages, and logging
- **System Monitoring Script** displaying comprehensive server information
- **Automated Monitoring** every 10 minutes via cron

<a name="installation"></a>

### 🚀 Installation

1. **Choose Operating System**: Install the latest stable Debian or Rocky Linux
2. **Partitioning**: Create at least 2 encrypted partitions using LVM
3. **Basic Setup**: Configure hostname (yourlogin42), users, and groups
4. **Security Configuration**: Set up password policy, sudo, SSH, and firewall
5. **Monitoring**: Create and configure the monitoring.sh script

```bash
# Example partitioning (adjust sizes as needed)
# /boot: 500MB
# /: 10GB (encrypted LVM)
# /home: remaining space (encrypted LVM)
# swap: appropriate size
```

<a name="usage"></a>

### 💻 Usage

After setup, your server will be running with SSH on port 4242.

Connect via SSH:
```bash
ssh youruser@server_ip -p 4242
```

The monitoring script runs automatically every 10 minutes and displays system information on all terminals.

To run manually:
```bash
sudo ./monitoring.sh
```

<a name="project-structure"></a>

### 📂 Project Structure

```
Born2BeRoot/
├── monitoring.sh              # System monitoring script
├── README.md                  # This file
└── readme/                    # Assets folder
    └── born2beroot.png
```

<a name="configuration"></a>

### 🔧 Configuration

#### Password Policy
- Password expires every 30 days
- Minimum 2 days before change allowed
- Warning 7 days before expiration
- Minimum 10 characters with uppercase, lowercase, number
- No more than 3 consecutive identical characters
- Cannot contain username
- At least 7 different characters from previous password

#### Sudo Configuration
- 3 attempts max for wrong password
- Custom error message
- Log all actions to /var/log/sudo/
- TTY mode enabled
- Restricted paths: /usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/snap/bin

#### SSH
- Port 4242
- Root login disabled
- Password authentication enabled

#### Firewall
- Only port 4242 open
- UFW for Debian, firewalld for Rocky

<a name="monitoring-script"></a>

### 📊 Monitoring Script

The `monitoring.sh` script displays:
- OS architecture and kernel version
- Number of physical and virtual processors
- RAM usage and percentage
- Disk usage and percentage
- CPU load percentage
- Last reboot date/time
- LVM status
- Active TCP connections
- Logged-in users
- IPv4 address and MAC address
- Sudo command count

Example output:
```
#Architecture: Linux wil 4.19.0-16-amd64 #1 SMP Debian 4.19.181-1 (2021-03-19) x86_64 GNU/Linux
#CPU physical : 1
#vCPU : 1
#Memory Usage: 74/987MB (7.50%)
#Disk Usage: 1009/2Gb (49%)
#CPU load: 6.7%
#Last boot: 2021-04-25 14:45
#LVM use: yes
#Connections TCP : 1 ESTABLISHED
#User log: 1
#Network: IP 10.0.2.15 (08:00:27:51:9b:a5)
#Sudo : 42 cmd
```

### 👨‍🎓 Note
<p align="left">
    <img src="https://image.noelshack.com/fichiers/2024/11/2/1710273269-100.png"
         alt="100/100" width="180" height="184">
</p>

<a name="credits"></a>

### 📖 Credits

Below you will find the links used for this project:

- [Pasqualerossi the BOSS | Tuto Github Born2BeRoot](https://github.com/pasqualerossi/Born2BeRoot-Guide)

</details>

---

## 🇫🇷 Français

<details>
<summary><b>📖 Cliquez pour développer/réduire la version française</b></summary>

### 📖 À propos

**Born2BeRoot** est un projet de l'école **42** qui consiste à configurer votre premier serveur en suivant des règles spécifiques. Puisqu'il s'agit de configurer un serveur, vous installerez le minimum de services. Pour cette raison, une interface graphique n'est d'aucune utilité ici. Il est donc interdit d'installer X.org ou tout autre serveur graphique équivalent. Sinon, votre note sera de 0.

Vous devez choisir comme système d'exploitation soit la dernière version stable de Debian (pas testing/unstable), soit la dernière version stable de Rocky. Debian est fortement recommandé si vous êtes nouveau en administration système. La configuration de Rocky est assez complexe. Par conséquent, vous n'avez pas à configurer KDump. Cependant, SELinux doit être en cours d'exécution au démarrage et sa configuration doit être adaptée aux besoins du projet. AppArmor pour Debian doit également être en cours d'exécution au démarrage.

Vous devez créer au moins 2 partitions chiffrées en utilisant LVM. Pendant la défense, on vous posera quelques questions sur le système d'exploitation que vous avez choisi. Par exemple, vous devez connaître les différences entre aptitude et apt, ou ce qu'est SELinux ou AppArmor. En bref, comprenez ce que vous utilisez !

Ce projet enseigne :
- Configuration et installation de serveur
- Partitionnement avec LVM et chiffrement
- Durcissement de la sécurité (pare-feu, SSH, sudo, politiques de mot de passe)
- Surveillance système et scripting
- Bases de l'administration système Linux

### 🧠 Compétences acquises

En complétant le projet Born2BeRoot, les étudiants développent des compétences essentielles en administration système Linux :

- **Installation du système d'exploitation** : Choisir et installer Debian ou Rocky Linux avec des services minimaux
- **Partitionnement et chiffrement** : Utiliser LVM pour créer des partitions chiffrées pour la sécurité
- **Configuration de sécurité** : Configurer SELinux/AppArmor, pare-feu (UFW/firewalld), restrictions SSH
- **Gestion des utilisateurs** : Créer des utilisateurs, groupes, et implémenter des politiques de mot de passe fortes
- **Configuration de sudo** : Configurer sudo avec des règles strictes, journalisation, et restrictions
- **Scripting** : Écrire un script bash de surveillance pour afficher les informations système
- **Surveillance système** : Comprendre les ressources système, connexions, et statistiques d'utilisation
- **Tâches cron** : Planifier des tâches avec cron pour une surveillance automatisée
- **Gestion du pare-feu** : Configurer UFW ou firewalld pour sécuriser le serveur
- **Sécurité SSH** : Désactiver la connexion root, changer le port par défaut, et accès sécurisé

### 📋 Table des matières

- [Caractéristiques](#caractéristiques)
- [Installation](#installation-1)
- [Utilisation](#utilisation)
- [Structure du projet](#structure-du-projet)
- [Configuration](#configuration-1)
- [Script de surveillance](#script-de-surveillance)
- [Crédits](#crédits-1)

<a name="caractéristiques"></a>

### ✨ Caractéristiques

- **Configuration de serveur minimal** sans interface graphique
- **Partitions LVM chiffrées** pour la sécurité des données
- **Politique de mot de passe forte** avec expiration et règles de complexité
- **Configuration SSH sécurisée** sur le port 4242 avec connexion root désactivée
- **Protection pare-feu** utilisant UFW (Debian) ou firewalld (Rocky)
- **Durcissement de sudo** avec limites de tentatives, messages personnalisés, et journalisation
- **Script de surveillance système** affichant des informations complètes sur le serveur
- **Surveillance automatisée** toutes les 10 minutes via cron

<a name="installation-1"></a>

### 🚀 Installation

1. **Choisir le système d'exploitation** : Installer la dernière version stable de Debian ou Rocky Linux
2. **Partitionnement** : Créer au moins 2 partitions chiffrées en utilisant LVM
3. **Configuration de base** : Configurer le nom d'hôte (votrelogin42), utilisateurs, et groupes
4. **Configuration de sécurité** : Configurer la politique de mot de passe, sudo, SSH, et pare-feu
5. **Surveillance** : Créer et configurer le script monitoring.sh

```bash
# Exemple de partitionnement (ajuster les tailles selon les besoins)
# /boot: 500MB
# /: 10GB (LVM chiffré)
# /home: espace restant (LVM chiffré)
# swap: taille appropriée
```

<a name="utilisation"></a>

### 💻 Utilisation

Après la configuration, votre serveur fonctionnera avec SSH sur le port 4242.

Connexion via SSH :
```bash
ssh votrenom@ip_serveur -p 4242
```

Le script de surveillance s'exécute automatiquement toutes les 10 minutes et affiche les informations système sur tous les terminaux.

Pour exécuter manuellement :
```bash
sudo ./monitoring.sh
```

<a name="structure-du-projet"></a>

### 📂 Structure du projet

```
Born2BeRoot/
├── monitoring.sh              # Script de surveillance système
├── README.md                  # Ce fichier
└── readme/                    # Dossier des ressources
    └── born2beroot.png
```

<a name="configuration-1"></a>

### 🔧 Configuration

#### Politique de mot de passe
- Le mot de passe expire tous les 30 jours
- Minimum 2 jours avant changement autorisé
- Avertissement 7 jours avant expiration
- Minimum 10 caractères avec majuscule, minuscule, chiffre
- Pas plus de 3 caractères identiques consécutifs
- Ne peut pas contenir le nom d'utilisateur
- Au moins 7 caractères différents du mot de passe précédent

#### Configuration de sudo
- 3 tentatives max pour mot de passe erroné
- Message d'erreur personnalisé
- Journaliser toutes les actions dans /var/log/sudo/
- Mode TTY activé
- Chemins restreints : /usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/snap/bin

#### SSH
- Port 4242
- Connexion root désactivée
- Authentification par mot de passe activée

#### Pare-feu
- Seulement le port 4242 ouvert
- UFW pour Debian, firewalld pour Rocky

<a name="script-de-surveillance"></a>

### 📊 Script de surveillance

Le script `monitoring.sh` affiche :
- Architecture OS et version du noyau
- Nombre de processeurs physiques et virtuels
- Utilisation RAM et pourcentage
- Utilisation disque et pourcentage
- Charge CPU en pourcentage
- Date/heure du dernier redémarrage
- Statut LVM
- Connexions TCP actives
- Utilisateurs connectés
- Adresse IPv4 et adresse MAC
- Nombre de commandes sudo

Exemple de sortie :
```
#Architecture: Linux wil 4.19.0-16-amd64 #1 SMP Debian 4.19.181-1 (2021-03-19) x86_64 GNU/Linux
#CPU physical : 1
#vCPU : 1
#Memory Usage: 74/987MB (7.50%)
#Disk Usage: 1009/2Gb (49%)
#CPU load: 6.7%
#Last boot: 2021-04-25 14:45
#LVM use: yes
#Connections TCP : 1 ESTABLISHED
#User log: 1
#Network: IP 10.0.2.15 (08:00:27:51:9b:a5)
#Sudo : 42 cmd
```

### 👨‍🎓 Note
<p align="left">
    <img src="https://image.noelshack.com/fichiers/2024/11/2/1710273269-100.png"
         alt="100/100" width="180" height="184">
</p>

<a name="crédits-1"></a>

### 📖 Crédits

Vous trouverez ci-dessous les liens utilisés pour ce projet :

- [Pasqualerossi the BOSS | Tuto Github Born2BeRoot](https://github.com/pasqualerossi/Born2BeRoot-Guide)

</details>

---

[contributors-shield]: https://img.shields.io/github/contributors/HaruSnak/42-born2beroot.svg?style=for-the-badge
[contributors-url]: https://github.com/HaruSnak/42-born2beroot/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/HaruSnak/42-born2beroot.svg?style=for-the-badge
[forks-url]: https://github.com/HaruSnak/42-born2beroot/network/members
[stars-shield]: https://img.shields.io/github/stars/HaruSnak/42-born2beroot.svg?style=for-the-badge
[stars-url]: https://github.com/HaruSnak/42-born2beroot/stargazers
[issues-shield]: https://img.shields.io/github/issues/HaruSnak/42-born2beroot.svg?style=for-the-badge
[issues-url]: https://github.com/HaruSnak/42-born2beroot/issues
[linkedin-shield]: https://img.shields.io/badge/-LinkedIn-black.svg?style=for-the-badge&logo=linkedin&colorB=555
[linkedin-url]: https://www.linkedin.com/in/shany-moreno-5a863b2aa

