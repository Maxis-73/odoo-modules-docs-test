# Módulo: Peru - Accounting

## Información General
- **Nombre técnico:** l10n_pe
- **Versión:** 3.0
- **Categoría:** Accounting/Localizations/Account Charts
- **Dependencias:** base_vat, base_address_extended, l10n_latam_base, l10n_latam_invoice_document, account_debit_note, account






## Modelos

### account.chart.template


- Hereda de:

  - account.chart.template




- No agrega campos



### res.city


- Hereda de:

  - res.city




- Campos:

  - **l10n_pe_code** (Char) → Code





### l10n_pe.res.city.district


- Hereda de: Base



- Campos:

  - **name** (Char)


  - **city_id** (Many2one) → res.city


  - **code** (Char)





### account.move


- Hereda de:

  - account.move




- No agrega campos



### l10n_latam.identification.type


- Hereda de:

  - l10n_latam.identification.type




- Campos:

  - **l10n_pe_vat_code** (Char)





### account.tax


- Hereda de:

  - account.tax




- Campos:

  - **l10n_pe_edi_tax_code** (Selection)


  - **l10n_pe_edi_unece_category** (Selection)


  - **l10n_pe_edi_isc_type** (Selection)





### res.bank


- Hereda de:

  - res.bank




- Campos:

  - **l10n_pe_edi_code** (Char) → Code (PE)





### res.company


- Hereda de:

  - res.company




- No agrega campos



### res.partner


- Hereda de:

  - res.partner




- Campos:

  - **l10n_pe_district** (Many2one) → l10n_pe.res.city.district


  - **l10n_pe_district_name** (Char)







