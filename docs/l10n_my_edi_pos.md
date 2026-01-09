# Módulo: Malaysia - E-invoicing (POS)

## Información General
- **Nombre técnico:** l10n_my_edi_pos
- **Versión:** 1.0
- **Categoría:** Accounting/Localizations/EDI
- **Dependencias:** l10n_my_edi_extended, point_of_sale


## Propósito
Consolidated E-invoicing using MyInvois



## Descripción

    This modules allows the user to send consolidated invoices to the MyInvois system when using the POS app.
    



## Modelos

### myinvois.document


- Hereda de:


  - mail.thread

  - mail.activity.mixin

  - sequence.mixin





- Campos:

  - **name** (Char)


  - **active** (Boolean)


  - **company_id** (Many2one) → res.company


  - **currency_id** (Many2one) → res.currency


  - **company_currency_id** (Many2one)


  - **myinvois_issuance_date** (Date)


  - **myinvois_file_id** (Many2one) → ir.attachment


  - **myinvois_file** (Binary)


  - **myinvois_state** (Selection)


  - **myinvois_error_document_hash** (Char)


  - **myinvois_retry_at** (Char)


  - **myinvois_exemption_reason** (Char)


  - **myinvois_custom_form_reference** (Char)


  - **myinvois_submission_uid** (Char)


  - **myinvois_external_uuid** (Char)


  - **myinvois_validation_time** (Datetime)


  - **myinvois_document_long_id** (Char)


  - **invoice_ids** (Many2many) → account.move





### account.edi.xml.ubl_myinvois_my


- Hereda de:

  - account.edi.xml.ubl_myinvois_my




- No agrega campos



### myinvois.document


- Hereda de:

  - myinvois.document




- Campos:

  - **pos_order_ids** (Many2many) → pos.order


  - **pos_config_id** (Many2one) → pos.config


  - **linked_order_count** (Integer)


  - **pos_order_date_range** (Char)





### pos.order


- Hereda de:

  - pos.order




- Campos:

  - **consolidated_invoice_ids** (Many2many) → myinvois.document





### account.tax


- Hereda de:

  - account.tax




- Campos:

  - **l10n_my_tax_exemption_reason** (Char)








## Vistas


### myinvois.document

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | myinvois.document.form.view | `l10n_my_edi_pos.myinvois_document_form_view` | - |
| list | myinvois.document.list.view | `l10n_my_edi_pos.myinvois_document_list_view` | - |



#### Botones (l10n_my_edi_pos.myinvois_document_form_view)
- **Submit To MyInvois** (object)
- **Update Submission Status** (object)
- **Cancel Submission** (object)


### myinvois.document.status.update.wizard

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | myinvois.document.status.update.wizard.form | `l10n_my_edi_pos.myinvois_document_status_update_form` | - |



#### Botones (l10n_my_edi_pos.myinvois_document_status_update_form)
- **Update Document** (object)


### myinvois.consolidate.invoice.wizard

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | myinvois.consolidate.invoice.wizard.form | `l10n_my_edi_pos.myinvois_consolidate_invoice_wizard_form` | - |



#### Botones (l10n_my_edi_pos.myinvois_consolidate_invoice_wizard_form)
- **Create Consolidated Invoices** (object)

