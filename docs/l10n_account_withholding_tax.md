# Módulo: Withholding Tax on Payment

## Información General
- **Nombre técnico:** l10n_account_withholding_tax
- **Versión:** 1.0
- **Categoría:** Accounting/Localizations
- **Dependencias:** account




## Descripción
Allows to register withholding taxes during the payment of an invoice or bill.



## Modelos

### account.withholding.line


- Hereda de:

  - analytic.mixin




- Campos:

  - **name** (Char)


  - **placeholder_value** (Char)


  - **placeholder_type** (Selection)


  - **previous_placeholder_type** (Selection)


  - **type_tax_use** (Char)


  - **tax_id** (Many2one) → account.tax


  - **withholding_sequence_id** (Many2one)


  - **source_base_amount_currency** (Monetary)


  - **source_base_amount** (Monetary)


  - **source_tax_amount_currency** (Monetary)


  - **source_tax_amount** (Monetary)


  - **source_currency_id** (Many2one) → res.currency


  - **source_tax_id** (Many2one) → account.tax


  - **original_base_amount** (Monetary)


  - **original_tax_amount** (Monetary)


  - **base_amount** (Monetary)


  - **amount** (Monetary)


  - **account_id** (Many2one) → account.account


  - **comodel_percentage_paid_factor** (Float)


  - **comodel_date** (Date)


  - **comodel_payment_type** (Selection)


  - **company_id** (Many2one) → res.company


  - **comodel_company_currency_id** (Many2one)


  - **comodel_currency_id** (Many2one) → res.currency





### account.payment


- Hereda de:

  - account.payment




- Campos:

  - **display_withholding** (Boolean)


  - **should_withhold_tax** (Boolean)


  - **withholding_line_ids** (One2many) → account.payment.withholding.line


  - **withholding_payment_account_id** (Many2one)


  - **outstanding_account_id** (Many2one)


  - **withholding_hide_tax_base_account** (Boolean)





### product.template


- Hereda de:

  - product.template




- No agrega campos



### account.payment.withholding.line


- Hereda de:

  - account.withholding.line




- Campos:

  - **payment_id** (Many2one) → account.payment





### account.tax


- Hereda de:

  - account.tax




- Campos:

  - **is_withholding_tax_on_payment** (Boolean)


  - **withholding_sequence_id** (Many2one) → ir.sequence





### res.config.settings


- Hereda de:

  - res.config.settings




- Campos:

  - **withholding_tax_base_account_id** (Many2one)





### res.company


- Hereda de:

  - res.company




- Campos:

  - **withholding_tax_base_account_id** (Many2one) → account.account








## Vistas


### account.payment

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | account.payment.form | `l10n_account_withholding_tax.view_account_payment_form` | account.view_account_payment_form |


