# Módulo: Purchase Matrix

## Información General
- **Nombre técnico:** purchase_product_matrix
- **Versión:** 1.0
- **Categoría:** Inventory/Purchase
- **Dependencias:** purchase, product_matrix


## Propósito
Add variants to your purchase orders through an Order Grid Entry.



## Descripción

This module allows to fill Purchase Orders rapidly
by choosing product variants quantity through a Grid Entry.
    



## Modelos

### purchase.order


- Hereda de:

  - purchase.order




- Campos:

  - **report_grids** (Boolean)


  - **grid_product_tmpl_id** (Many2one) → product.template


  - **grid_update** (Boolean)


  - **grid** (Char)





### purchase.order.line


- Hereda de:

  - purchase.order.line




- Campos:

  - **product_template_id** (Many2one) → product.template


  - **is_configurable_product** (Boolean) → Is the product configurable?


  - **product_template_attribute_value_ids** (Many2many)


  - **product_no_variant_attribute_value_ids** (Many2many) → product.template.attribute.value







