```mermaid
sequenceDiagram
    participant A as User
    participant B as Client
    participant C as Server
    participant D as Datebase
    
    A ->> B: Fill username
    A ->> B: Fill password
    B ->> A: Enable "Login" button
    A ->> B: Click "Login" button
    B ->>+ C: POST/login
    C ->> D: SELECT FROM users
    Note over C,D:See login.py for impl. details 
    D -->> C: results
    C -->> B: {authenticated : true}
    B ->> A: redirect/home 
```