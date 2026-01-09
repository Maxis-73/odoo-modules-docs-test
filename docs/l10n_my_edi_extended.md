# Módulo: Malaysia - E-invoicing Extended Features

## Información General
- **Nombre técnico:** l10n_my_edi_extended
- **Versión:** 1.0
- **Categoría:** Accounting/Localizations/EDI
- **Dependencias:** l10n_my_edi


## Propósito
Extended features for the E-invoicing using MyInvois



## Descripción

    This module improves the MyInvois E-invoicing feature by adding proper support for self billing, rendering the MyInvois
    QR code in the invoice PDF file and allows better management of foreign customer TIN.
    



## Modelos

### account.move.send


- Hereda de:

  - account.move.send




- No agrega campos



### account.edi.xml.ubl_myinvois_my


- Hereda de:

  - account.edi.xml.ubl_myinvois_my




- No agrega campos



### account.move


- Hereda de:

  - account.move




- Campos:

  - **l10n_my_edi_invoice_long_id** (Char)


  - **l10n_my_invoice_need_edi** (Boolean)





### account.move.line


- Hereda de:

  - account.move.line




- Campos:

  - **l10n_my_edi_classification_code** (Selection)





### res.partner


- Hereda de:

  - res.partner




- Campos:

  - **l10n_my_edi_industrial_classification** (Many2one) → l10n_my_edi.industry_classification


  - **l10n_my_edi_malaysian_tin** (Char)







