# Módulo: Indonesia E-faktur (Coretax)

## Información General
- **Nombre técnico:** l10n_id_efaktur_coretax
- **Versión:** 1.0
- **Categoría:** Accounting/Localizations/EDI
- **Dependencias:** l10n_id, l10n_id_efaktur




## Descripción

        E-invoicing feature provided by DJP (Indonesian Tax Office). As of January 1st 2025,
        Indonesia is using CoreTax system, which changes the file format and content of E-Faktur.
        We're changing from CSV files into XML.
        At the same time, due to tax regulation changes back and forth, for general E-Faktur now,
        TaxBase (DPP) has to be mulitplied by factor of 11/12 while multiplied to tax of 12% which
        is resulting to 11%.
    



## Modelos

### uom.uom


- Hereda de:

  - uom.uom




- Campos:

  - **l10n_id_uom_code** (Many2one) → l10n_id_efaktur_coretax.uom.code





### product.template


- Hereda de:

  - product.template




- Campos:

  - **l10n_id_product_code** (Many2one) → l10n_id_efaktur_coretax.product.code





### l10n_id_efaktur_coretax.document


- Hereda de:


  - mail.thread.main.attachment

  - mail.activity.mixin





- Campos:

  - **name** (Char)


  - **company_id** (Many2one) → res.company


  - **active** (Boolean)


  - **invoice_ids** (One2many) → account.move


  - **attachment_id** (Many2one) → ir.attachment





### account.move


- Hereda de:

  - account.move




- Campos:

  - **l10n_id_coretax_add_info_07** (Selection)


  - **l10n_id_coretax_facility_info_07** (Selection)


  - **l10n_id_coretax_add_info_08** (Selection)


  - **l10n_id_coretax_facility_info_08** (Selection)


  - **l10n_id_kode_transaksi** (Selection)


  - **l10n_id_coretax_efaktur_available** (Boolean)


  - **l10n_id_coretax_document** (Many2one) → l10n_id_efaktur_coretax.document


  - **l10n_id_coretax_custom_doc** (Char)





### l10n_id_efaktur_coretax.uom.code


- Hereda de: Base



- Campos:

  - **code** (Char)


  - **name** (Char)





### account.move.line


- Hereda de:

  - account.move.line




- No agrega campos



### l10n_id_efaktur_coretax.product.code


- Hereda de: Base



- Campos:

  - **code** (Char)


  - **description** (Text)





### res.partner


- Hereda de:

  - res.partner




- Campos:

  - **l10n_id_kode_transaksi** (Selection)


  - **l10n_id_tku** (Char)


  - **l10n_id_buyer_document_type** (Selection)


  - **l10n_id_buyer_document_number** (Char)








## Vistas


### l10n_id_efaktur_coretax.product.code

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | product.code.list | `l10n_id_efaktur_coretax.produc_code_list` | - |



### l10n_id_efaktur_coretax.uom.code

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | uom.code.list | `l10n_id_efaktur_coretax.uom_code_list` | - |



### l10n_id_efaktur_coretax.document

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | l10n_id.efaktur_coretax.document.form.view | `l10n_id_efaktur_coretax.l10n_id_efaktur_document_form_view` | - |
| list | l10n_id.efaktur_coretax.document.list.view | `l10n_id_efaktur_coretax.l10n_id_efaktur_document_list_view` | - |
| search | l10n_id.efaktur_coretax.document.filter.view | `l10n_id_efaktur_coretax.l10n_id_efaktur_document_filter_view` | - |



#### Botones (l10n_id_efaktur_coretax.l10n_id_efaktur_document_form_view)
- **Download** (object) - Grupos: `account.group_account_invoice`
- **Regenerate File** (object) - Grupos: `account.group_account_invoice`


#### Filtros de búsqueda (l10n_id_efaktur_coretax.l10n_id_efaktur_document_filter_view)

**Filtros:**
- **Active** (`[('active', '=', True)]`)
- **Inactive** (`[('active', '=', False)]`)

