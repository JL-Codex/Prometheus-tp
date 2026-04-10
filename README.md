Rapport de TP : Surveillance avec Prometheus et Grafana
1. Introduction

Ce projet consiste en la mise en place d'une pile de surveillance (monitoring) complète pour un serveur Linux. L'objectif est de collecter des métriques système en temps réel, de les stocker et de les visualiser via des tableaux de bord dynamiques.

Composants utilisés :

    Prometheus Server : Le cœur de l'architecture qui récupère et stocke les données.

    Node Exporter : Agent installé sur le serveur pour exposer les métriques matérielles (CPU, RAM, Disque).

    Grafana : Outil de visualisation pour transformer les données brutes en graphiques.

2. Architecture et Installation

En raison de l'utilisation de GitHub Codespaces, les services ont été lancés manuellement pour contourner l'absence de systemd.
Lancement des services

    Prometheus : Lancé sur le port 9090 avec la configuration personnalisée.

    Node Exporter : Lancé sur le port 9100 pour collecter les statistiques du nœud.

    Grafana Server : Lancé sur le port 3000 pour l'interface de visualisation.

    <img width="678" height="782" alt="prom server hosted" src="https://github.com/user-attachments/assets/61eca981-6d0e-40cd-94f8-75192add360f" />
    Preuve du serveur Prometheus prêt à recevoir des requêtes web.
    
    <img width="849" height="824" alt="node exporter hosted" src="https://github.com/user-attachments/assets/540f928e-be90-4bee-b645-e872c01cc3c1" />
    Preuve de Node Exporter écoutant sur le port 9100.

3. Configuration et Collecte de Données

Le fichier prometheus.yml a été configuré pour inclure Node Exporter comme cible de "scrape".
Vérification des Cibles (Targets)

Une fois la configuration appliquée, j'ai vérifié que Prometheus voyait bien les services comme actifs ("UP").

    <img width="1858" height="934" alt="prom targets" src="https://github.com/user-attachments/assets/4a283593-a6ef-4b7d-94b0-6112a7e93f95" />
    Capture d'écran montrant l'état "UP" pour Prometheus et Node_Exporter.

Interface de Requêtage

Prometheus permet d'utiliser le langage PromQL pour interroger les données avant leur visualisation.

    <img width="1868" height="902" alt="prom web main" src="https://github.com/user-attachments/assets/539f353d-5822-48fc-9b64-f0a88dfcb4a6" />
    Interface principale de Prometheus pour les requêtes PromQL.

4. Visualisation sous Grafana

Grafana a été connecté à Prometheus en tant que source de données.
Connexion à la Source de Données

    <img width="1522" height="136" alt="connection from graf to prom" src="https://github.com/user-attachments/assets/9ba4845a-08ab-48c9-9c0b-aa45dc5db999" />
    Confirmation de la connexion réussie entre Grafana et l'API Prometheus.

Tableau de Bord Final

j'ai importé le tableau de bord ID 14513 pour obtenir une vue d'ensemble du système Linux.

    <img width="1857" height="930" alt="after import" src="https://github.com/user-attachments/assets/cb23d285-d8b6-481c-82bc-8ce67208ab84" />
    Tableau de bord final affichant l'utilisation CPU, la charge système et la RAM.
