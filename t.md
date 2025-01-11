```mermaid
sequenceDiagram
    participant User
    participant Browser
    participant Server

    User->>Browser: Open the notes page<br>(https://studies.cs.helsinki.fi/exampleapp/notes)
    Browser->>Server: HTTP GET /exampleapp/notes
    Server-->>Browser: HTML content (notes page)
    Browser->>Server: Requests for CSS, JavaScript, and other assets
    Server-->>Browser: Responds with requested assets

    User->>Browser: Writes a note in the text field and clicks Save
    Browser->>Server: HTTP POST /new_note<br>(with note content in payload)
    Server-->>Browser: Redirect response (e.g., HTTP 302)
    Browser->>Server: HTTP GET /exampleapp/notes (after redirect)
    Server-->>Browser: Updated HTML content (including the new note)

    User->>Browser: Sees the new note in the list
