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

    User->>Browser: Interacts with the app 
    Browser->>Browser: Updates the page dynamically using JavaScript
