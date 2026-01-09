# Módulo: Two-Factor Authentication (TOTP)

## Información General
- **Nombre técnico:** auth_totp
- **Versión:** N/A
- **Categoría:** Extra Tools
- **Dependencias:** web




## Descripción

Two-Factor Authentication (TOTP)
================================
Allows users to configure two-factor authentication on their user account
for extra security, using time-based one-time passwords (TOTP).

Once enabled, the user will need to enter a 6-digit code as provided
by their authenticator app before being granted access to the system.
All popular authenticator apps are supported.

Note: logically, two-factor prevents password-based RPC access for users
where it is enabled. In order to be able to execute RPC scripts, the user
can setup API keys to replace their main password.
    



## Modelos

### auth_totp.device


- Hereda de:

  - res.users.apikeys




- No agrega campos




### res.users


- Hereda de:

  - res.users




#### Campos
- **totp_secret** (Char)
- **totp_enabled** (Boolean)
- **totp_trusted_device_ids** (One2many) → auth_totp.device





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | user form: add totp status | `auth_totp.view_totp_form` | base.view_users_form |
| list | users preference: totp | `auth_totp.view_totp_field` | base.view_users_form_simple_modif |









## Vistas Adicionales


### auth_totp.wizard

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | auth_totp wizard | `auth_totp.view_totp_wizard` | - |



**Botones (auth_totp.view_totp_wizard):**
- **Activate** (object)



