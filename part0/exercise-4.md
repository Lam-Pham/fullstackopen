
```mermaid
sequenceDiagram
    participant browser
    participant server
    browser->>server: HTTP POST https://studies.cs.helsinki.fi/exampleapp/new_note
    server->>browser: HTTP status code 302
    browser->>server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/notes
    server->>browser: HTML Code
    browser->>server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/main.css
    server->>browser: main.css
    browser->>server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/main.js

    note over browser: browser executes js-code that requests JSON data from server

    server->>browser: main.js
    browser->>server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/data.json

    note over browser: browser executes the event handler that renders notes to display

```