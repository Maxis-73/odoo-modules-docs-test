# Módulo: Contact Form

## Información General
- **Nombre técnico:** website_crm
- **Versión:** 2.1
- **Categoría:** Website/Website
- **Dependencias:** website, crm


## Propósito
Generate leads from a contact form



## Descripción

Add capability to your website forms to generate leads or opportunities in the CRM app.
Forms has to be customized inside the *Website Builder* in order to generate leads.

This module includes contact phone and mobile numbers validation.



## Modelos

### website


- Hereda de:

  - website




- Campos:

  - **crm_default_team_id** (Many2one) → crm.team


  - **crm_default_user_id** (Many2one) → res.users





### crm.lead


- Hereda de:

  - crm.lead




- Campos:

  - **visitor_ids** (Many2many) → website.visitor


  - **visitor_page_count** (Integer) → # Page Views





### website.visitor


- Hereda de:

  - website.visitor




- Campos:

  - **lead_ids** (Many2many) → crm.lead


  - **lead_count** (Integer) → # Leads







