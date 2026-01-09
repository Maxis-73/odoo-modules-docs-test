# Módulo: Ecuadorian Accounting

## Información General
- **Nombre técnico:** l10n_ec
- **Versión:** 3.9
- **Categoría:** Accounting/Localizations/Account Charts
- **Dependencias:** base, base_iban, account_debit_note, l10n_latam_invoice_document, l10n_latam_base, account




## Descripción

Functional
----------

This module adds accounting features for Ecuadorian localization, which
represent the minimum requirements to operate a business in Ecuador in compliance
with local regulation bodies such as the ecuadorian tax authority -SRI- and the
Superintendency of Companies -Super Intendencia de Compañías-

Follow the next configuration steps:
1. Go to your company and configure your country as Ecuador
2. Install the invoicing or accounting module, everything will be handled automatically

Highlights:
* Ecuadorian chart of accounts will be automatically installed, based on example provided by Super Intendencia de Compañías
* List of taxes (including withholds) will also be installed, you can switch off the ones your company doesn't use
* Fiscal position, document types, list of local banks, list of local states, etc, will also be installed

Technical
---------
Master Data:
* Chart of Accounts, based on recomendation by Super Cías
* Ecuadorian Taxes, Tax Tags, and Tax Groups
* Ecuadorian Fiscal Positions
* Document types (there are about 41 purchase documents types in Ecuador)
* Identification types
* Ecuador banks
* Partners: Consumidor Final, SRI, IESS, and also basic VAT validation




## Modelos

### l10n_latam.document.type


- Hereda de:

  - l10n_latam.document.type




- Campos:

  - **internal_type** (Selection)


  - **l10n_ec_check_format** (Boolean)





### l10n_ec.sri.payment


- Hereda de: Base



- Campos:

  - **name** (Char) → Name


  - **code** (Char) → Code


  - **active** (Boolean) → Active





### account.chart.template


- Hereda de:

  - account.chart.template




- No agrega campos



### account.move


- Hereda de:

  - account.move




- Campos:

  - **l10n_ec_sri_payment_id** (Many2one) → l10n_ec.sri.payment





### account.journal


- Hereda de:

  - account.journal




- Campos:

  - **l10n_ec_require_emission** (Boolean)


  - **l10n_ec_entity** (Char)


  - **l10n_ec_emission** (Char)


  - **l10n_ec_emission_address_id** (Many2one) → res.partner





### account.tax


- Hereda de:

  - account.tax




- Campos:

  - **l10n_ec_code_base** (Char)


  - **l10n_ec_code_applied** (Char)


  - **l10n_ec_code_ats** (Char)





### res.company


- Hereda de:

  - res.company




- No agrega campos



### account.tax.group


- Hereda de:

  - account.tax.group




- Campos:

  - **l10n_ec_type** (Selection)





### res.partner


- Hereda de:

  - res.partner




- Campos:

  - **l10n_ec_vat_validation** (Char)








## Vistas


### l10n_ec.sri.payment

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | l10n_ec.sri.payment.form | `l10n_ec.view_payment_method_form` | - |
| list | l10n_ec.sri.payment.list | `l10n_ec.view_payment_method_tree` | - |


