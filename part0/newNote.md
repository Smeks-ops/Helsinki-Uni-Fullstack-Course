newNoteDiagram
    participant browser
    participant server
    
    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new-note
    activate server
    server-->>browser: 201 Created (New note is saved)
    deactivate server

    Note right of browser: The browser sends a POST request to the server with the new note data.
    
    Note right of browser: The server processes the request, creates a new note, and responds with a 201 status code, indicating that the note has been successfully created.
    
    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/notes
    activate server
    server-->>browser: Updated list of notes (including the new one)
    deactivate server
    
    Note right of browser: After saving the note, the browser sends a GET request to retrieve the updated list of notes from the server.
    
    Note right of browser: The server responds with an updated list of notes, including the newly created one.
    
    browser-->>browser: Display the updated list of notes
    Note right of browser: The browser then displays the updated list of notes, including the newly added note.
