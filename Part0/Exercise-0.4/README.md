```mermaid
    sequenceDiagram
        participant browser
        participant server

        browser ->> server: POST https://studies.cs.helsinki.fi/exampleapp/new_note
        activate server
        server ->> browser: Redirect 302 to route exampleapp/notes
        deactivate server

        browser ->> server: GET https://studies.cs.helsinki.fi/exampleapp/notes
        activate server
        server ->> browser: Status 200
        deactivate server

        browser ->> server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
        activate server
        server ->> browser: Status 200
        deactivate server

        browser ->> server: GET https://studies.cs.helsinki.fi/exampleapp/main.js
        activate server
        server ->> browser: Status 200 with "data.json" file
        deactivate server
```
