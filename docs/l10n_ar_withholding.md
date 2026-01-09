# Módulo: Argentina - Payment Withholdings

## Información General
- **Nombre técnico:** l10n_ar_withholding
- **Versión:** 1.0
- **Categoría:** Accounting/Localizations
- **Dependencias:** l10n_ar, l10n_latam_check




## Descripción
Allows to register withholdings during the payment of an invoice.



## Modelos

### l10n_ar.partner.tax


- Hereda de: Base



- Campos:

  - **partner_id** (Many2one) → res.partner


  - **tax_id** (Many2one) → account.tax


  - **company_id** (Many2one)


  - **from_date** (Date)


  - **to_date** (Date)


  - **ref** (Char)





### account.payment


- Hereda de:

  - account.payment




- Campos:

  - **l10n_ar_withholding_ids** (One2many)





### account.move


- Hereda de:

  - account.move




- Campos:

  - **l10n_ar_withholding_ids** (One2many) → account.move.line





### account.tax


- Hereda de:

  - account.tax




- Campos:

  - **l10n_ar_type_tax_use** (Selection)


  - **l10n_ar_withholding_payment_type** (Selection)


  - **l10n_ar_tax_type** (Selection)


  - **l10n_ar_withholding_sequence_id** (Many2one) → ir.sequence


  - **l10n_ar_code** (Char) → AFIP Code


  - **l10n_ar_non_taxable_amount** (Float)


  - **l10n_ar_minimum_threshold** (Float)


  - **l10n_ar_state_id** (Many2one) → res.country.state


  - **l10n_ar_scale_id** (Many2one) → l10n_ar.earnings.scale





### res.config.settings


- Hereda de:

  - res.config.settings




- Campos:

  - **l10n_ar_tax_base_account_id** (Many2one) → account.account





### res.company


- Hereda de:

  - res.company




- Campos:

  - **l10n_ar_tax_base_account_id** (Many2one) → account.account





### account.chart.template


- Hereda de:

  - account.chart.template




- No agrega campos



### l10n_ar.earnings.scale


- Hereda de: Base



- Campos:

  - **name** (Char)


  - **line_ids** (One2many) → l10n_ar.earnings.scale.line





### l10n_ar.earnings.scale.line


- Hereda de: Base



- Campos:

  - **scale_id** (Many2one) → l10n_ar.earnings.scale


  - **currency_id** (Many2one) → res.currency


  - **from_amount** (Monetary)


  - **to_amount** (Monetary)


  - **fixed_amount** (Monetary)


  - **percentage** (Monetary)


  - **excess_amount** (Monetary)





### res.partner


- Hereda de:

  - res.partner




- Campos:

  - **l10n_ar_partner_tax_ids** (One2many) → l10n_ar.partner.tax








## Vistas


### res.partner

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | res.partner.form.inherit | `l10n_ar_withholding.view_partner_form` | account.view_partner_property_form |



### l10n_ar.earnings.scale

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | l10n_ar.earnings.scale.tree | `l10n_ar_withholding.view_afip_earnings_table_scale_tree` | - |
| form | l10n_ar.earnings.scale.form | `l10n_ar_withholding.view_afip_earnings_table_scale_form` | - |



### account.payment

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | account.payment.form.inherited | `l10n_ar_withholding.view_account_payment_form` | l10n_latam_check.view_account_payment_form_inherited |


