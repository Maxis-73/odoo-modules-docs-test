# Módulo: Indian - E-invoicing

## Información General
- **Nombre técnico:** l10n_in_edi
- **Versión:** 1.03.00
- **Categoría:** Accounting/Localizations/EDI
- **Dependencias:** account_edi, l10n_in




## Descripción

Indian - E-invoicing
To submit invoicing through API to the government.
We use "Tera Software Limited" as GSP

Step 1: First you need to create an API username and password in the E-invoice portal.
Step 2: Switch to company related to that GST number
Step 3: Set that username and password in Odoo (Goto: Invoicing/Accounting -> Configuration -> Settings -> Customer Invoices or find "E-invoice" in search bar)
Step 4: Repeat steps 1,2,3 for all GSTIN you have in odoo. If you have a multi-company with the same GST number then perform step 1 for the first company only.

For the creation of API username and password please ref this [document](https://service.odoo.co.in/einvoice_create_api_user).
    



## Modelos

### account.move


- Hereda de:

  - account.move




- Campos:

  - **l10n_in_edi_cancel_reason** (Selection)


  - **l10n_in_edi_cancel_remarks** (Char) → Cancel remarks


  - **l10n_in_edi_show_cancel** (Boolean)





### account.edi.format


- Hereda de:

  - account.edi.format




- No agrega campos



### res.config.settings


- Hereda de:

  - res.config.settings




- Campos:

  - **l10n_in_edi_username** (Char) → Indian EDI username


  - **l10n_in_edi_password** (Char) → Indian EDI password





### res.company


- Hereda de:

  - res.company




- Campos:

  - **l10n_in_edi_username** (Char) → E-invoice (IN) Username


  - **l10n_in_edi_password** (Char) → E-invoice (IN) Password


  - **l10n_in_edi_token** (Char) → E-invoice (IN) Token


  - **l10n_in_edi_token_validity** (Datetime) → E-invoice (IN) Valid Until







