# Módulo: Türkiye - Accounting

## Información General
- **Nombre técnico:** l10n_tr
- **Versión:** 1.3
- **Categoría:** Accounting/Localizations/Account Charts
- **Dependencias:** account




## Descripción

This is the base module to manage the accounting chart for Türkiye in Odoo

Türkiye accounting basic charts and localizations
-------------------------------------------------
Activates:

- Chart of Accounts
- Taxes
- Tax Report
    



## Modelos

### account.chart.template


- Hereda de:

  - account.chart.template




- No agrega campos



### account.journal


- Hereda de:

  - account.journal




- Campos:

  - **l10n_tr_default_sales_return_account_id** (Many2one) → account.account





### product.template


- Hereda de:

  - product.template




- Campos:

  - **l10n_tr_default_sales_return_account_id** (Many2one) → account.account





### account.move.line


- Hereda de:

  - account.move.line




- No agrega campos





