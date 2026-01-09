# Módulo: Malaysia - UBL PINT

## Información General
- **Nombre técnico:** l10n_my_ubl_pint
- **Versión:** 1.0
- **Categoría:** Accounting/Localizations/EDI
- **Dependencias:** account_edi_ubl_cii




## Descripción

    The UBL PINT e-invoicing format for Malaysia is based on the Peppol International (PINT) model for Billing.
    



## Modelos

### account.edi.xml.pint_my


- Hereda de:

  - account.edi.xml.ubl_bis3




- No agrega campos



### res.company


- Hereda de:

  - res.company




- Campos:

  - **sst_registration_number** (Char)


  - **ttx_registration_number** (Char)





### base.document.layout


- Hereda de:

  - base.document.layout




- Campos:

  - **account_fiscal_country_id** (Many2one)


  - **sst_registration_number** (Char)


  - **ttx_registration_number** (Char)





### res.partner


- Hereda de:

  - res.partner




- Campos:

  - **invoice_edi_format** (Selection)


  - **sst_registration_number** (Char)


  - **ttx_registration_number** (Char)







