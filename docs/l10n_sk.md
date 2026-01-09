# Módulo: Slovak - Accounting

## Información General
- **Nombre técnico:** l10n_sk
- **Versión:** 1.0
- **Categoría:** Accounting/Localizations/Account Charts
- **Dependencias:** base_iban, base_vat, account




## Descripción

Slovakia accounting chart and localization: Chart of Accounts 2020, basic VAT rates +
fiscal positions.

Tento modul definuje:
• Slovenskú účtovú osnovu za rok 2020

• Základné sadzby pre DPH z predaja a nákupu

• Základné fiškálne pozície pre slovenskú legislatívu


Pre viac informácií kontaktujte info@26house.com alebo navštívte https://www.26house.com.

    



## Modelos

### account.chart.template


- Hereda de:

  - account.chart.template




- No agrega campos



### account.move


- Hereda de:

  - account.move




- Campos:

  - **taxable_supply_date** (Date)





### res.company


- Hereda de:

  - res.company




- Campos:

  - **trade_registry** (Char)


  - **income_tax_id** (Char)





### base.document.layout


- Hereda de:

  - base.document.layout




- Campos:

  - **account_fiscal_country_id** (Many2one)


  - **company_registry** (Char)


  - **income_tax_id** (Char)







