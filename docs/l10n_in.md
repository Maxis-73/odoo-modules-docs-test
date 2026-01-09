# Módulo: Indian - Accounting

## Información General
- **Nombre técnico:** l10n_in
- **Versión:** 2.0
- **Categoría:** Accounting/Localizations/Account Charts
- **Dependencias:** account_tax_python, base_vat, account_debit_note, account, iap




## Descripción

Indian Accounting: Chart of Account.

Indian accounting chart and localization.

Odoo allows to manage Indian Accounting by providing Two Formats Of Chart of Accounts i.e Indian Chart Of Accounts - Standard and Indian Chart Of Accounts - Schedule VI.

Note: The Schedule VI has been revised by MCA and is applicable for all Balance Sheet made after
31st March, 2011. The Format has done away with earlier two options of format of Balance
Sheet, now only Vertical format has been permitted Which is Supported By Odoo.
  



## Modelos

### uom.uom


- Hereda de:

  - uom.uom




- Campos:

  - **l10n_in_code** (Char) → Indian GST UQC





### res.company


- Hereda de:

  - res.company




- Campos:

  - **l10n_in_upi_id** (Char)


  - **l10n_in_hsn_code_digit** (Selection)


  - **l10n_in_edi_production_env** (Boolean)


  - **l10n_in_pan** (Char)


  - **l10n_in_pan_type** (Char)


  - **l10n_in_gst_state_warning** (Char)





### product.template


- Hereda de:

  - product.template




- Campos:

  - **l10n_in_hsn_code** (Char)


  - **l10n_in_hsn_warning** (Text)





### account.move


- Hereda de:

  - account.move




- Campos:

  - **l10n_in_gst_treatment** (Selection)


  - **l10n_in_state_id** (Many2one) → res.country.state


  - **l10n_in_gstin** (Char)


  - **l10n_in_shipping_bill_number** (Char) → Shipping bill number


  - **l10n_in_shipping_bill_date** (Date) → Shipping bill date


  - **l10n_in_shipping_port_code_id** (Many2one) → l10n_in.port.code


  - **l10n_in_reseller_partner_id** (Many2one) → res.partner


  - **l10n_in_journal_type** (Selection)


  - **l10n_in_warning** (Json)





### l10n_in.port.code


- Hereda de: Base



- Campos:

  - **code** (Char)


  - **name** (Char)


  - **state_id** (Many2one) → res.country.state





### account.tax


- Hereda de:

  - account.tax




- Campos:

  - **l10n_in_reverse_charge** (Boolean) → Reverse charge


  - **l10n_in_tax_type** (Selection)





### res.config.settings


- Hereda de:

  - res.config.settings




- Campos:

  - **group_l10n_in_reseller** (Boolean)


  - **l10n_in_edi_production_env** (Boolean)


  - **module_l10n_in_edi** (Boolean) → Indian Electronic Invoicing


  - **module_l10n_in_edi_ewaybill** (Boolean) → Indian Electronic Waybill


  - **module_l10n_in_gstin_status** (Boolean) → Check GST Number Status


  - **module_l10n_in_withholding** (Boolean) → Indian TDS and TCS


  - **l10n_in_hsn_code_digit** (Selection)


  - **module_l10n_in_enet_batch_payment** (Boolean)





### account.move.line


- Hereda de:

  - account.move.line




- Campos:

  - **l10n_in_hsn_code** (Char)





### account.chart.template


- Hereda de:

  - account.chart.template




- No agrega campos



### iap.account


- Hereda de:

  - iap.account




- No agrega campos



### res.partner


- Hereda de:

  - res.partner




- Campos:

  - **l10n_in_gst_treatment** (Selection)


  - **l10n_in_pan** (Char)


  - **display_pan_warning** (Boolean)


  - **l10n_in_gst_state_warning** (Char)





### res.country.state


- Hereda de:

  - res.country.state




- Campos:

  - **l10n_in_tin** (Char) → TIN Number








## Vistas


### account.move.line

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | account.move.line.list.l10n_in | `l10n_in.view_move_line_tree_hsn_l10n_in` | - |



### l10n_in.port.code

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | l10n_in.port.code.form | `l10n_in.l10n_in_port_code_form_view` | - |
| list | l10n_in.port.code.list | `l10n_in.l10n_in_port_code_tree_view` | - |
| search | l10n_in.port.code.search | `l10n_in.l10n_in_port_code_search_view` | - |



#### Filtros de búsqueda (l10n_in.l10n_in_port_code_search_view)


**Agrupar por:**
- State

