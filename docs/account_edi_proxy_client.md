# Módulo: Proxy features for account_edi

## Información General
- **Nombre técnico:** account_edi_proxy_client
- **Versión:** 1.0
- **Categoría:** Accounting/Accounting
- **Dependencias:** account, certificate




## Descripción

This module adds generic features to register an Odoo DB on the proxy responsible for receiving data (via requests from web-services).
- An edi_proxy_user has a unique identification on a specific proxy type (e.g. l10n_it_edi, peppol) which
allows to identify him when receiving a document addressed to him. It is linked to a specific company on a specific
Odoo database.
- Encryption features allows to decrypt all the user's data when receiving it from the proxy.
- Authentication offers an additionnal level of security to avoid impersonification, in case someone gains to the user's database.
    



## Modelos

### account_edi_proxy_client.user


- Hereda de: Base



#### Campos
- **active** (Boolean)
- **id_client** (Char)
- **company_id** (Many2one) → res.company
- **edi_identification** (Char)
- **private_key_id** (Many2one) → certificate.key
- **refresh_token** (Char)
- **proxy_type** (Selection)
- **edi_mode** (Selection)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | EDI Proxy User | `account_edi_proxy_client.view_form_account_edi_proxy_client_user` | - |
| list | EDI Proxy Users | `account_edi_proxy_client.view_tree_account_edi_proxy_client_user` | - |




### certificate.key


- Hereda de:

  - certificate.key




- No agrega campos




### res.company


- Hereda de:

  - res.company




#### Campos
- **account_edi_proxy_client_ids** (One2many) → account_edi_proxy_client.user










