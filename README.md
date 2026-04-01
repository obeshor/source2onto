# Source2Onto - Collaborative Ontology Engineering Tool

Source2Onto est une plateforme collaborative web permettant l'ingénierie d'ontologies à partir de codes sources. Elle permet à plusieurs utilisateurs de travailler simultanément sur l'extraction de termes, la modélisation de classes et d'axiomes, tout en communiquant en temps réel.

## Fonctionnalités Principales

- **Éditeur Collaboratif en Temps Réel** : Modification simultanée de documents avec visualisation des curseurs des autres participants (via CodeMirror et Socket.io).
- **Extraction d'Ontologies** : Configuration des langages (Java, PHP, JavaScript) et des modèles pour l'extraction automatique de concepts, propriétés de données et propriétés d'objets.
- **Gestion de Projets** : Création de projets dédiés, invitation de collaborateurs et suivi de l'avancement.
- **Chat Intégré** : Messagerie instantanée pour faciliter la collaboration entre les membres d'un projet.
- **Tableau de Bord et Métriques** : Visualisation des statistiques du projet (nombre de classes, propriétés, individus, axiomes, etc.).
- **Exportation Multi-format** : Possibilité d'exporter les résultats aux formats TXT, OWL et RDF.

## Technologies Utilisées

- **Backend** : Node.js avec le framework Express.
- **Base de données** : RethinkDB (choisie pour ses capacités de push en temps réel).
- **Temps Réel** : Socket.io pour la synchronisation de l'éditeur et du chat.
- **Frontend** : EJS (moteur de templates), jQuery, Bootstrap 4, CodeMirror (éditeur de code).
- **Gestion de dépendances** : NPM pour le backend et Bower pour le frontend.

## Structure du Projet

```text
├── server.js               # Point d'entrée du serveur HTTP et Socket.io
├── src/
│   ├── app.js              # Configuration de l'application Express et des routes
│   ├── controller/         # Logique métier (Projets, Extraction, Compte, etc.)
│   ├── repository/         # Accès aux données (RethinkDB)
│   ├── routes/             # Définition des points d'accès (API et Vues)
│   ├── io/                 # Gestion des événements Socket.io (Chat, Extraction)
│   ├── middleware/         # Authentification, gestion Flash, connexion DB
│   ├── views/              # Templates EJS (Interface utilisateur)
│   └── public/             # Assets statiques (CSS, JS, Images)
├── bower_components/       # Dépendances frontend (CodeMirror, jQuery)
└── package.json            # Dépendances backend
```

## Installation

### Prérequis

1.  **Node.js** installé sur votre machine.
2.  **RethinkDB** installé et en cours d'exécution (port par défaut : 28015).

### Étapes

1.  Clonez le dépôt :
    ```bash
    git clone <url-du-depot>
    cd source2onto
    ```

2.  Installez les dépendances backend :
    ```bash
    npm install
    ```

3.  Installez les dépendances frontend (si nécessaire, via bower) :
    ```bash
    bower install
    ```

4.  Assurez-vous que RethinkDB est lancé. Au premier démarrage, l'application créera automatiquement les tables nécessaires (`users`, `edit`, `projet`, `chat`, `associer`) dans la base de données `test`.

## Lancement

Pour démarrer l'application :
```bash
npm start
```
L'application sera accessible sur `http://localhost:3000`.

## Auteurs
Projet développé dans le cadre d'un outil d'ingénierie ontologique collaborative.
