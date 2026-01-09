# Módulo: Signup

## Información General
- **Nombre técnico:** auth_signup
- **Versión:** 1.0
- **Categoría:** Hidden/Tools
- **Dependencias:** base_setup, mail, web




## Descripción

Allow users to sign up and reset their password
===============================================
    



## Modelos

### res.users


- Hereda de:

  - res.users




#### Campos
- **state** (Selection)





### res.config.settings


- Hereda de:

  - res.config.settings




#### Campos
- **auth_signup_reset_password** (Boolean)
- **auth_signup_uninvited** (Selection)
- **auth_signup_template_user_id** (Many2one) → res.users





### ir.http


- Hereda de:

  - ir.http




- No agrega campos




### res.partner


- Hereda de:

  - res.partner




#### Campos
- **signup_type** (Char)







