## sequenceDiagram
    participant browser
    participant server
    participant user

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/notes
    activate server
    server-->>browser: HTML document
    deactivate server

    Note right of user: User interacts with the webpage<br/>and creates a new note

    user->>browser: Enters note content and clicks Save
    activate browser

    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note
    server-->>browser: Note saved successfully
    deactivate server

    browser-->>user: Confirmation message
    deactivate browser
