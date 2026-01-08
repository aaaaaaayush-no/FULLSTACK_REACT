```mermaid
sequenceDiagram
    participant User
    participant Browser
    participant Server

    User->>Browser: Writes note text into input field
    User->>Browser: Clicks "Save" button

    Note right of Browser: Browser submits HTML form

    Browser->>Server: POST /notes (form data)
    Note right of Server: Server saves note

    Server-->>Browser: HTTP 302 Redirect to /notes
    Browser->>Server: GET /notes
    Server-->>Browser: HTML page with updated notes

    Browser-->>User: Page reloads and shows new note
