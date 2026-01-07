📊 Projet Cloud Zabbix – Supervision & Monitoring

🧠 Présentation du projet

Ce projet consiste à mettre en place une solution de supervision centralisée avec Zabbix dans un environnement cloud / virtualisé.
L’objectif est de surveiller en temps réel les serveurs et services, détecter rapidement les incidents et visualiser les performances du système.

La solution est conçue pour être scalable, fiable et adaptée aux infrastructures cloud.

⸻

🎯 Objectifs du projet
	•	Déployer un serveur de supervision Zabbix
	•	Superviser des machines virtuelles / serveurs Linux
	•	Collecter les métriques :
	•	CPU
	•	Mémoire (RAM)
	•	Disque
	•	Réseau
	•	Configurer des alertes et des déclencheurs (triggers)
	•	Fournir une interface Web de monitoring
	•	Utiliser une architecture cloud basée sur Docker

⸻

🏗️ Architecture générale

L’architecture du projet est composée des éléments suivants :
	•	Zabbix Server : collecte et traite les données de supervision
	•	Zabbix Agent 2 : installé sur les machines à superviser
	•	Base de données MySQL : stockage des données
	•	Interface Web Zabbix (incluse dans l’image officielle Zabbix)
	•	Docker & Docker Compose pour le déploiement
<img width="1280" height="853" alt="image" src="https://github.com/user-attachments/assets/1a02d8a2-1f87-4f2c-83d8-cd2b9f5add49" />



⸻
II:Etapes De realisation 

1. Conception de l’architecture

Une architecture cloud simple et efficace a été définie :
	•	Un serveur central Zabbix hébergé dans un environnement virtualisé
	•	Des agents Zabbix installés sur chaque machine supervisée
	•	Une base de données MySQL pour le stockage des données
	•	Une interface Web pour l’administration et la visualisation

L’architecture a été pensée pour être modulaire et évolutive.

⸻

2. Préparation de l’environnement

Avant le déploiement, l’environnement a été préparé :
	•	Installation du système Linux (Ubuntu Server)
	•	Installation de Docker et Docker Compose
	•	Vérification de la connectivité réseau entre les machines
	•	Configuration des ports nécessaires à la supervision

⸻

3. Déploiement de la plateforme Zabbix

Le déploiement de Zabbix a été réalisé à l’aide de Docker Compose :
	•	Lancement des conteneurs Zabbix Server, Web et MySQL
	•	Vérification du bon fonctionnement des services
	•	Accès à l’interface Web Zabbix via le navigateur

Cette approche permet un déploiement rapide et reproductible.

⸻

4. Installation et configuration des agents

Sur chaque machine à superviser :
	•	Installation de Zabbix Agent 2
	•	Configuration de l’adresse du serveur Zabbix
	•	Définition du nom d’hôte
	•	Démarrage et activation du service agent

Les machines sont ensuite ajoutées dans l’interface Zabbix.

⸻

5.Configuration de la supervision

Une fois les hôtes ajoutés :
	•	Association de templates Zabbix adaptés
	•	Activation de la collecte des métriques
	•	Définition de triggers pour les seuils critiques
	•	Configuration des graphiques et dashboards

⸻

6. Tests et validation

Des tests ont été réalisés pour valider la solution :
	•	Test de communication Agent ↔ Server
	•	Simulation de surcharge CPU / mémoire
	•	Vérification de la génération des alertes
	•	Contrôle de l’affichage des données en temps réel
----


🛠️ Technologies utilisées
	•	Zabbix (Server & Agent 2)
	•	Docker
	•	Docker Compose
	•	MySQL
	•	Linux (Ubuntu Server)


⸻

🚀 Déploiement du projet

1️⃣ Prérequis
	•	Linux (Ubuntu recommandé)
	•	Docker installé
	•	Docker Compose installé
	•	Accès root ou sudo

⸻

2️⃣ Lancement des conteneurs Zabbix

Dans le dossier du projet :

docker-compose up -d

Vérification des conteneurs :

docker ps


⸻

3️⃣ Accès à l’interface Web Zabbix

Ouvrir un navigateur et accéder à :

http://IP_DU_SERVEUR:8080

Identifiants par défaut :
	•	Utilisateur : Admin
	•	Mot de passe : zabbix

⸻

🖥️ Configuration des agents Zabbix

Sur chaque machine à superviser :

Installation de l’agent

sudo apt update
sudo apt install zabbix-agent2 -y

Configuration principale

Fichier :

/etc/zabbix/zabbix_agent2.conf

Paramètres importants :

Server=IP_ZABBIX_SERVER
ServerActive=IP_ZABBIX_SERVER
Hostname=VM-CLIENT-01

Redémarrage de l’agent :

sudo systemctl restart zabbix-agent2
sudo systemctl enable zabbix-agent2


⸻

🔐 Ports réseau utilisés

Service	Port	Description
Zabbix Server	10051	Collecte des données
Zabbix Agent	10050	Envoi des métriques
Interface Web	8080	Accès au monitoring


⸻

📈 Supervision & fonctionnalités
	•	Surveillance des ressources système
	•	Détection automatique des hôtes
	•	Tableaux de bord dynamiques
	•	Alertes en temps réel
	•	Historique et tendances des performances

⸻

🧪 Tests réalisés
	•	Test de connectivité Agent ↔ Server
	•	Surveillance CPU / RAM / Disque
	•	Génération d’alertes en cas de surcharge
	•	Visualisation des métriques en temps réel

⸻

🔒 Sécurité
	•	Accès contrôlé à l’interface Web
	•	Communication Agent ↔ Server limitée par IP
	•	Ports exposés strictement nécessaires

⸻

🧾 Conclusion

Ce projet démontre la mise en place d’une solution de supervision cloud complète avec Zabbix, permettant une gestion proactive des infrastructures.
Il constitue une base solide pour des environnements professionnels et académiques.

⸻

👤 Auteur
Abdelhakim Taha
Étudiant en ingénierie informatique
Projet académique – Supervision Cloud avec Zabbix
