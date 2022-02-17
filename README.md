# Mermaid Markdown Examples

Mermaid Website: https://mermaid-js.github.io/mermaid/#/

## Sequence Diagrams

Documentation: https://mermaid-js.github.io/mermaid/#/sequenceDiagram

### New User Registration

```mermaid
sequenceDiagram
  participant V as VISITOR
  participant A as CLIENT
  participant I as IDENTITY SERVICE
  participant D as DATABASE
  participant M as MAILER
  V->>A: sign up request
  A->>V: registration page
  V->>A: desired credentials
  alt Invalid Credentials
    A->>V: validation error
  else Valid Credentials
    A->>I: create user
  end
  alt Already Registered
    I->>A: validation error
    A->>V: login page
  else Registration Succeeds
    I->>A: session token
    A->>D: insert user record
    A->>M: send verification email
    A->>V: welcome page
  end
```
