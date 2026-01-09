# Módulo: Indonesian - Accounting

## Información General
- **Nombre técnico:** l10n_id
- **Versión:** 1.3
- **Categoría:** Accounting/Localizations/Account Charts
- **Dependencias:** account, base_iban, base_vat




## Descripción

This is the latest Indonesian Odoo localisation necessary to run Odoo accounting for SMEs with:
    - generic Indonesian chart of accounts
    - tax structure



## Modelos

### account.chart.template


- Hereda de:

  - account.chart.template




- No agrega campos



### account.move


- Hereda de:

  - account.move




- Campos:

  - **l10n_id_qris_transaction_ids** (Many2many) → l10n_id.qris.transaction





### l10n_id.qris.transaction


- Hereda de: Base



- Campos:

  - **model** (Char)


  - **model_id** (Char)


  - **qris_invoice_id** (Char)


  - **qris_amount** (Integer)


  - **qris_content** (Char)


  - **qris_creation_datetime** (Datetime)


  - **bank_id** (Many2one) → res.partner.bank


  - **paid** (Boolean)





### res.partner.bank


- Hereda de:

  - res.partner.bank




- Campos:

  - **l10n_id_qris_api_key** (Char) → QRIS API Key


  - **l10n_id_qris_mid** (Char) → QRIS Merchant ID







