# Módulo: Spain - Facturae EDI

## Información General
- **Nombre técnico:** l10n_es_edi_facturae
- **Versión:** 1.0
- **Categoría:** Accounting/Localizations/EDI
- **Dependencias:** certificate, l10n_es




## Descripción

This module create the Facturae file required to send the invoices information to the General State Administrations.
It allows the export and signature of the signing of Facturae files.
The current version of Facturae supported is the 3.2.2

for more informations, see https://www.facturae.gob.es/face/Paginas/FACE.aspx
    



## Modelos

### uom.uom


- Hereda de:

  - uom.uom




- Campos:

  - **l10n_es_edi_facturae_uom_code** (Selection)





### account.move.send


- Hereda de:

  - account.move.send




- No agrega campos



### account.move


- Hereda de:

  - account.move




- Campos:

  - **l10n_es_edi_facturae_xml_id** (Many2one) → ir.attachment


  - **l10n_es_edi_facturae_xml_file** (Binary)


  - **l10n_es_edi_facturae_reason_code** (Selection)


  - **l10n_es_invoicing_period_start_date** (Date)


  - **l10n_es_invoicing_period_end_date** (Date)


  - **l10n_es_payment_means** (Selection)





### account.tax


- Hereda de:

  - account.tax




- Campos:

  - **l10n_es_edi_facturae_tax_type** (Selection)





### res.company


- Hereda de:

  - res.company




- Campos:

  - **l10n_es_edi_facturae_residence_type** (Char)


  - **l10n_es_edi_facturae_certificate_ids** (One2many) → certificate.certificate





### certificate.certificate


- Hereda de:

  - certificate.certificate




- Campos:

  - **scope** (Selection)





### account.chart.template


- Hereda de:

  - account.chart.template




- No agrega campos



### l10n_es_edi_facturae.ac_role_type


- Hereda de: Base



- Campos:

  - **code** (Char)


  - **name** (Char)





### res.partner


- Hereda de:

  - res.partner




- Campos:

  - **invoice_edi_format** (Selection)


  - **type** (Selection)


  - **l10n_es_edi_facturae_ac_center_code** (Char)


  - **l10n_es_edi_facturae_ac_role_type_ids** (Many2many) → l10n_es_edi_facturae.ac_role_type


  - **l10n_es_edi_facturae_ac_physical_gln** (Char)


  - **l10n_es_edi_facturae_ac_logical_operational_point** (Char)


  - **l10n_es_edi_facturae_residence_type** (Char)








## Vistas


### uom.category

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | uom.category.form.inherit.l10n_es_edi_facturae | `l10n_es_edi_facturae.product_uom_categ_form_view_inherit_l10n_es_edi_facturae` | uom.product_uom_categ_form_view |


