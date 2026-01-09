# Módulo: Philippines - Accounting

## Información General
- **Nombre técnico:** l10n_ph
- **Versión:** 1.1
- **Categoría:** Accounting/Localizations/Account Charts
- **Dependencias:** account, base_vat


## Propósito
This is the module to manage the accounting chart for The Philippines.





## Modelos

### account.payment


- Hereda de:

  - account.payment




- No agrega campos



### account.move


- Hereda de:

  - account.move




- No agrega campos



### account.tax


- Hereda de:

  - account.tax




- Campos:

  - **l10n_ph_atc** (Char) → Philippines ATC





### account.chart.template


- Hereda de:

  - account.chart.template




- No agrega campos



### res.partner


- Hereda de:

  - res.partner




- Campos:

  - **branch_code** (Char) → Branch Code


  - **first_name** (Char) → First Name


  - **middle_name** (Char) → Middle Name


  - **last_name** (Char) → Last Name








## Vistas


### l10n_ph_2307.wizard

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | l10n_ph_2307.wizard.form | `l10n_ph.l10n_ph_2307_wizard_view_form` | - |



#### Botones (l10n_ph.l10n_ph_2307_wizard_view_form)
- **Generate** (object)

