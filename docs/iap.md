# Módulo: In-App Purchases

## Información General
- **Nombre técnico:** iap
- **Versión:** 1.1
- **Categoría:** Hidden/Tools
- **Dependencias:** web, base_setup


## Propósito
Basic models and helpers to support In-App purchases.



## Descripción

This module provides standard tools (account model, context manager and helpers)
to support In-App purchases inside Odoo. 



## Modelos

### iap.service


- Hereda de: Base



#### Campos
- **name** (Char)
- **technical_name** (Char)
- **description** (Char)
- **unit_name** (Char)
- **integer_balance** (Boolean)





### iap.enrich.api


- Hereda de: Base



- No agrega campos




### iap.account


- Hereda de: Base



#### Campos
- **name** (Char)
- **service_id** (Many2one) → iap.service
- **service_name** (Char)
- **service_locked** (Boolean)
- **description** (Char)
- **account_token** (Char)
- **company_ids** (Many2many) → res.company
- **balance** (Char)
- **warning_threshold** (Float) → Email Alert Threshold
- **warning_user_ids** (Many2many) → res.users
- **state** (Selection)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | iap.account.form | `iap.iap_account_view_form` | - |
| list | iap.account.list | `iap.iap_account_view_tree` | - |



**Botones (iap.iap_account_view_form):**
- **action_buy_credits** (object)








