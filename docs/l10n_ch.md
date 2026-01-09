# Módulo: Switzerland - Accounting

## Información General
- **Nombre técnico:** l10n_ch
- **Versión:** 11.3
- **Categoría:** Accounting/Localizations/Account Charts
- **Dependencias:** account, base_iban, l10n_din5008




## Descripción

Swiss localization
This module defines a chart of account for Switzerland (Swiss PME/KMU 2015), taxes and enables the generation of a QR-bill when you print an invoice or send it by mail.
The QR bill is attached to the invoice and eases its payment.

A QR-bill will be generated if:
    - The partner set on your invoice has a complete address (street, city, postal code and country) in Switzerland
    - The option to generate the Swiss QR-code is selected on the invoice (done by default)
    - A correct account number/QR IBAN is set on your bank journal
    - (when using a QR-IBAN): the payment reference of the invoice is a QR-reference

The generation of the QR-bill is automatic if you meet the previous criteria. The QR-bill will be appended after the invoice when printing or sending by mail.

    



## Modelos

### account.payment


- Hereda de:

  - account.payment




- Campos:

  - **l10n_ch_reference_warning_msg** (Char)





### ir.actions.report


- Hereda de:

  - ir.actions.report




- No agrega campos



### account.journal


- Hereda de:

  - account.journal




- Campos:

  - **invoice_reference_model** (Selection)





### account.move


- Hereda de:

  - account.move




- Campos:

  - **l10n_ch_is_qr_valid** (Boolean)





### account.chart.template


- Hereda de:

  - account.chart.template




- No agrega campos



### res.partner.bank


- Hereda de:

  - res.partner.bank




- Campos:

  - **l10n_ch_qr_iban** (Char)


  - **l10n_ch_display_qr_bank_options** (Boolean)








## Vistas


### l10n_ch.qr_invoice.wizard

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | l10n_ch.qr_invoice.wizard.form | `l10n_ch.l10n_ch_qr_invoice_wizard_form` | - |



#### Botones (l10n_ch.l10n_ch_qr_invoice_wizard_form)
- **Print All** (object)
- **Check invalid invoices** (object)

