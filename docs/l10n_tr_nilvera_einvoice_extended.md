# Módulo: Türkiye - Nilvera E-Invoice Extended

## Información General
- **Nombre técnico:** l10n_tr_nilvera_einvoice_extended
- **Versión:** 1.0
- **Categoría:** Accounting/Accounting
- **Dependencias:** l10n_tr_nilvera_einvoice, contacts




## Descripción

This module enhances the core Nilvera integration by adding additional invoice scenarios and types required for Turkish e-Invoicing compliance.

Features include:
    1.Support for invoice scenarios: Basic, Export, and Public Sector
    2.Support for invoice types: Sales, Withholding, Tax Exempt, and Registered for Export
    3.Configuration of withholding reasons and exemption reasons
    4.Addition of Tax Offices.
    



## Modelos

### account.move.send


- Hereda de:

  - account.move.send




- No agrega campos



### product.product


- Hereda de:

  - product.product




- Campos:

  - **l10n_tr_ctsp_number** (Char)





### product.template


- Hereda de:

  - product.template




- Campos:

  - **l10n_tr_ctsp_number** (Char)





### l10n_tr_nilvera_einvoice_extended.account.tax.code


- Hereda de: Base



- Campos:

  - **name** (Char)


  - **code** (Integer)


  - **percentage** (Float)


  - **code_type** (Selection)





### account.move


- Hereda de:

  - account.move




- Campos:

  - **l10n_tr_gib_invoice_scenario** (Selection)


  - **l10n_tr_gib_invoice_type** (Selection)


  - **l10n_tr_is_export_invoice** (Boolean)


  - **l10n_tr_shipping_type** (Selection)


  - **l10n_tr_exemption_code_id** (Many2one) → l10n_tr_nilvera_einvoice_extended.account.tax.code


  - **l10n_tr_exemption_code_domain_list** (Binary)


  - **l10n_tr_nilvera_customer_status** (Selection)





### account.chart.template


- Hereda de:

  - account.chart.template




- No agrega campos



### account.tax


- Hereda de:

  - account.tax




- Campos:

  - **l10n_tr_tax_withholding_code_id** (Many2one) → l10n_tr_nilvera_einvoice_extended.account.tax.code





### res.config.settings


- Hereda de:

  - res.config.settings




- Campos:

  - **l10n_tr_nilvera_export_alias** (Char)





### account.move.line


- Hereda de:

  - account.move.line




- Campos:

  - **l10n_tr_ctsp_number** (Char)





### account.edi.xml.ubl.tr


- Hereda de:

  - account.edi.xml.ubl.tr




- No agrega campos



### l10n_tr_nilvera_einvoice_extended.tax.office


- Hereda de: Base



- Campos:

  - **name** (Char)


  - **code** (Integer)


  - **state_id** (Many2one) → res.country.state


  - **state_code** (Char)





### res.company


- Hereda de:

  - res.company




- Campos:

  - **l10n_tr_tax_office_id** (Many2one)


  - **l10n_tr_nilvera_export_alias** (Char)





### res.partner


- Hereda de:

  - res.partner




- Campos:

  - **l10n_tr_tax_office_id** (Many2one) → l10n_tr_nilvera_einvoice_extended.tax.office








## Vistas


### l10n_tr_nilvera_einvoice_extended.tax.office

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | l10n_tr_nilvera_einvoice_extended.tax.office.list | `l10n_tr_nilvera_einvoice_extended.l10n_tr_nilvera_einvoice_extended_tax_office_view_list` | - |
| form | l10n_tr_nilvera_einvoice_extended.tax.office.form | `l10n_tr_nilvera_einvoice_extended.l10n_tr_nilvera_einvoice_extended_tax_office_view_form` | - |



### l10n_tr_nilvera_einvoice_extended.account.tax.code

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | l10n_tr_nilvera_einvoice_extended.account.tax.code.list | `l10n_tr_nilvera_einvoice_extended.l10n_tr_nilvera_einvoice_extended_account_tax_code_view_list` | - |
| form | l10n_tr_nilvera_einvoice_extended.account.tax.code.form | `l10n_tr_nilvera_einvoice_extended.l10n_tr_nilvera_einvoice_extended_account_tax_code_view_form` | - |


