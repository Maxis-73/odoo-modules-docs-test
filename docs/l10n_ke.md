# Módulo: Kenya - Accounting

## Información General
- **Nombre técnico:** l10n_ke
- **Versión:** 1.0
- **Categoría:** Accounting/Localizations/Account Charts
- **Dependencias:** account




## Descripción

This provides a base chart of accounts and taxes template for use in Odoo.
    



## Modelos

### account.move


- Hereda de:

  - account.move




- Campos:

  - **l10n_ke_wh_certificate_number** (Char)


  - **l10n_ke_wh_certificate_date** (Date)





### account.tax


- Hereda de:

  - account.tax




- Campos:

  - **l10n_ke_item_code_id** (Many2one) → l10n_ke.item.code





### l10n_ke.item.code


- Hereda de: Base



- Campos:

  - **code** (Char)


  - **description** (Char)


  - **tax_rate** (Selection)





### res.company


- Hereda de:

  - res.company




- Campos:

  - **l10n_ke_oscu_is_active** (Boolean)





### account.chart.template


- Hereda de:

  - account.chart.template




- No agrega campos






## Vistas


### l10n_ke.item.code

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | l10n_ke.item.code.list | `l10n_ke.view_l10n_ke_item_code_tree` | - |
| search | l10n_ke.item.code.search | `l10n_ke.view_l10n_ke_item_code_search` | - |



#### Filtros de búsqueda (l10n_ke.view_l10n_ke_item_code_search)

**Filtros:**
- **Exempted** (`[('tax_rate','=','E')]`)
- **Zero Rated** (`[('tax_rate','=','C')]`)
- **Taxable at 8%** (`[('tax_rate','=','B')]`)


**Agrupar por:**
- By Tax Rate

