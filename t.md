```mermaid
sequenceDiagram
    participant User
    participant Browser
    participant Server

   User->>Browser:Open https://studies.cs.helsinki.fi/exampleapp/notes
   Browser->>Server GET  /exampleapp/notes
   activate Server
   Server-->>Browser: HTML DOCUMENT
   deactivate Server
   Browser->>Server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
   activate Server
   Server-->>Browser: the css file
   deactivate Server
   Browser->>Server: GET https://studies.cs.helsinki.fi/exampleapp/main.js
   activate Server
   Server-->>Browser: the JavaScript file
   deactivate Server
   User->>Browser:Enter text as input
   User->>Browser: SAVE it
   Browser->>Server: POST /exampleapp/new_note
   Server -->>Browser: POST 302 redirect to /exampleapp/notes
   Browser->>Server: GET /exampleapp/notes
   Server-->>Browser: update notes page HTML
     deactivat
   Browser->>Server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
   activate Server
   Server-->>Browser: the css file
   deactivate Server
   Browser->>Server: GET https://studies.cs.helsinki.fi/exampleapp/main.js
   activate Server
   Server-->>Browser: the JavaScript file
   deactivate Server
   Browser->>Server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
   activate Server
   Server-->>Browser: the Json file
   deactivate Server
  
   
           
