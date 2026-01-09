# Módulo: Argentina - Accounting

## Información General
- **Nombre técnico:** l10n_ar
- **Versión:** 3.7
- **Categoría:** Accounting/Localizations/Account Charts
- **Dependencias:** l10n_latam_invoice_document, l10n_latam_base, account




## Descripción

Functional
----------

This module add accounting features for the Argentinean localization, which represent the minimal configuration needed for a company  to operate in Argentina and under the AFIP (Administración Federal de Ingresos Públicos) regulations and guidelines.

Follow the next configuration steps for Production:

1. Go to your company and configure your VAT number and AFIP Responsibility Type
2. Go to Accounting / Settings and set the Chart of Account that you will like to use.
3. Create your Sale journals taking into account AFIP POS info.

Demo data for testing:

* 3 companies were created, one for each AFIP responsibility type with the respective Chart of Account installed. Choose the company that fix you in order to make tests:

  * (AR) Responsable Inscripto
  * (AR) Exento
  * (AR) Monotributo

* Journal sales configured to Pre printed and Expo invoices in all companies
* Invoices and other documents examples already validated in “(AR) Responsable Inscripto” company
* Partners example for the different responsibility types:

  * ADHOC (IVA Responsable Inscripto)
  * Servicios Globales (IVA Sujeto Exento)
  * Gritti (Monotributo)
  * Montana Sur. IVA Liberado in Zona Franca
  * Barcelona food (Cliente del Exterior)
  * Odoo (Proveedor del Exterior)

Highlights:

* Chart of account will not be automatically installed, each CoA Template depends on the AFIP Responsibility of the company, you will need to install the CoA for your needs.
* No sales journals will be generated when installing a CoA, you will need to configure your journals manually.
* The Document type will be properly pre selected when creating an invoice depending on the fiscal responsibility of the issuer and receiver of the document and the related journal.
* A CBU account type has been added and also CBU Validation


Technical
---------

This module adds both models and fields that will be eventually used for the electronic invoice module. Here is a summary of the main features:

Master Data:

* Chart of Account: one for each AFIP responsibility that is related to a legal entity:

  * Responsable Inscripto (RI)
  * Exento (EX)
  * Monotributo (Mono)

* Argentinean Taxes and Account Tax Groups (VAT taxes with the existing aliquots and other types)
* AFIP Responsibility Types
* Fiscal Positions (in order to map taxes)
* Legal Documents Types in Argentina
* Identification Types valid in Argentina.
* Country AFIP codes and Country VAT codes for legal entities, natural persons and others
* Currency AFIP codes
* Unit of measures AFIP codes
* Partners: Consumidor Final and AFIP




## Modelos

### uom.uom


- Hereda de:

  - uom.uom




- Campos:

  - **l10n_ar_afip_code** (Char) → Code





### res.currency


- Hereda de:

  - res.currency




- Campos:

  - **l10n_ar_afip_code** (Char) → AFIP Code





### res.partner.bank


- Hereda de:

  - res.partner.bank




- No agrega campos



### res.country


- Hereda de:

  - res.country




- Campos:

  - **l10n_ar_afip_code** (Char) → AFIP Code


  - **l10n_ar_natural_vat** (Char) → Natural Person VAT


  - **l10n_ar_legal_entity_vat** (Char) → Legal Entity VAT


  - **l10n_ar_other_vat** (Char) → Other VAT





### l10n_ar.afip.responsibility.type


- Hereda de: Base



- Campos:

  - **name** (Char)


  - **sequence** (Integer)


  - **code** (Char)


  - **active** (Boolean)





### l10n_latam.document.type


- Hereda de:

  - l10n_latam.document.type




- Campos:

  - **l10n_ar_letter** (Selection)


  - **purchase_aliquots** (Selection)





### account.chart.template


- Hereda de:

  - account.chart.template




- No agrega campos



### account.move


- Hereda de:

  - account.move




- Campos:

  - **l10n_ar_afip_responsibility_type_id** (Many2one) → l10n_ar.afip.responsibility.type


  - **l10n_ar_afip_concept** (Selection)


  - **l10n_ar_afip_service_start** (Date)


  - **l10n_ar_afip_service_end** (Date)





### account.fiscal.position


- Hereda de:

  - account.fiscal.position




- Campos:

  - **l10n_ar_afip_responsibility_type_ids** (Many2many) → l10n_ar.afip.responsibility.type





### account.journal


- Hereda de:

  - account.journal




- Campos:

  - **l10n_ar_afip_pos_system** (Selection)


  - **l10n_ar_afip_pos_number** (Integer) → AFIP POS Number


  - **company_partner** (Many2one) → res.partner


  - **l10n_ar_afip_pos_partner_id** (Many2one) → res.partner


  - **l10n_ar_is_pos** (Boolean)





### account.chart.template


- Hereda de:

  - account.chart.template




- No agrega campos



### l10n_latam.identification.type


- Hereda de:

  - l10n_latam.identification.type




- Campos:

  - **l10n_ar_afip_code** (Char) → AFIP Code





### account.move.line


- Hereda de:

  - account.move.line




- No agrega campos



### res.company


- Hereda de:

  - res.company




- Campos:

  - **l10n_ar_gross_income_number** (Char)


  - **l10n_ar_gross_income_type** (Selection)


  - **l10n_ar_afip_responsibility_type_id** (Many2one)


  - **l10n_ar_company_requires_vat** (Boolean)


  - **l10n_ar_afip_start_date** (Date) → Activities Start





### account.chart.template


- Hereda de:

  - account.chart.template




- No agrega campos



### account.chart.template


- Hereda de:

  - account.chart.template




- No agrega campos



### account.tax.group


- Hereda de:

  - account.tax.group




- Campos:

  - **l10n_ar_tribute_afip_code** (Selection)


  - **l10n_ar_vat_afip_code** (Selection)





### res.partner


- Hereda de:

  - res.partner




- Campos:

  - **l10n_ar_vat** (Char)


  - **l10n_ar_formatted_vat** (Char)


  - **l10n_ar_gross_income_number** (Char) → Gross Income Number


  - **l10n_ar_gross_income_type** (Selection)


  - **l10n_ar_afip_responsibility_type_id** (Many2one) → l10n_ar.afip.responsibility.type








## Vistas


### uom.uom

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | uom.uom.list | `l10n_ar.product_uom_tree_view` | uom.product_uom_tree_view |



### l10n_ar.afip.responsibility.type

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | afip.responsibility.type.form | `l10n_ar.view_afip_responsibility_type_form` | - |
| list | afip.responsibility.type.list | `l10n_ar.view_afip_responsibility_type_tree` | - |



### account.invoice.report

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| search | account.invoice.report.search | `l10n_ar.view_account_invoice_report_search_inherit` | account.view_account_invoice_report_search |



#### Filtros de búsqueda (l10n_ar.view_account_invoice_report_search_inherit)

**Filtros:**
- **With Document** (`[('l10n_latam_document_type_id', '!=', False)]`)
- **Accounting Date: This Year** (`[('date', '<', (context_today() + relativedelta(years=1, month=1, day=1)).strftime('%Y-%m-%d')), ('date', '>=', (context_today() + relativedelta(month=1, day=1)).strftime('%Y-%m-%d'))]`)
- **user**


**Agrupar por:**
- State
- Account

