# Módulo: Czech - Accounting

## Información General
- **Nombre técnico:** l10n_cz
- **Versión:** 1.1
- **Categoría:** Accounting/Localizations/Account Charts
- **Dependencias:** account, base_iban, base_vat




## Descripción

Czech accounting chart and localization.  With Chart of Accounts with taxes and basic fiscal positions.

Tento modul definuje:

- Českou účetní osnovu za rok 2020

- Základní sazby pro DPH z prodeje a nákupu

- Základní fiskální pozice pro českou legislativu
    



## Modelos

### account.move


- Hereda de:

  - account.move




- Campos:

  - **taxable_supply_date** (Date)





### account.chart.template


- Hereda de:

  - account.chart.template




- No agrega campos



### account.move.line


- Hereda de:

  - account.move.line




- No agrega campos



### res.company


- Hereda de:

  - res.company




- Campos:

  - **trade_registry** (Char)





### base.document.layout


- Hereda de:

  - base.document.layout




- Campos:

  - **account_fiscal_country_id** (Many2one)


  - **company_registry** (Char)







