# Módulo: Chile - Accounting

## Información General
- **Nombre técnico:** l10n_cl
- **Versión:** 3.1
- **Categoría:** Accounting/Localizations/Account Charts
- **Dependencias:** contacts, base_vat, l10n_latam_base, l10n_latam_invoice_document, uom, account




## Descripción

Chilean accounting chart and tax localization.
Plan contable chileno e impuestos de acuerdo a disposiciones vigentes.
    



## Modelos

### uom.uom


- Hereda de:

  - uom.uom




- Campos:

  - **l10n_cl_sii_code** (Char) → SII Code





### res.currency


- Hereda de:

  - res.currency




- Campos:

  - **l10n_cl_currency_code** (Char) → Currency Code


  - **l10n_cl_short_name** (Char) → Short Name





### res.bank


- Hereda de:

  - res.bank




- Campos:

  - **l10n_cl_sbif_code** (Char) → Cod. SBIF


  - **fiscal_country_codes** (Char)





### res.country


- Hereda de:

  - res.country




- Campos:

  - **l10n_cl_customs_code** (Char) → Customs Code


  - **l10n_cl_customs_name** (Char) → Customs Name


  - **l10n_cl_customs_abbreviation** (Char) → Customs Abbreviation





### account.chart.template


- Hereda de:

  - account.chart.template




- No agrega campos



### l10n_latam.document.type


- Hereda de:

  - l10n_latam.document.type




- Campos:

  - **internal_type** (Selection)


  - **l10n_cl_active** (Boolean) → Active in localization





### account.move


- Hereda de:

  - account.move




- Campos:

  - **partner_id_vat** (Char)


  - **l10n_latam_internal_type** (Selection)





### account.tax


- Hereda de:

  - account.tax




- Campos:

  - **l10n_cl_sii_code** (Integer) → SII Code





### account.move.line


- Hereda de:

  - account.move.line




- No agrega campos



### res.company


- Hereda de:

  - res.company




- Campos:

  - **l10n_cl_activity_description** (Char)





### res.partner


- Hereda de:

  - res.partner




- Campos:

  - **l10n_cl_sii_taxpayer_type** (Selection)


  - **l10n_cl_activity_description** (Char)








## Vistas


### account.move

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | account.move.form.inherit.l10n.cl | `l10n_cl.view_move_form_inherit_l10n_cl` | account.view_move_form |
| list | account.move.list2 | `l10n_cl.view_complete_invoice_refund_tree` | - |


