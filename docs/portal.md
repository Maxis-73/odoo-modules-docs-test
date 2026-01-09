# Módulo: Customer Portal

## Información General
- **Nombre técnico:** portal
- **Versión:** N/A
- **Categoría:** Hidden
- **Dependencias:** web, web_editor, http_routing, mail, auth_signup


## Propósito
Customer Portal



## Descripción

This module adds required base code for a fully integrated customer portal.
It contains the base controller class and base templates. Business addons
will add their specific templates and controllers to extend the customer
portal.

This module contains most code coming from odoo v10 website_portal. Purpose
of this module is to allow the display of a customer portal without having
a dependency towards website editing and customization capabilities.



## Modelos

### mail.thread


- Hereda de:

  - mail.thread




#### Campos
- **website_message_ids** (One2many) → mail.message





### ir.ui.view


- Hereda de:

  - ir.ui.view




#### Campos
- **customize_show** (Boolean) → Show As Optional Inherit





### res.users.apikeys.description


- Hereda de:

  - res.users.apikeys.description




- No agrega campos




### portal.mixin


- Hereda de: Base



#### Campos
- **access_url** (Char) → Portal Access URL
- **access_token** (Char) → Security Token
- **access_warning** (Text) → Access warning





### mail.message


- Hereda de:

  - mail.message




- No agrega campos




### res.config.settings


- Hereda de:

  - res.config.settings




#### Campos
- **portal_allow_api_keys** (Boolean)





### ir.http


- Hereda de:

  - ir.http




- No agrega campos




### ir.qweb


- Hereda de:

  - ir.qweb




- No agrega campos




### res.partner


- Hereda de:

  - res.partner




- No agrega campos









## Vistas Adicionales


### portal.share

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | portal.share.wizard | `portal.portal_share_wizard` | - |



**Botones (portal.portal_share_wizard):**
- **Send** (object)


### portal.wizard

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | Grant portal access | `portal.wizard_view` | - |



**Botones (portal.wizard_view):**
- **action_refresh_modal** (object)
- **action_refresh_modal** (object)
- **action_refresh_modal** (object)
- **Grant Access** (object)
- **Revoke Access** (object)
- **Re-Invite** (object)



