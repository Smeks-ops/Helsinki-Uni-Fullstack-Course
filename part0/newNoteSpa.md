newNoteSpaSequenceDiagram
    participant browser
    participant server
    participant SPA
    
    browser->>SPA: User interacts with SPA (e.g., fills out a new note)
    activate SPA
    
    Note right of SPA: The user interacts with the SPA by creating a new note.
    
    SPA->>browser: Capture user input (e.g., new note content)
    
    Note right of SPA: The SPA captures the user's input, such as the content of the new note.
    
    browser->>server: POST request to save new note
    activate server
    
    Note right of browser: The SPA sends a POST request to the server to save the new note.
    
    server->>server: Process the new note data
    
    Note right of server: The server processes the new note data, including validation and storage.
    
    server-->>browser: 201 Created (New note saved)
    
    Note right of server: The server responds with a 201 status code to indicate that the new note has been successfully saved.
    
    browser-->>SPA: Update SPA with new note
    
    Note right of browser: The SPA receives the server's response and updates the user interface to display the newly created note.
    
    deactivate SPA
    deactivate server
