# Módulo: Hungary - E-invoicing

## Información General
- **Nombre técnico:** l10n_hu_edi
- **Versión:** 1.0.0
- **Categoría:** Accounting/Localizations/EDI
- **Dependencias:** account_debit_note, base_iban, l10n_hu




## Descripción

* Electronically report invoices to the NAV (Hungarian Tax Agency) when issuing physical (paper) invoices.
* Perform the Tax Audit Export (Adóhatósági Ellenőrzési Adatszolgáltatás) in NAV 3.0 format.
    



## Modelos

### uom.uom


- Hereda de:

  - uom.uom




- Campos:

  - **l10n_hu_edi_code** (Selection)





### account.move.send


- Hereda de:

  - account.move.send




- No agrega campos



### account.chart.template


- Hereda de:

  - account.chart.template




- No agrega campos



### account.move


- Hereda de:

  - account.move




- Campos:

  - **l10n_hu_payment_mode** (Selection)


  - **l10n_hu_edi_state** (Selection)


  - **l10n_hu_edi_batch_upload_index** (Integer)


  - **l10n_hu_edi_attachment** (Binary)


  - **l10n_hu_edi_send_time** (Datetime)


  - **l10n_hu_edi_transaction_code** (Char)


  - **l10n_hu_edi_messages** (Json)


  - **l10n_hu_invoice_chain_index** (Integer)


  - **l10n_hu_edi_attachment_filename** (Char)


  - **l10n_hu_edi_message_html** (Html)





### product.template


- Hereda de:

  - product.template




- Campos:

  - **l10n_hu_product_code_type** (Selection)


  - **l10n_hu_product_code** (Char)





### account.tax


- Hereda de:

  - account.tax




- Campos:

  - **l10n_hu_tax_type** (Selection)


  - **l10n_hu_tax_reason** (Char)





### res.config.settings


- Hereda de:

  - res.config.settings




- Campos:

  - **l10n_hu_tax_regime** (Selection)


  - **l10n_hu_edi_server_mode** (Selection)


  - **l10n_hu_edi_username** (Char)


  - **l10n_hu_edi_password** (Char)


  - **l10n_hu_edi_signature_key** (Char)


  - **l10n_hu_edi_replacement_key** (Char)


  - **l10n_hu_edi_is_active** (Boolean)





### res.company


- Hereda de:

  - res.company




- Campos:

  - **l10n_hu_group_vat** (Char)


  - **l10n_hu_tax_regime** (Selection)


  - **l10n_hu_edi_server_mode** (Selection)


  - **l10n_hu_edi_username** (Char)


  - **l10n_hu_edi_password** (Char)


  - **l10n_hu_edi_signature_key** (Char)


  - **l10n_hu_edi_replacement_key** (Char)


  - **l10n_hu_edi_last_transaction_recovery** (Datetime)





### res.partner


- Hereda de:

  - res.partner




- Campos:

  - **l10n_hu_group_vat** (Char)








## Vistas


### l10n_hu_edi.tax_audit_export

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | l10n_hu_edi.tax_audit_export.form | `l10n_hu_edi.l10n_hu_edi_tax_audit_export_form` | - |



#### Botones (l10n_hu_edi.l10n_hu_edi_tax_audit_export_form)
- **Export** (object)


### l10n_hu_edi.cancellation

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | l10n_hu_edi.cancellation.form | `l10n_hu_edi.l10n_hu_edi_cancellation_form` | - |



#### Botones (l10n_hu_edi.l10n_hu_edi_cancellation_form)
- **Request Annulment** (object)

