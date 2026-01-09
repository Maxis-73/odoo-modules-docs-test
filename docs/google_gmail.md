# Módulo: Google Gmail

## Información General
- **Nombre técnico:** google_gmail
- **Versión:** 1.2
- **Categoría:** Hidden
- **Dependencias:** mail




## Descripción
Gmail support for incoming / outgoing mail servers



## Modelos

### ir.mail_server


- Hereda de:


  - ir.mail_server

  - google.gmail.mixin





#### Campos
- **smtp_authentication** (Selection)





### fetchmail.server


- Hereda de:


  - fetchmail.server

  - google.gmail.mixin





#### Campos
- **server_type** (Selection)





### res.config.settings


- Hereda de:

  - res.config.settings




#### Campos
- **google_gmail_client_identifier** (Char) → Gmail Client Id
- **google_gmail_client_secret** (Char) → Gmail Client Secret





### google.gmail.mixin


- Hereda de: Base



#### Campos
- **google_gmail_authorization_code** (Char)
- **google_gmail_refresh_token** (Char)
- **google_gmail_access_token** (Char)
- **google_gmail_access_token_expiration** (Integer)
- **google_gmail_uri** (Char)







