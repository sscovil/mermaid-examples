# Mermaid Markdown Examples

Mermaid Website: https://mermaid-js.github.io/mermaid/#/

## Sequence Diagrams

Documentation: https://mermaid-js.github.io/mermaid/#/sequenceDiagram

### New User Registration

```mermaid
sequenceDiagram
  participant V as VISITOR
  participant C as CLIENT
  participant I as IDENTITY SERVICE
  participant D as DATABASE
  participant M as MAILER
  V->>C: sign up request
  C->>V: registration page
  V->>C: desired credentials
  alt Invalid Credentials
    C->>V: validation error
  else Valid Credentials
    C->>I: create user
  end
  alt Already Registered
    I->>C: validation error
    C->>V: login page
  else Registration Succeeds
    I->>D: insert user record
    I->>M: send verification email
    I->>C: session token
    C->>V: welcome page
  end
```
