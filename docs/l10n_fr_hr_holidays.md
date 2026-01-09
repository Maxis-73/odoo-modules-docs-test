# Módulo: France - Time Off

## Información General
- **Nombre técnico:** l10n_fr_hr_holidays
- **Versión:** 1.0
- **Categoría:** Human Resources/Time Off
- **Dependencias:** hr_holidays


## Propósito
Management of leaves for part-time workers in France





## Modelos

### hr.leave


- Hereda de:

  - hr.leave




- Campos:

  - **l10n_fr_date_to_changed** (Boolean)





### res.config.settings


- Hereda de:

  - res.config.settings




- Campos:

  - **l10n_fr_reference_leave_type** (Many2one) → hr.leave.type





### res.company


- Hereda de:

  - res.company




- Campos:

  - **l10n_fr_reference_leave_type** (Many2one) → hr.leave.type







