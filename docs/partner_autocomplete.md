# Módulo: Partner Autocomplete

## Información General
- **Nombre técnico:** partner_autocomplete
- **Versión:** 1.1
- **Categoría:** Hidden/Tools
- **Dependencias:** iap_mail


## Propósito
Auto-complete partner companies' data



## Descripción

Auto-complete partner companies' data
    



## Modelos

### iap.autocomplete.api


- Hereda de: Base



- No agrega campos



### res.partner.autocomplete.sync


- Hereda de: Base



- Campos:

  - **partner_id** (Many2one) → res.partner


  - **synched** (Boolean) → Is synched





### res.config.settings


- Hereda de:

  - res.config.settings




- Campos:

  - **partner_autocomplete_insufficient_credit** (Boolean) → Insufficient credit





### res.company


- Hereda de:

  - res.company




- Campos:

  - **partner_gid** (Integer) → Company database ID


  - **iap_enrich_auto_done** (Boolean) → Enrich Done





### ir.http


- Hereda de:

  - ir.http




- No agrega campos



### res.partner


- Hereda de:

  - res.partner




- Campos:

  - **partner_gid** (Integer) → Company database ID


  - **additional_info** (Char) → Additional info







