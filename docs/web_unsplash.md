# Módulo: Unsplash Image Library

## Información General
- **Nombre técnico:** web_unsplash
- **Versión:** 1.1
- **Categoría:** Hidden
- **Dependencias:** base_setup, web_editor, html_editor


## Propósito
Find free high-resolution images from Unsplash



## Descripción
Explore the free high-resolution image library of Unsplash.com and find images to use in Odoo. An Unsplash search bar is added to the image library modal.



## Modelos

### res.users


- Hereda de:

  - res.users




- No agrega campos



### ir.attachment


- Hereda de:

  - ir.attachment




- No agrega campos



### res.config.settings


- Hereda de:

  - res.config.settings




- Campos:

  - **unsplash_access_key** (Char) → Access Key


  - **unsplash_app_id** (Char) → Application ID





### ir.qweb.field.image


- Hereda de:

  - ir.qweb.field.image




- No agrega campos





