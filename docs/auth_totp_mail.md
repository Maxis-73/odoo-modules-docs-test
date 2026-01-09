# Módulo: 2FA Invite mail

## Información General
- **Nombre técnico:** auth_totp_mail
- **Versión:** N/A
- **Categoría:** Extra Tools
- **Dependencias:** auth_totp, mail




## Descripción

2FA Invite mail
Allow the users to invite another user to use Two-Factor authentication
by sending an email to the target user. This email redirects them to:
- the users security settings if the user is internal.
- the portal security settings page if the user is not internal.
    



## Modelos

### auth_totp.device


- Hereda de:

  - auth_totp.device




- No agrega campos



### res.users


- Hereda de:

  - res.users




- No agrega campos






## Vistas


### res.users

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | res.users.view.form.auth.totp.mail | `auth_totp_mail.res_users_view_form` | base.view_users_form_simple_modif |


