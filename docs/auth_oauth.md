# Módulo: OAuth2 Authentication

## Información General
- **Nombre técnico:** auth_oauth
- **Versión:** N/A
- **Categoría:** Hidden/Tools
- **Dependencias:** base, web, base_setup, auth_signup




## Descripción

Allow users to login through OAuth2 Provider.
=============================================




## Modelos

### auth.oauth.provider


- Hereda de: Base



#### Campos
- **name** (Char)
- **client_id** (Char)
- **auth_endpoint** (Char)
- **scope** (Char)
- **validation_endpoint** (Char)
- **data_endpoint** (Char)
- **enabled** (Boolean)
- **css_class** (Char)
- **body** (Char)
- **sequence** (Integer)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | auth.oauth.provider.form | `auth_oauth.view_oauth_provider_form` | - |
| list | auth.oauth.provider.list | `auth_oauth.view_oauth_provider_tree` | - |




### res.users


- Hereda de:

  - res.users




#### Campos
- **oauth_provider_id** (Many2one) → auth.oauth.provider
- **oauth_uid** (Char)
- **oauth_access_token** (Char)





### res.config.settings


- Hereda de:

  - res.config.settings




#### Campos
- **auth_oauth_google_enabled** (Boolean)
- **auth_oauth_google_client_id** (Char)
- **server_uri_google** (Char)





### ir.config_parameter


- Hereda de:

  - ir.config_parameter




- No agrega campos









