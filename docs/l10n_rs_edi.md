# Módulo: Serbia - eFaktura E-invoicing

## Información General
- **Nombre técnico:** l10n_rs_edi
- **Versión:** 1.0
- **Categoría:** Accounting/Localizations/EDI
- **Dependencias:** account_edi_ubl_cii, l10n_rs


## Propósito
E-Invoice implementation for Serbia



## Descripción

eFaktura E-invoice implementation for Serbia
    



## Modelos

### account.move.send


- Hereda de:

  - account.move.send




- No agrega campos



### account.edi.xml.ubl.rs


- Hereda de:

  - account.edi.xml.ubl_21




- No agrega campos



### account.move


- Hereda de:

  - account.move




- Campos:

  - **l10n_rs_edi_uuid** (Char)


  - **l10n_rs_edi_is_eligible** (Boolean)


  - **l10n_rs_edi_attachment_file** (Binary)


  - **l10n_rs_edi_attachment_id** (Many2one) → ir.attachment


  - **l10n_rs_edi_state** (Selection)


  - **l10n_rs_edi_error** (Text)


  - **l10n_rs_tax_date_obligations_code** (Selection)


  - **l10n_rs_edi_invoice** (Char)


  - **l10n_rs_edi_sales_invoice** (Char)


  - **l10n_rs_edi_purchase_invoice** (Char)





### res.config.settings


- Hereda de:

  - res.config.settings




- Campos:

  - **l10n_rs_edi_api_key** (Char)


  - **l10n_rs_edi_demo_env** (Boolean)





### res.company


- Hereda de:

  - res.company




- Campos:

  - **l10n_rs_edi_api_key** (Char)


  - **l10n_rs_edi_demo_env** (Boolean)





### res.partner


- Hereda de:

  - res.partner




- Campos:

  - **l10n_rs_edi_registration_number** (Char)


  - **l10n_rs_edi_public_funds** (Char)







