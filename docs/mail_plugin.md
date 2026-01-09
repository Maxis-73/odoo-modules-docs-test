# Módulo: Mail Plugin

## Información General
- **Nombre técnico:** mail_plugin
- **Versión:** 1.0
- **Categoría:** Sales/CRM
- **Dependencias:** web, contacts, iap


## Propósito
Allows integration with mail plugins.



## Descripción
Integrate Odoo with your mailbox, get information about contacts directly inside your mailbox, log content of emails as internal notes



## Modelos

### res.partner.iap


- Hereda de: Base



#### Campos
- **partner_id** (Many2one) → res.partner
- **iap_search_domain** (Char) → Search Domain / Email
- **iap_enrich_info** (Text) → IAP Enrich Info





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | res.partner.iap.view.form | `mail_plugin.res_partner_iap_view_form` | - |
| list | res.partner.iap.view.list | `mail_plugin.res_partner_iap_view_tree` | - |




### ir.http


- Hereda de:

  - ir.http




- No agrega campos




### res.partner


- Hereda de:

  - res.partner




#### Campos
- **iap_enrich_info** (Text) → IAP Enrich Info
- **iap_search_domain** (Char) → Search Domain / Email










