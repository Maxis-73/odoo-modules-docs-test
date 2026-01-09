# Módulo: Vietnam - E-invoicing

## Información General
- **Nombre técnico:** l10n_vn_edi_viettel
- **Versión:** 1.0
- **Categoría:** Accounting/Localizations/EDI
- **Dependencias:** l10n_vn


## Propósito
E-invoicing using SInvoice by Viettel



## Descripción

Vietnam - E-invoicing
Using SInvoice by Viettel
    



## Modelos

### account.move.send


- Hereda de:

  - account.move.send




- No agrega campos



### l10n_vn_edi_viettel.sinvoice.template


- Hereda de: Base



- Campos:

  - **name** (Char)


  - **template_invoice_type** (Selection)


  - **invoice_symbols_ids** (One2many) → l10n_vn_edi_viettel.sinvoice.symbol





### l10n_vn_edi_viettel.sinvoice.symbol


- Hereda de: Base



- Campos:

  - **name** (Char)


  - **invoice_template_id** (Many2one) → l10n_vn_edi_viettel.sinvoice.template





### account.move


- Hereda de:

  - account.move




- Campos:

  - **l10n_vn_edi_invoice_state** (Selection)


  - **l10n_vn_edi_invoice_transaction_id** (Char)


  - **l10n_vn_edi_invoice_symbol** (Many2one) → l10n_vn_edi_viettel.sinvoice.symbol


  - **l10n_vn_edi_invoice_number** (Char)


  - **l10n_vn_edi_reservation_code** (Char)


  - **l10n_vn_edi_issue_date** (Datetime)


  - **l10n_vn_edi_sinvoice_file_id** (Many2one) → ir.attachment


  - **l10n_vn_edi_sinvoice_file** (Binary)


  - **l10n_vn_edi_sinvoice_xml_file_id** (Many2one) → ir.attachment


  - **l10n_vn_edi_sinvoice_xml_file** (Binary)


  - **l10n_vn_edi_sinvoice_pdf_file_id** (Many2one) → ir.attachment


  - **l10n_vn_edi_sinvoice_pdf_file** (Binary)


  - **l10n_vn_edi_agreement_document_name** (Char)


  - **l10n_vn_edi_agreement_document_date** (Datetime)


  - **l10n_vn_edi_adjustment_type** (Selection)


  - **l10n_vn_edi_replacement_origin_id** (Many2one) → account.move


  - **l10n_vn_edi_reversed_entry_invoice_number** (Char)





### res.config.settings


- Hereda de:

  - res.config.settings




- Campos:

  - **l10n_vn_edi_username** (Char)


  - **l10n_vn_edi_password** (Char)


  - **l10n_vn_edi_default_symbol** (Many2one) → l10n_vn_edi_viettel.sinvoice.symbol





### res.company


- Hereda de:

  - res.company




- Campos:

  - **l10n_vn_edi_username** (Char)


  - **l10n_vn_edi_password** (Char)


  - **l10n_vn_edi_token** (Char)


  - **l10n_vn_edi_token_expiry** (Datetime)





### res.partner


- Hereda de:

  - res.partner




- Campos:

  - **invoice_edi_format** (Selection)


  - **l10n_vn_edi_symbol** (Many2one) → l10n_vn_edi_viettel.sinvoice.symbol








## Vistas


### l10n_vn_edi_viettel.cancellation

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | l10n_vn_edi_viettel.cancellation.form | `l10n_vn_edi_viettel.l10n_vn_edi_cancellation_form` | - |



#### Botones (l10n_vn_edi_viettel.l10n_vn_edi_cancellation_form)
- **Request Cancellation** (object)

