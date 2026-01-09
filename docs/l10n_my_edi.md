# Módulo: Malaysia - E-invoicing

## Información General
- **Nombre técnico:** l10n_my_edi
- **Versión:** 1.0
- **Categoría:** Accounting/Localizations/EDI
- **Dependencias:** l10n_my, l10n_my_ubl_pint, account_edi_proxy_client


## Propósito
E-invoicing using MyInvois



## Descripción

    This modules allows the user to send their invoices to the MyInvois system.
    



## Modelos

### account.move.send


- Hereda de:

  - account.move.send




- No agrega campos



### account.edi.xml.ubl_myinvois_my


- Hereda de:

  - account.edi.xml.ubl_21




- No agrega campos



### product.template


- Hereda de:

  - product.template




- Campos:

  - **l10n_my_edi_classification_code** (Selection)





### account.move


- Hereda de:

  - account.move




- Campos:

  - **l10n_my_edi_file_id** (Many2one) → ir.attachment


  - **l10n_my_edi_file** (Binary)


  - **l10n_my_edi_display_tax_exemption_reason** (Boolean)


  - **l10n_my_edi_exemption_reason** (Char)


  - **l10n_my_edi_custom_form_reference** (Char)


  - **l10n_my_edi_state** (Selection)


  - **l10n_my_edi_validation_time** (Datetime)


  - **l10n_my_edi_submission_uid** (Char)


  - **l10n_my_edi_external_uuid** (Char)


  - **l10n_my_error_document_hash** (Char)


  - **l10n_my_edi_retry_at** (Char)





### l10n_my_edi.industry_classification


- Hereda de: Base



- Campos:

  - **name** (Char)


  - **code** (Char)





### account_edi_proxy_client.user


- Hereda de:

  - account_edi_proxy_client.user




- Campos:

  - **proxy_type** (Selection)





### account.tax


- Hereda de:

  - account.tax




- Campos:

  - **l10n_my_tax_type** (Selection)





### res.config.settings


- Hereda de:

  - res.config.settings




- Campos:

  - **l10n_my_edi_mode** (Selection)


  - **l10n_my_edi_default_import_journal_id** (Many2one)


  - **l10n_my_edi_proxy_user_id** (Many2one)


  - **l10n_my_edi_company_vat** (Char)


  - **l10n_my_accept_processing** (Boolean)





### res.company


- Hereda de:

  - res.company




- Campos:

  - **l10n_my_edi_proxy_user_id** (Many2one) → account_edi_proxy_client.user


  - **l10n_my_identification_type** (Selection)


  - **l10n_my_identification_number** (Char)


  - **l10n_my_identification_number_placeholder** (Char)


  - **l10n_my_edi_industrial_classification** (Many2one) → l10n_my_edi.industry_classification


  - **l10n_my_edi_mode** (Selection)


  - **l10n_my_edi_default_import_journal_id** (Many2one) → account.journal





### res.partner


- Hereda de:

  - res.partner




- Campos:

  - **l10n_my_tin_validation_state** (Selection)


  - **l10n_my_edi_display_tin_warning** (Boolean)


  - **l10n_my_identification_type** (Selection)


  - **l10n_my_identification_number** (Char)


  - **l10n_my_identification_number_placeholder** (Char)








## Vistas


### l10n_my_edi.industry_classification

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | l10n_my_edi.industry_classification.list | `l10n_my_edi.view_classification_list` | - |



### l10n_my_edi.document.status.update

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | l10n_my_edi.document.status.update.form | `l10n_my_edi.l10n_my_edi_document_status_update_form` | - |



#### Botones (l10n_my_edi.l10n_my_edi_document_status_update_form)
- **Update Invoice** (object)

