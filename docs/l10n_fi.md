# Módulo: Finnish Localization

## Información General
- **Nombre técnico:** l10n_fi
- **Versión:** 13.0.2
- **Categoría:** Accounting/Localizations/Account Charts
- **Dependencias:** base_iban, base_vat, account




## Descripción

This is the Odoo module to manage the accounting in Finland.

After installing this module, you'll have access to:
    * Finnish chart of account
    * Fiscal positions
    * Invoice Payment Reference Types (Finnish Standard Reference & Finnish Creditor Reference (RF))
    * Finnish Reference format for Sale Orders

Set the payment reference type from the Sales Journal.
    



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





### res.partner


- Hereda de:

  - res.partner




- No agrega campos





