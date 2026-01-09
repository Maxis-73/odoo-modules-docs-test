# Módulo: Belgium - Accounting

## Información General
- **Nombre técnico:** l10n_be
- **Versión:** 2.0
- **Categoría:** Accounting/Localizations/Account Charts
- **Dependencias:** account, base_iban, base_vat




## Descripción

This is the base module to manage the accounting chart for Belgium in Odoo.

After installing this module, the Configuration wizard for accounting is launched.
    * We have the account templates which can be helpful to generate Charts of Accounts.
    * On that particular wizard, you will be asked to pass the name of the company,
      the chart template to follow, the no. of digits to generate, the code for your
      account and bank account, currency to create journals.

Thus, the pure copy of Chart Template is generated.

Wizards provided by this module:
--------------------------------
    * Partner VAT Intra: Enlist the partners with their related VAT and invoiced
      amounts. Prepares an XML file format.

        **Path to access:** Invoicing/Reporting/Legal Reports/Belgium Statements/Partner VAT Intra
    * Periodical VAT Declaration: Prepares an XML file for Vat Declaration of
      the Main company of the User currently Logged in.

        **Path to access:** Invoicing/Reporting/Legal Reports/Belgium Statements/Periodical VAT Declaration
    * Annual Listing Of VAT-Subjected Customers: Prepares an XML file for Vat
      Declaration of the Main company of the User currently Logged in Based on
      Fiscal year.

        **Path to access:** Invoicing/Reporting/Legal Reports/Belgium Statements/Annual Listing Of VAT-Subjected Customers

    



## Modelos

### account.move


- Hereda de:

  - account.move




- No agrega campos



### account.journal


- Hereda de:

  - account.journal




- Campos:

  - **invoice_reference_model** (Selection)





### account.chart.template


- Hereda de:

  - account.chart.template




- No agrega campos



### account.tax


- Hereda de:

  - account.tax




- Campos:

  - **tax_scope** (Selection)





### account.chart.template


- Hereda de:

  - account.chart.template




- No agrega campos



### account.chart.template


- Hereda de:

  - account.chart.template




- No agrega campos



### res.partner


- Hereda de:

  - res.partner




- No agrega campos





