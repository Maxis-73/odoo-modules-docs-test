# Módulo: Microsoft Outlook

## Información General
- **Nombre técnico:** microsoft_outlook
- **Versión:** 1.1
- **Categoría:** Hidden
- **Dependencias:** mail




## Descripción
Outlook support for incoming / outgoing mail servers



## Modelos

### ir.mail_server


- Hereda de:


  - ir.mail_server

  - microsoft.outlook.mixin





#### Campos
- **smtp_authentication** (Selection)





### microsoft.outlook.mixin


- Hereda de: Base



#### Campos
- **is_microsoft_outlook_configured** (Boolean) → Is Outlook Credential Configured
- **microsoft_outlook_refresh_token** (Char)
- **microsoft_outlook_access_token** (Char)
- **microsoft_outlook_access_token_expiration** (Integer)
- **microsoft_outlook_uri** (Char)





### fetchmail.server


- Hereda de:


  - fetchmail.server

  - microsoft.outlook.mixin





#### Campos
- **server_type** (Selection)





### res.config.settings


- Hereda de:

  - res.config.settings




#### Campos
- **microsoft_outlook_client_identifier** (Char) → Outlook Client Id
- **microsoft_outlook_client_secret** (Char) → Outlook Client Secret







