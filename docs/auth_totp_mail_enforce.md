# Módulo: 2FA by mail

## Información General
- **Nombre técnico:** auth_totp_mail_enforce
- **Versión:** N/A
- **Categoría:** Extra Tools
- **Dependencias:** auth_totp, mail




## Descripción

2FA by mail
Two-Factor authentication by sending a code to the user email inbox
when the 2FA using an authenticator app is not configured.
To enforce users to use a two-factor authentication by default,
and encourage users to configure their 2FA using an authenticator app.
    



## Modelos

### auth.totp.rate.limit.log


- Hereda de: Base



- Campos:

  - **user_id** (Many2one) → res.users


  - **scope** (Char)


  - **ip** (Char)


  - **limit_type** (Selection)





### res.users


- Hereda de:

  - res.users




- No agrega campos



### res.config.settings


- Hereda de:

  - res.config.settings




- Campos:

  - **auth_totp_enforce** (Boolean)


  - **auth_totp_policy** (Selection)







