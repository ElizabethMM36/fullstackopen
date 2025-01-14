```mermaid
sequenceDiagram
    participant User
    participant Browser
    participant Server

    User->>Browser: Open https://studies.cs.helsinki.fi/exampleapp/spa
    Browser->>Server: GET /exampleapp/spa
    activate Server
    Server-->>Browser: HTML document (SPA)
    deactivate Server

    Browser->>Server: GET /exampleapp/main.css
    activate Server
    Server-->>Browser: CSS file
    deactivate Server

    Browser->>Server: GET /exampleapp/spa.js
    activate Server
    Server-->>Browser: JavaScript file 
    deactivate Server

    Browser->>Server: GET /exampleapp/data.json
    activate Server
    Server-->>Browser: JSON file 
    deactivate Server

    User->>Browser: Enters a new note in the input field
    User->>Browser: Click Save

    Browser->>Server: POST /exampleapp/new_note_spa
    activate Server
    Server-->>Browser: 201 made
    deactivate Server

    Browser->>Browser: Updates notes list 
    User->>Browser: Views the updated notes list
