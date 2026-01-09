# Módulo: Denmark EDI - Nemhandel

## Información General
- **Nombre técnico:** l10n_dk_nemhandel
- **Versión:** 1.0
- **Categoría:** Accounting/Localizations/EDI
- **Dependencias:** account_edi_proxy_client, account_edi_ubl_cii, l10n_dk


## Propósito
This module is used to send/receive documents with Nemhandel



## Descripción

        - Send and receive documents via Nemhandel network in OIOUBL 2.1 format
    



## Modelos

### account.move.send


- Hereda de:

  - account.move.send




- No agrega campos



### account.edi.xml.oioubl_21


- Hereda de:

  - account.edi.xml.ubl_21




- No agrega campos



### account.move


- Hereda de:

  - account.move




- Campos:

  - **nemhandel_message_uuid** (Char)


  - **nemhandel_move_state** (Selection)





### account.journal


- Hereda de:

  - account.journal




- Campos:

  - **l10n_dk_nemhandel_proxy_state** (Selection)


  - **is_nemhandel_journal** (Boolean)





### account_edi_proxy_client.user


- Hereda de:

  - account_edi_proxy_client.user




- Campos:

  - **nemhandel_verification_code** (Char)


  - **proxy_type** (Selection)





### res.config.settings


- Hereda de:

  - res.config.settings




- Campos:

  - **nemhandel_edi_user** (Many2one)


  - **nemhandel_edi_mode** (Selection)


  - **nemhandel_contact_email** (Char)


  - **nemhandel_identifier_type** (Selection)


  - **nemhandel_identifier_value** (Char)


  - **nemhandel_edi_identification** (Char)


  - **nemhandel_phone_number** (Char)


  - **l10n_dk_nemhandel_proxy_state** (Selection)


  - **nemhandel_purchase_journal_id** (Many2one)





### res.company


- Hereda de:

  - res.company




- Campos:

  - **nemhandel_contact_email** (Char)


  - **nemhandel_phone_number** (Char)


  - **l10n_dk_nemhandel_proxy_state** (Selection)


  - **nemhandel_identifier_type** (Selection)


  - **nemhandel_identifier_value** (Char)


  - **nemhandel_purchase_journal_id** (Many2one) → account.journal


  - **nemhandel_edi_user** (Many2one) → account_edi_proxy_client.user





### res.partner


- Hereda de:

  - res.partner




- Campos:

  - **invoice_sending_method** (Selection)


  - **invoice_edi_format** (Selection)


  - **nemhandel_verification_state** (Selection)


  - **nemhandel_identifier_type** (Selection)


  - **nemhandel_identifier_value** (Char)


  - **is_using_nemhandel** (Boolean)








## Vistas


### nemhandel.registration

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | nemhandel.registration.form | `l10n_dk_nemhandel.nemhandel_registration_form` | - |



#### Botones (l10n_dk_nemhandel.nemhandel_registration_form)
- **Activate Nemhandel** (object)
- **Activate Nemhandel (Test)** (object)
- **Activate Nemhandel (Demo)** (object)
- **Confirm** (object)
- **Send again** (object)
- **Cancel Registration** (object)

