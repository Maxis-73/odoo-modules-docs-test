# Módulo: Tax extension for UBL/CII

## Información General
- **Nombre técnico:** account_edi_ubl_cii_tax_extension
- **Versión:** 1.0
- **Categoría:** Accounting/Accounting
- **Dependencias:** account_edi_ubl_cii


## Propósito
Tax extension for UBL/CII



## Descripción

    This module adds 2 useful fields on the taxes for electronic invoicing: the tax category code and the tax exemption reason code.
    These fields will be read when generating Peppol Bis 3 or Factur-X xml, for instance.
    



## Modelos

### account.edi.common


- Hereda de:

  - account.edi.common




- No agrega campos




### account.tax


- Hereda de:

  - account.tax




#### Campos
- **ubl_cii_tax_category_code** (Selection)
- **ubl_cii_tax_exemption_reason_code** (Selection)







