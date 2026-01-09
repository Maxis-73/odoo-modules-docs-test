# Módulo: Sweden - Accounting

## Información General
- **Nombre técnico:** l10n_se
- **Versión:** 1.1
- **Categoría:** Accounting/Localizations/Account Charts
- **Dependencias:** account, base_vat




## Descripción

Swedish Accounting
------------------

This is the base module to manage the accounting chart for Sweden in Odoo.
It also includes the invoice OCR payment reference handling.
    



## Modelos

### account.chart.template


- Hereda de:

  - account.chart.template




- No agrega campos



### account.move


- Hereda de:

  - account.move




- No agrega campos



### account.journal


- Hereda de:

  - account.journal




- Campos:

  - **invoice_reference_model** (Selection)


  - **l10n_se_invoice_ocr_length** (Integer)





### account.chart.template


- Hereda de:

  - account.chart.template




- No agrega campos



### account.chart.template


- Hereda de:

  - account.chart.template




- No agrega campos



### res.company


- Hereda de:

  - res.company




- Campos:

  - **org_number** (Char)





### res.partner


- Hereda de:

  - res.partner




- Campos:

  - **l10n_se_check_vendor_ocr** (Boolean)


  - **l10n_se_default_vendor_payment_ref** (Char)







