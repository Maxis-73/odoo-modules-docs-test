# Módulo: Indonesia E-faktur

## Información General
- **Nombre técnico:** l10n_id_efaktur
- **Versión:** 1.0
- **Categoría:** Accounting/Localizations/EDI
- **Dependencias:** l10n_id




## Descripción

E-Faktur Menu(Indonesia)
Format: 010.000-16.00000001
* 2 (dua) digit pertama adalah Kode Transaksi
* 1 (satu) digit berikutnya adalah Kode Status
* 3 (tiga) digit berikutnya adalah Kode Cabang
* 2 (dua) digit pertama adalah Tahun Penerbitan
* 8 (delapan) digit berikutnya adalah Nomor Urut

To be able to export customer invoices as e-Faktur,
you need to put the ranges of numbers you were assigned
by the government in Accounting > Customers > e-Faktur

When you validate an invoice, where the partner has the ID PKP
field checked, a tax number will be assigned to that invoice.
Afterwards, you can filter the invoices still to export in the
invoices list and click on Action > Download e-Faktur to download
the csv and upload it to the site of the government.

You can replace an already sent invoice by another by indicating
the replaced invoice and the new one and you can reset an invoice
you have not already sent to the government to reuse its number.
    



## Modelos

### l10n_id_efaktur.document


- Hereda de:


  - mail.thread

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

  - **l10n_id_tax_number** (Char)


  - **l10n_id_replace_invoice_id** (Many2one) → account.move


  - **l10n_id_efaktur_document** (Many2one) → l10n_id_efaktur.document


  - **l10n_id_kode_transaksi** (Selection)


  - **l10n_id_efaktur_range** (Many2one) → l10n_id_efaktur.efaktur.range


  - **l10n_id_need_kode_transaksi** (Boolean)


  - **l10n_id_available_range_count** (Integer)


  - **l10n_id_show_kode_transaksi** (Boolean)





### l10n_id_efaktur.efaktur.range


- Hereda de: Base



- Campos:

  - **company_id** (Many2one) → res.company


  - **max** (Char)


  - **min** (Char)


  - **available** (Integer)


  - **next_num** (Integer)





### res.partner


- Hereda de:

  - res.partner




- Campos:

  - **l10n_id_pkp** (Boolean)


  - **l10n_id_nik** (Char)


  - **l10n_id_kode_transaksi** (Selection)








## Vistas


### l10n_id_efaktur.efaktur.range

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | l10n_id_efaktur.efaktur.range.list.view | `l10n_id_efaktur.efaktur_tree_view` | - |



### l10n_id_efaktur.document

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | l10n_id.efaktur.document.form.view | `l10n_id_efaktur.l10n_id_efaktur_document_form_view` | - |
| list | l10n_id.efaktur.document.list.view | `l10n_id_efaktur.l10n_id_efaktur_document_list_view` | - |
| search | l10n_id.efaktur.document.filter.view | `l10n_id_efaktur.l10n_id_efaktur_document_filter_view` | - |



#### Botones (l10n_id_efaktur.l10n_id_efaktur_document_form_view)
- **Download** (object) - Grupos: `account.group_account_invoice`
- **Regenerate File** (object) - Grupos: `account.group_account_invoice`


#### Filtros de búsqueda (l10n_id_efaktur.l10n_id_efaktur_document_filter_view)

**Filtros:**
- **Active** (`[('active', '=', True)]`)
- **Inactive** (`[('active', '=', False)]`)

