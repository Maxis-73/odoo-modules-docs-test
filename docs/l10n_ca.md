# Módulo: Canada - Accounting

## Información General
- **Nombre técnico:** l10n_ca
- **Versión:** 1.1
- **Categoría:** Accounting/Localizations/Account Charts
- **Dependencias:** account, base_iban




## Descripción

This is the module to manage the Canadian accounting chart in Odoo.

Canadian accounting charts and localizations.

Fiscal positions
----------------

When considering taxes to be applied, it is the province where the delivery occurs that matters.
Therefore we decided to implement the most common case in the fiscal positions: delivery is the
responsibility of the vendor and done at the customer location.

Some examples:

1) You have a customer from another province and you deliver to his location.
On the customer, set the fiscal position to his province.

2) You have a customer from another province. However this customer comes to your location
with their truck to pick up products. On the customer, do not set any fiscal position.

3) An international vendor doesn't charge you any tax. Taxes are charged at customs
by the customs broker. On the vendor, set the fiscal position to International.

4) An international vendor charge you your provincial tax. They are registered with your
position.
    



## Modelos

### account.chart.template


- Hereda de:

  - account.chart.template




- No agrega campos



### res.company


- Hereda de:

  - res.company




- Campos:

  - **l10n_ca_pst** (Char)





### base.document.layout


- Hereda de:

  - base.document.layout




- Campos:

  - **l10n_ca_pst** (Char)


  - **account_fiscal_country_id** (Many2one)





### res.partner


- Hereda de:

  - res.partner




- Campos:

  - **l10n_ca_pst** (Char)







