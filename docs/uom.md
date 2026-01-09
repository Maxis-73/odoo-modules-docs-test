# Módulo: Units of measure

## Información General
- **Nombre técnico:** uom
- **Versión:** 1.0
- **Categoría:** Sales/Sales
- **Dependencias:** base




## Descripción

This is the base module for managing Units of measure.
========================================================================
    



## Modelos

### uom.category


- Hereda de: Base



#### Campos
- **name** (Char) → Unit of Measure Category
- **uom_ids** (One2many) → uom.uom
- **reference_uom_id** (Many2one) → uom.uom





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | uom.category.form | `uom.product_uom_categ_form_view` | - |
| list | uom.category.list | `uom.product_uom_categ_tree_view` | - |
| search | uom.category.view.search | `uom.uom_categ_view_search` | - |




### uom.uom


- Hereda de: Base



#### Campos
- **name** (Char) → Unit of Measure
- **category_id** (Many2one) → uom.category
- **factor** (Float) → Ratio
- **factor_inv** (Float) → Bigger Ratio
- **rounding** (Float) → Rounding Precision
- **active** (Boolean) → Active
- **uom_type** (Selection)
- **ratio** (Float) → Combined Ratio
- **color** (Integer) → Color





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | uom.uom.list | `uom.product_uom_tree_view` | - |
| form | uom.uom.form | `uom.product_uom_form_view` | - |
| search | uom.uom.view.search | `uom.uom_uom_view_search` | - |



**Filtros de búsqueda (uom.uom_uom_view_search):**

- **Archived** (`[('active', '=', False)]`)


*Agrupar por:*
- Category








