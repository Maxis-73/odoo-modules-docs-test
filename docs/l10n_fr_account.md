# Módulo: France - Accounting

## Información General
- **Nombre técnico:** l10n_fr_account
- **Versión:** 2.2
- **Categoría:** Accounting/Localizations/Account Charts
- **Dependencias:** base_iban, base_vat, account, l10n_fr




## Descripción

This is the module to manage the accounting chart for France in Odoo.

This module applies to companies based in France mainland. It doesn't apply to
companies based in the DOM-TOMs (Guadeloupe, Martinique, Guyane, Réunion, Mayotte).

This localisation module creates the VAT taxes of type 'tax included' for purchases
(it is notably required when you use the module 'hr_expense'). Beware that these
'tax included' VAT taxes are not managed by the fiscal positions provided by this
module (because it is complex to manage both 'tax excluded' and 'tax included'
scenarios in fiscal positions).

This localisation module doesn't properly handle the scenario when a France-mainland
company sells services to a company based in the DOMs. We could manage it in the
fiscal positions, but it would require to differentiate between 'product' VAT taxes
and 'service' VAT taxes. We consider that it is too 'heavy' to have this by default
in l10n_fr_account; companies that sell services to DOM-based companies should update the
configuration of their taxes and fiscal positions manually.

**Credits:** Sistheo, Zeekom, CrysaLEAD, Akretion and Camptocamp.




## Modelos

### account.chart.template


- Hereda de:

  - account.chart.template




- No agrega campos



### account.chart.template


- Hereda de:

  - account.chart.template




- No agrega campos



### account.move


- Hereda de:

  - account.move




- Campos:

  - **l10n_fr_is_company_french** (Boolean)





### res.company


- Hereda de:

  - res.company




- Campos:

  - **l10n_fr_rounding_difference_loss_account_id** (Many2one) → account.account


  - **l10n_fr_rounding_difference_profit_account_id** (Many2one) → account.account








## Vistas


### l10n_fr.fec.export.wizard

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | l10n_fr.fec.export.wizard.view | `l10n_fr_account.fec_export_wizard_view` | - |



#### Botones (l10n_fr_account.fec_export_wizard_view)
- **Generate** (object)

