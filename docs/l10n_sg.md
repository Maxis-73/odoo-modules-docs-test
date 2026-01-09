# Módulo: Singapore - Accounting

## Información General
- **Nombre técnico:** l10n_sg
- **Versión:** 2.2
- **Categoría:** Accounting/Localizations/Account Charts
- **Dependencias:** account_qr_code_emv, account




## Descripción

Singapore accounting chart and localization.

This module add, for accounting:
 - The Chart of Accounts of Singapore
 - Field UEN (Unique Entity Number) on company and partner
 - Field PermitNo and PermitNoDate on invoice

    



## Modelos

### account.move


- Hereda de:

  - account.move




- Campos:

  - **l10n_sg_permit_number** (Char)


  - **l10n_sg_permit_number_date** (Date)





### res.partner.bank


- Hereda de:

  - res.partner.bank




- Campos:

  - **proxy_type** (Selection)





### res.company


- Hereda de:

  - res.company




- Campos:

  - **l10n_sg_unique_entity_number** (Char)





### res.partner


- Hereda de:

  - res.partner




- Campos:

  - **l10n_sg_unique_entity_number** (Char)





### account.chart.template


- Hereda de:

  - account.chart.template




- No agrega campos





