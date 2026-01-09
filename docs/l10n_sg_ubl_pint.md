# Módulo: Singapore - UBL PINT

## Información General
- **Nombre técnico:** l10n_sg_ubl_pint
- **Versión:** 1.0
- **Categoría:** Accounting/Localizations/EDI
- **Dependencias:** account_edi_ubl_cii_tax_extension




## Descripción

    The UBL PINT e-invoicing format for Singapore is based on the Peppol International (PINT) model for Billing.
    



## Modelos

### account.edi.xml.pint_sg


- Hereda de:

  - account.edi.xml.ubl_bis3




- No agrega campos



### account.move


- Hereda de:

  - account.move




- No agrega campos



### account.tax


- Hereda de:

  - account.tax




- Campos:

  - **ubl_cii_tax_category_code** (Selection)





### res.partner


- Hereda de:

  - res.partner




- Campos:

  - **invoice_edi_format** (Selection)







