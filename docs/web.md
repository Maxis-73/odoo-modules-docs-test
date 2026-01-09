# Módulo: Web

## Información General
- **Nombre técnico:** web
- **Versión:** 1.0
- **Categoría:** Hidden
- **Dependencias:** base




## Descripción

Odoo Web core module.
========================

This module provides the core of the Odoo Web Client.




## Modelos

### base.document.layout


- Hereda de: Base



#### Campos
- **company_id** (Many2one) → res.company
- **logo** (Binary)
- **preview_logo** (Binary)
- **report_header** (Html)
- **report_footer** (Html)
- **company_details** (Html)
- **is_company_details_empty** (Boolean)
- **paperformat_id** (Many2one)
- **external_report_layout_id** (Many2one)
- **font** (Selection)
- **primary_color** (Char)
- **secondary_color** (Char)
- **custom_colors** (Boolean)
- **logo_primary_color** (Char)
- **logo_secondary_color** (Char)
- **layout_background** (Selection)
- **layout_background_image** (Binary)
- **report_layout_id** (Many2one) → report.layout
- **preview** (Html)
- **partner_id** (Many2one)
- **phone** (Char)
- **email** (Char)
- **website** (Char)
- **vat** (Char)
- **name** (Char)
- **country_id** (Many2one)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | Document Layout | `web.view_base_document_layout` | - |



**Botones (web.view_base_document_layout):**
- **Continue** (object)



### ir.ui.view


- Hereda de:

  - ir.ui.view




- No agrega campos




### ir.model


- Hereda de:

  - ir.model




- No agrega campos




### res.users


- Hereda de:

  - res.users




- No agrega campos




### res.config.settings


- Hereda de:

  - res.config.settings




#### Campos
- **web_app_name** (Char) → Web App Name





### ir.ui.menu


- Hereda de:

  - ir.ui.menu




- No agrega campos




### ir.http


- Hereda de:

  - ir.http




- No agrega campos




### ir.qweb.field.image


- Hereda de:

  - ir.qweb.field.image




- No agrega campos




### ir.qweb.field.image_url


- Hereda de:

  - ir.qweb.field.image_url




- No agrega campos




### res.partner


- Hereda de:

  - res.partner




- No agrega campos




### base


- Hereda de:

  - base




- No agrega campos




### res.company


- Hereda de:

  - res.company




- No agrega campos









