# Módulo: Passkeys

## Información General
- **Nombre técnico:** auth_passkey
- **Versión:** 1.0
- **Categoría:** Hidden/Tools
- **Dependencias:** base_setup, web


## Propósito
Log in with a Passkey



## Descripción

The implementation of Passkeys using the webauthn protocol.

Passkeys are a secure alternative to a username and a password.
When a user logs in with a Passkey, MFA will not be required.




## Modelos

### auth.passkey.key


- Hereda de: Base



- Campos:

  - **name** (Char)


  - **credential_identifier** (Char)


  - **public_key** (Char)


  - **sign_count** (Integer)





### auth.passkey.key.create


- Hereda de: Base



- Campos:

  - **name** (Char) → Name





### res.users


- Hereda de:

  - res.users




- Campos:

  - **auth_passkey_key_ids** (One2many) → auth.passkey.key





### res.users.identitycheck


- Hereda de:

  - res.users.identitycheck




- Campos:

  - **auth_method** (Selection)








## Vistas


### auth.passkey.key

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | auth.passkey.key.rename | `auth_passkey.auth_passkey_key_rename` | - |



### auth.passkey.key.create

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | Create Passkey Wizard Form | `auth_passkey.auth_passkey_key_create_view_form` | - |



#### Botones (auth_passkey.auth_passkey_key_create_view_form)
- **Create** (object)


### res.users

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| kanban | auth.passkey.users.form | `auth_passkey.auth_passkey_users_form` | base.view_users_form |
| kanban | auth.passkey.users.preferences | `auth_passkey.auth_passkey_users_preferences` | base.view_users_form_simple_modif |


