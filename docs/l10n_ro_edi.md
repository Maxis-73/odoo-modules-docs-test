# Módulo: Romania - E-invoicing

## Información General
- **Nombre técnico:** l10n_ro_edi
- **Versión:** 1.0
- **Categoría:** Accounting/Localizations/EDI
- **Dependencias:** account_edi_ubl_cii, l10n_ro


## Propósito
E-Invoice implementation for Romania



## Descripción

E-invoice implementation for Romania
    



## Modelos

### account.move.send


- Hereda de:

  - account.move.send




- No agrega campos



### l10n_ro_edi.document


- Hereda de: Base



- Campos:

  - **invoice_id** (Many2one) → account.move


  - **state** (Selection)


  - **datetime** (Datetime)


  - **attachment_id** (Many2one) → ir.attachment


  - **message** (Char)


  - **key_loading** (Char)


  - **key_signature** (Char)


  - **key_certificate** (Char)





### account.move


- Hereda de:

  - account.move




- Campos:

  - **l10n_ro_edi_document_ids** (One2many) → l10n_ro_edi.document


  - **l10n_ro_edi_state** (Selection)


  - **l10n_ro_edi_attachment_id** (Many2one) → ir.attachment


  - **l10n_ro_edi_index** (Char)





### res.config.settings


- Hereda de:

  - res.config.settings




- Campos:

  - **l10n_ro_edi_client_id** (Char)


  - **l10n_ro_edi_client_secret** (Char)


  - **l10n_ro_edi_access_token** (Char)


  - **l10n_ro_edi_refresh_token** (Char)


  - **l10n_ro_edi_access_expiry_date** (Date)


  - **l10n_ro_edi_refresh_expiry_date** (Date)


  - **l10n_ro_edi_callback_url** (Char)


  - **l10n_ro_edi_test_env** (Boolean)


  - **l10n_ro_edi_oauth_error** (Char)





### account.edi.xml.ubl_ro


- Hereda de:

  - account.edi.xml.ubl_bis3




- No agrega campos



### res.company


- Hereda de:

  - res.company




- Campos:

  - **l10n_ro_edi_client_id** (Char)


  - **l10n_ro_edi_client_secret** (Char)


  - **l10n_ro_edi_access_token** (Char)


  - **l10n_ro_edi_refresh_token** (Char)


  - **l10n_ro_edi_access_expiry_date** (Date)


  - **l10n_ro_edi_refresh_expiry_date** (Date)


  - **l10n_ro_edi_callback_url** (Char)


  - **l10n_ro_edi_test_env** (Boolean)


  - **l10n_ro_edi_oauth_error** (Char)





### res.partner


- Hereda de:

  - res.partner




- Campos:

  - **invoice_edi_format** (Selection)








## Vistas


### account.move

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | account.move.form.inherit.l10n_ro_edi | `l10n_ro_edi.account_move_form_inherit_l10n_ro_edi` | account.view_move_form |


