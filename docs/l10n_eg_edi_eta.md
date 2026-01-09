# Módulo: Egypt E-Invoicing

## Información General
- **Nombre técnico:** l10n_eg_edi_eta
- **Versión:** 0.2
- **Categoría:** account
- **Dependencias:** account_edi, l10n_eg


## Propósito

            Egypt Tax Authority Invoice Integration
        



## Descripción

Egypt Tax Authority Invoice Integration
Integrates with the ETA portal to automatically send and sign the Invoices to the Tax Authority.
    



## Modelos

### l10n_eg_edi.uom.code


- Hereda de: Base



- Campos:

  - **name** (Char)


  - **code** (Char)





### uom.uom


- Hereda de:

  - uom.uom




- Campos:

  - **l10n_eg_unit_code_id** (Many2one) → l10n_eg_edi.uom.code





### res.currency.rate


- Hereda de:

  - res.currency.rate




- No agrega campos



### product.template


- Hereda de:

  - product.template




- Campos:

  - **l10n_eg_eta_code** (Char) → ETA Item code





### product.product


- Hereda de:

  - product.product




- Campos:

  - **l10n_eg_eta_code** (Char) → ETA Code





### l10n_eg_edi.thumb.drive


- Hereda de: Base



- Campos:

  - **user_id** (Many2one) → res.users


  - **company_id** (Many2one) → res.company


  - **certificate** (Binary) → ETA Certificate


  - **pin** (Char) → ETA USB Pin


  - **access_token** (Char)





### account.move


- Hereda de:

  - account.move




- Campos:

  - **l10n_eg_long_id** (Char)


  - **l10n_eg_qr_code** (Char)


  - **l10n_eg_submission_number** (Char)


  - **l10n_eg_uuid** (Char)


  - **l10n_eg_eta_json_doc_id** (Many2one) → ir.attachment


  - **l10n_eg_signing_time** (Datetime) → Signing Time


  - **l10n_eg_is_signed** (Boolean)





### account.journal


- Hereda de:

  - account.journal




- Campos:

  - **l10n_eg_branch_id** (Many2one) → res.partner


  - **l10n_eg_activity_type_id** (Many2one) → l10n_eg_edi.activity.type


  - **l10n_eg_branch_identifier** (Char) → ETA Branch ID





### account.edi.format


- Hereda de:

  - account.edi.format




- No agrega campos



### res.config.settings


- Hereda de:

  - res.config.settings




- Campos:

  - **l10n_eg_client_identifier** (Char)


  - **l10n_eg_client_secret** (Char)


  - **l10n_eg_production_env** (Boolean)


  - **l10n_eg_invoicing_threshold** (Float)





### l10n_eg_edi.activity.type


- Hereda de: Base



- Campos:

  - **name** (Char)


  - **code** (Char)





### res.company


- Hereda de:

  - res.company




- Campos:

  - **l10n_eg_client_identifier** (Char) → ETA Client ID


  - **l10n_eg_client_secret** (Char) → ETA Secret


  - **l10n_eg_production_env** (Boolean) → In Production Environment


  - **l10n_eg_invoicing_threshold** (Float) → Invoicing Threshold





### res.partner


- Hereda de:

  - res.partner




- Campos:

  - **l10n_eg_building_no** (Char) → Building No.








## Vistas


### l10n_eg_edi.thumb.drive

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | view_l10n_eg_edi_thumb_drive_tree | `l10n_eg_edi_eta.view_l10n_eg_edi_thumb_drive_tree` | - |


