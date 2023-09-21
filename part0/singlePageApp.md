singlePageAppSequenceDiagram
    participant browser
    participant server
    participant SPA
    
    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/spa
    activate server
    server-->>browser: HTML document (SPA)
    deactivate server
    
    Note right of browser: The browser requests the SPA HTML document.
    
    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.js
    activate server
    server-->>browser: JavaScript file (SPA logic)
    deactivate server
    
    Note right of browser: The browser requests the JavaScript file containing the SPA logic.
    
    browser->>SPA: SPA Initialization
    activate SPA
    
    Note right of browser: The SPA initializes and starts rendering the page.
    
    browser->>server: AJAX Request for Data
    activate server
    server-->>browser: JSON data (e.g., notes)
    deactivate server
    
    Note right of browser: The SPA makes an AJAX request to fetch data (e.g., notes) from the server.
    
    browser-->>SPA: Data Received
    Note right of browser: The SPA receives the data from the server.
    
    SPA->>browser: Render Page
    deactivate SPA
    
    Note right of browser: The SPA renders the page using the received data.
