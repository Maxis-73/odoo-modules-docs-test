# Módulo: Mexico - Accounting

## Información General
- **Nombre técnico:** l10n_mx
- **Versión:** 2.3
- **Categoría:** Accounting/Localizations/Account Charts
- **Dependencias:** account




## Descripción

Minimal accounting configuration for Mexico.

This Chart of account is a minimal proposal to be able to use OoB the
accounting feature of Odoo.

This doesn't pretend be all the localization for MX it is just the minimal
data required to start from 0 in mexican localization.

This modules and its content is updated frequently by openerp-mexico team.

With this module you will have:

 - Minimal chart of account tested in production environments.
 - Minimal chart of taxes, to comply with SAT_ requirements.

.. _SAT: http://www.sat.gob.mx/
    



## Modelos

### account.chart.template


- Hereda de:

  - account.chart.template




- No agrega campos



### account.tax


- Hereda de:

  - account.tax




- Campos:

  - **l10n_mx_factor_type** (Selection)


  - **l10n_mx_tax_type** (Selection)





### res.bank


- Hereda de:

  - res.bank




- Campos:

  - **l10n_mx_edi_code** (Char) → ABM Code


  - **fiscal_country_codes** (Char)





### res.partner.bank


- Hereda de:

  - res.partner.bank




- Campos:

  - **l10n_mx_edi_clabe** (Char) → CLABE


  - **fiscal_country_codes** (Char)





### account.account


- Hereda de:

  - account.account




- No agrega campos





