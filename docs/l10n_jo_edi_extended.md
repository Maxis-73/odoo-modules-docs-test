# Módulo: Jordan E-Invoicing Extended Features

## Información General
- **Nombre técnico:** l10n_jo_edi_extended
- **Versión:** 1.0
- **Categoría:** Accounting/Localizations/EDI
- **Dependencias:** l10n_jo_edi


## Propósito
Extended features for JoFotara



## Descripción

This module improves the Jordan E-invoicing (JoFotara) by the following:
       1. Adds support for different invoice types and payment methods.
       2. Introduces demo mode.
    



## Modelos

### account.move.send


- Hereda de:

  - account.move.send




- No agrega campos



### account.move


- Hereda de:

  - account.move




- Campos:

  - **l10n_jo_edi_invoice_type** (Selection)


  - **l10n_jo_edi_state** (Selection)





### res.config.settings


- Hereda de:

  - res.config.settings




- Campos:

  - **l10n_jo_edi_demo_mode** (Boolean)





### res.company


- Hereda de:

  - res.company




- Campos:

  - **l10n_jo_edi_demo_mode** (Boolean)







