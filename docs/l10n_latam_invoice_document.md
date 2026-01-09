# Módulo: LATAM Document

## Información General
- **Nombre técnico:** l10n_latam_invoice_document
- **Versión:** 1.0
- **Categoría:** Accounting/Localizations
- **Dependencias:** account, account_debit_note


## Propósito
LATAM Document Types



## Descripción

Functional
----------

In some Latinamerica countries, including Argentina and Chile, some accounting transactions like invoices and vendor bills are classified by a document types defined by the government fiscal authorities (In Argentina case AFIP, Chile case SII).

This module is intended to be extended by localizations in order to manage these document types and is an essential information that needs to be displayed in the printed reports and that needs to be easily identified, within the set of invoices as well of account moves.

Each document type have their own rules and sequence number, this last one is integrated with the invoice number and journal sequence in order to be easy for the localization user. In order to support or not this document types a Journal has a new option that lets to use document or not.

Technical
---------

If your localization needs this logic will then need to add this module as dependency and in your localization module extend:

* extend company's _localization_use_documents() method.
* create the data of the document types that exists for the specific country. The document type has a country field





## Modelos

### l10n_latam.document.type


- Hereda de: Base



- Campos:

  - **active** (Boolean)


  - **sequence** (Integer)


  - **country_id** (Many2one) → res.country


  - **name** (Char)


  - **doc_code_prefix** (Char) → Document Code Prefix


  - **code** (Char)


  - **report_name** (Char) → Name on Reports


  - **internal_type** (Selection)





### account.move


- Hereda de:

  - account.move




- Campos:

  - **l10n_latam_available_document_type_ids** (Many2many) → l10n_latam.document.type


  - **l10n_latam_document_type_id** (Many2one) → l10n_latam.document.type


  - **l10n_latam_document_number** (Char)


  - **l10n_latam_use_documents** (Boolean)


  - **l10n_latam_manual_document_number** (Boolean)


  - **l10n_latam_document_type_id_code** (Char)





### account.journal


- Hereda de:

  - account.journal




- Campos:

  - **l10n_latam_use_documents** (Boolean) → Use Documents?


  - **l10n_latam_company_use_documents** (Boolean)





### account.move.line


- Hereda de:

  - account.move.line




- Campos:

  - **l10n_latam_document_type_id** (Many2one)





### res.company


- Hereda de:

  - res.company




- No agrega campos



### account.chart.template


- Hereda de:

  - account.chart.template




- No agrega campos






## Vistas


### account.journal

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | account.journal.form | `l10n_latam_invoice_document.view_account_journal_form` | account.view_account_journal_form |



### l10n_latam.document.type

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | l10n_latam.document.type.form | `l10n_latam_invoice_document.view_document_type_form` | - |
| list | l10n_latam.document.type.list | `l10n_latam_invoice_document.view_document_type_tree` | - |
| search | l10n_latam.document.type.filter | `l10n_latam_invoice_document.view_document_type_filter` | - |



#### Filtros de búsqueda (l10n_latam_invoice_document.view_document_type_filter)

**Filtros:**
- **Active** (`[('active','=',True)]`)
- **Archived** (`[('active','=',False)]`)


**Agrupar por:**
- Internal Type
- Localization


### account.move

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | account.move.form | `l10n_latam_invoice_document.view_move_form` | account.view_move_form |



### account.invoice.report

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| search | account.invoice.report.search | `l10n_latam_invoice_document.view_account_invoice_report_search` | account.view_account_invoice_report_search |



#### Filtros de búsqueda (l10n_latam_invoice_document.view_account_invoice_report_search)

**Filtros:**
- **user**


**Agrupar por:**
- Document Type

