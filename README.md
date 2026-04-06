# Source2Onto - Collaborative Ontology Engineering Tool

Source2Onto is a collaborative web platform designed for ontology engineering derived from source code. It allows multiple users to work simultaneously on term extraction, class modeling, and axiom definition, all while communicating in real-time.

## Key Features

- **Real-Time Collaborative Editor**: Simultaneous document editing with visible cursors for other participants (powered by CodeMirror and Socket.io).
- **Ontology Extraction**: Configuration for multiple languages (Java, PHP, JavaScript) and models for the automatic extraction of concepts, data properties, and object properties.
- **Project Management**: Creation of dedicated projects, collaborator invitations, and progress tracking.
- **Integrated Chat**: Instant messaging to facilitate communication between project members.
- **Dashboard and Metrics**: Visualization of project statistics (number of classes, properties, individuals, axioms, etc.).
- **Multi-format Export**: Ability to export results in TXT, OWL, and RDF formats.

## Tech Stack

- **Backend**: Node.js with the Express framework.
- **Database**: RethinkDB (chosen for its real-time push capabilities).
- **Real-Time**: Socket.io for editor and chat synchronization.
- **Frontend**: EJS (template engine), jQuery, Bootstrap 4, CodeMirror (code editor).
- **Dependency Management**: NPM for the backend and Bower for the frontend.

## Project Structure

```text
├── server.js                # Entry point for HTTP and Socket.io server
├── src/
│   ├── app.js               # Express application configuration and routes
│   ├── controller/          # Business logic (Projects, Extraction, Account, etc.)
│   ├── repository/          # Data access (RethinkDB)
│   ├── routes/              # Endpoint definitions (API and Views)
│   ├── io/                  # Socket.io event handling (Chat, Extraction)
│   ├── middleware/          # Authentication, Flash handling, DB connection
│   ├── views/               # EJS templates (User Interface)
│   └── public/              # Static assets (CSS, JS, Images)
├── bower_components/        # Frontend dependencies (CodeMirror, jQuery)
└── package.json             # Backend dependencies
```

## Installation

### Prerequisites

1.  **Node.js** installed on your machine.
2.  **RethinkDB** installed and running (default port: 28015).

### Étapes

1.  Clone the repository :
    ```bash
    git clone <url-du-depot>
    cd source2onto
    ```

2.  Install backend dependencies :
    ```bash
    npm install
    ```

3.  Install frontend dependencies (if necessary, via bower) :
    ```bash
    bower install
    ```

4.  Ensure RethinkDB is running. Upon the first launch, the application will automatically create the necessary tables (`users`, `edit`, `projet`, `chat`, `associer`) in the `test` database.

## Usage

To start the application :
```bash
npm start
```
The application will be accessible at `http://localhost:3000`.

## Authors
Project developed as a collaborative ontological engineering tool.
