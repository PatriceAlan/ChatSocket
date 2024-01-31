# ChatSocket

Bienvenue dans ChatSocket, une application de chat qui repose sur une architecture robuste, offrant une expérience de communication fluide et réactive entre les utilisateurs. Cette application se compose de deux entités majeures : le serveur et les clients.

![Architecture](https://github.com/PatriceAlan/ChatSocket/blob/main/image.png?raw=true)

## Architecture

Le serveur agit en tant que pivot central, créant un point de connexion et gérant les demandes d'accès des clients. Chaque demande génère l'instanciation d'un socket de communication propre au client, conservé méticuleusement dans une liste. Simultanément, un thread dédié est créé pour chaque client, orchestrant la réception et la transmission des messages. Du côté client, l'établissement de la connexion requiert l'acheminement du pseudonyme au serveur, offrant ainsi l'accès au salon de discussion partagé. Une interface graphique sophistiquée permet aux utilisateurs de saisir leur pseudonyme, de visualiser les messages échangés, et d'interagir de manière intuitive.

Cette architecture, finement conçue, garantit une communication transparente et agréable.

## Implémentation technique

Le programme de chat repose sur une structure bien définie, composée de plusieurs fichiers Java interconnectés pour assurer une communication harmonieuse entre le serveur et les clients. Les principaux fichiers orchestrant le fonctionnement de l'application sont les suivants:

### 1. ClientSwing.java
- **Définition:** La classe `ClientSwing` gère l'interface utilisateur du client de chat basé sur Swing. Elle crée une fenêtre graphique, facilite la connexion au serveur, l'envoi et la réception de messages.
- **Fonctionnalités:** Affichage de la fenêtre de chat, connexion au serveur, envoi de messages, réception de messages, déconnexion du serveur.
- **Utilité:** Fournir une interface utilisateur conviviale pour le client, gérant la communication avec le serveur de manière transparente.

### 2. ThreadClientSwing.java
- **Définition:** La classe `ThreadClientSwing` définit un thread dédié à la gestion des messages du serveur. Elle lit les messages du serveur et les affiche dans la fenêtre de chat du client.
- **Fonctionnalités:** Lecture des messages du serveur, affichage des messages dans la fenêtre de chat.
- **Utilité:** Permettre au client de recevoir les messages du serveur en temps réel, assurant ainsi la mise à jour dynamique de l'interface utilisateur.

### 3. ServerSwing.java
- **Définition:** La classe `ServerSwing` est responsable de l'interface utilisateur du serveur de chat basé sur Swing. Elle gère les connexions des clients, envoie des messages à tous les clients connectés, et gère les déconnexions.
- **Fonctionnalités:** Affichage de la fenêtre de log du serveur, gestion des connexions des clients, envoi de messages à tous les clients, gestion des déconnexions.
- **Utilité:** Fournir une interface utilisateur pour le serveur, facilitant la gestion des connexions, des messages et des déconnexions des clients.

### 4. ThreadMessageSwing.java
- **Définition:** La classe `ThreadMessageSwing` représente un thread dédié à la gestion des messages d'un client. Elle lit les messages du client et les transmet au serveur pour affichage dans les logs.
- **Fonctionnalités:** Lecture des messages du client, affichage des messages dans le log du serveur, gestion de la déconnexion du client.
- **Utilité:** Gérer les messages spécifiques d'un client, assurant une déconnexion propre en fonction du message envoyé.

Ces classes forment une infrastructure solide qui garantit la cohérence et la fluidité des échanges au sein de l'application de chat. La collaboration entre ces fichiers constitue l'épine dorsale de l'implémentation technique de notre solution.