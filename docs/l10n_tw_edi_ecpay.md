# Módulo: Taiwan - E-invoicing

## Información General
- **Nombre técnico:** l10n_tw_edi_ecpay
- **Versión:** 1.0
- **Categoría:** Accounting/Localizations/EDI
- **Dependencias:** l10n_tw, base_vat


## Propósito
E-invoicing using ECpay



## Descripción

        Taiwan - E-invoicing
        =====================
        This module allows the user to send their invoices to the Ecpay system.
    



## Modelos

### account.move.send


- Hereda de:

  - account.move.send




- No agrega campos



### account.move


- Hereda de:

  - account.move




- Campos:

  - **l10n_tw_edi_file_id** (Many2one) → ir.attachment


  - **l10n_tw_edi_file** (Binary)


  - **l10n_tw_edi_ecpay_invoice_id** (Char)


  - **l10n_tw_edi_related_number** (Char)


  - **l10n_tw_edi_state** (Selection)


  - **l10n_tw_edi_love_code** (Char)


  - **l10n_tw_edi_is_print** (Boolean)


  - **l10n_tw_edi_carrier_type** (Selection)


  - **l10n_tw_edi_carrier_number** (Char)


  - **l10n_tw_edi_carrier_number_2** (Char)


  - **l10n_tw_edi_invoice_type** (Selection)


  - **l10n_tw_edi_clearance_mark** (Selection)


  - **l10n_tw_edi_zero_tax_rate_reason** (Selection)


  - **l10n_tw_edi_is_zero_tax_rate** (Boolean)


  - **l10n_tw_edi_invoice_create_date** (Datetime)


  - **l10n_tw_edi_refund_state** (Selection)


  - **l10n_tw_edi_refund_agreement_type** (Selection)


  - **l10n_tw_edi_allowance_notify_way** (Selection)


  - **l10n_tw_edi_invalidate_reason** (Char)


  - **l10n_tw_edi_refund_invoice_number** (Char)


  - **l10n_tw_edi_is_b2b** (Boolean)





### account.tax


- Hereda de:

  - account.tax




- Campos:

  - **l10n_tw_edi_tax_type** (Selection)


  - **l10n_tw_edi_special_tax_type** (Selection)





### res.config.settings


- Hereda de:

  - res.config.settings




- Campos:

  - **l10n_tw_edi_ecpay_staging_mode** (Boolean)


  - **l10n_tw_edi_ecpay_merchant_id** (Char)


  - **l10n_tw_edi_ecpay_hashkey** (Char)


  - **l10n_tw_edi_ecpay_hashIV** (Char)





### account.move.line


- Hereda de:

  - account.move.line




- Campos:

  - **l10n_tw_edi_ecpay_item_sequence** (Integer)





### res.company


- Hereda de:

  - res.company




- Campos:

  - **l10n_tw_edi_ecpay_staging_mode** (Boolean)


  - **l10n_tw_edi_ecpay_merchant_id** (Char)


  - **l10n_tw_edi_ecpay_hashkey** (Char)


  - **l10n_tw_edi_ecpay_hashIV** (Char)





### res.partner


- Hereda de:

  - res.partner




- Campos:

  - **invoice_edi_format** (Selection)








## Vistas


### l10n_tw_edi.invoice.cancel

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | l10n_tw_edi.invoice.cancel.form | `l10n_tw_edi_ecpay.l10n_tw_edi_invoice_cancel_form` | - |



#### Botones (l10n_tw_edi_ecpay.l10n_tw_edi_invoice_cancel_form)
- **Cancel Invoice** (object)


### l10n_tw_edi.invoice.print

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | l10n_tw_edi.invoice.print.form | `l10n_tw_edi_ecpay.l10n_tw_edi_invoice_print_form` | - |



#### Botones (l10n_tw_edi_ecpay.l10n_tw_edi_invoice_print_form)
- **Print Invoice** (object)

