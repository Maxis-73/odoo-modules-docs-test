# Módulo: Indian - TDS and TCS

## Información General
- **Nombre técnico:** l10n_in_withholding
- **Versión:** 1.0
- **Categoría:** Accounting/Localizations
- **Dependencias:** l10n_in




## Descripción

        Support for Indian TDS (Tax Deducted at Source).
    



## Modelos

### account.payment


- Hereda de:

  - account.payment




- Campos:

  - **l10n_in_total_withholding_amount** (Monetary)


  - **l10n_in_withhold_move_ids** (One2many)





### l10n_in.section.alert


- Hereda de: Base



- Campos:

  - **name** (Char) → Section Name


  - **tax_source_type** (Selection)


  - **consider_amount** (Selection)


  - **is_per_transaction_limit** (Boolean) → Per Transaction


  - **per_transaction_limit** (Float) → Per Transaction limit


  - **is_aggregate_limit** (Boolean) → Aggregate


  - **aggregate_limit** (Float) → Aggregate limit


  - **aggregate_period** (Selection)


  - **l10n_in_section_tax_ids** (One2many) → account.tax





### account.move


- Hereda de:

  - account.move




- Campos:

  - **l10n_in_is_withholding** (Boolean)


  - **l10n_in_withholding_ref_move_id** (Many2one) → account.move


  - **l10n_in_withhold_move_ids** (One2many) → account.move


  - **l10n_in_withholding_line_ids** (One2many) → account.move.line


  - **l10n_in_total_withholding_amount** (Monetary)


  - **l10n_in_tcs_tds_warning** (Char) → TDC/TCS Warning


  - **l10n_in_display_higher_tcs_button** (Boolean)





### account.tax


- Hereda de:

  - account.tax




- Campos:

  - **l10n_in_tds_tax_type** (Selection)


  - **l10n_in_section_id** (Many2one) → l10n_in.section.alert





### res.config.settings


- Hereda de:

  - res.config.settings




- Campos:

  - **l10n_in_withholding_account_id** (Many2one)


  - **l10n_in_withholding_journal_id** (Many2one)





### account.move.line


- Hereda de:

  - account.move.line




- Campos:

  - **l10n_in_withhold_tax_amount** (Monetary)





### account.account


- Hereda de:

  - account.account




- Campos:

  - **l10n_in_tds_tcs_section_id** (Many2one) → l10n_in.section.alert





### res.company


- Hereda de:

  - res.company




- Campos:

  - **l10n_in_withholding_account_id** (Many2one) → account.account


  - **l10n_in_withholding_journal_id** (Many2one) → account.journal





### account.chart.template


- Hereda de:

  - account.chart.template




- No agrega campos






## Vistas


### account.move

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | account.move.form.inherit.l10n_in_withholding | `l10n_in_withholding.account_move_view_form_inherit_l10n_in_withholding` | account.view_move_form |



### l10n_in.section.alert

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | l10n_in.section.alert.view.list | `l10n_in_withholding.l10n_in_section_alert_view_tree` | - |
| form | l10n_in.section.alert.view.form | `l10n_in_withholding.l10n_in_section_alert_view_form` | - |



### l10n_in.withhold.wizard

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | l10n_in.withhold.wizard.view.form | `l10n_in_withholding.tds_entry_view_form` | - |



#### Botones (l10n_in_withholding.tds_entry_view_form)
- **Confirm** (object)

