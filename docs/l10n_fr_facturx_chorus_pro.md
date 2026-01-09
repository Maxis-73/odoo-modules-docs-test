# Módulo: France - Peppol integration with Chorus Pro

## Información General
- **Nombre técnico:** l10n_fr_facturx_chorus_pro
- **Versión:** 1.0
- **Categoría:** Accounting/Localizations/EDI
- **Dependencias:** account, account_edi_ubl_cii, l10n_fr_account




## Descripción

Add support to fill three optional fields used when using Chorus Pro, especially when invoicing public services.




## Modelos

### account.edi.xml.ubl_bis3


- Hereda de:

  - account.edi.xml.ubl_bis3




- No agrega campos



### account.move


- Hereda de:

  - account.move




- Campos:

  - **buyer_reference** (Char)


  - **contract_reference** (Char)


  - **purchase_order_reference** (Char)







