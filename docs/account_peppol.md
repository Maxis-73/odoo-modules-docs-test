# Módulo: Peppol

## Información General
- **Nombre técnico:** account_peppol
- **Versión:** 1.1
- **Categoría:** Accounting/Accounting
- **Dependencias:** account_edi_proxy_client, account_edi_ubl_cii


## Propósito
This module is used to send/receive documents with PEPPOL



## Descripción

- Register as a PEPPOL participant
- Send and receive documents via PEPPOL network in Peppol BIS Billing 3.0 format
    



## Modelos

### account.move.send


- Hereda de:

  - account.move.send




- No agrega campos




### account.move


- Hereda de:

  - account.move




#### Campos
- **peppol_message_uuid** (Char)
- **peppol_move_state** (Selection)





### account.journal


- Hereda de:

  - account.journal




#### Campos
- **account_peppol_proxy_state** (Selection)
- **is_peppol_journal** (Boolean)





### account_edi_proxy_client.user


- Hereda de:

  - account_edi_proxy_client.user




#### Campos
- **peppol_verification_code** (Char)
- **proxy_type** (Selection)





### res.config.settings


- Hereda de:

  - res.config.settings




#### Campos
- **account_peppol_edi_user** (Many2one) → account_edi_proxy_client.user
- **account_peppol_edi_mode** (Selection)
- **account_peppol_contact_email** (Char)
- **account_peppol_eas** (Selection)
- **account_peppol_edi_identification** (Char)
- **account_peppol_endpoint** (Char)
- **account_peppol_migration_key** (Char)
- **account_peppol_phone_number** (Char)
- **account_peppol_proxy_state** (Selection)
- **account_peppol_purchase_journal_id** (Many2one)





### res.company


- Hereda de:

  - res.company




#### Campos
- **account_peppol_contact_email** (Char)
- **account_peppol_migration_key** (Char)
- **account_peppol_phone_number** (Char)
- **account_peppol_proxy_state** (Selection)
- **peppol_eas** (Selection)
- **peppol_endpoint** (Char)
- **peppol_purchase_journal_id** (Many2one) → account.journal





### res.partner


- Hereda de:

  - res.partner




#### Campos
- **invoice_sending_method** (Selection)
- **peppol_eas** (Selection)
- **available_peppol_sending_methods** (Json)
- **available_peppol_edi_formats** (Json)
- **peppol_verification_state** (Selection)










## Vistas Adicionales


### account_peppol.service.wizard

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | account.peppol.service.configuration.form | `account_peppol.peppol_service_configuration` | - |



**Botones (account_peppol.peppol_service_configuration):**
- **Confirm** (object)


### peppol.registration

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | peppol.registration.form | `account_peppol.peppol_registration_form` | - |




