# Módulo: Sale Matrix

## Información General
- **Nombre técnico:** sale_product_matrix
- **Versión:** 1.0
- **Categoría:** Sales/Sales
- **Dependencias:** sale, product_matrix


## Propósito
Add variants to Sales Order through a grid entry.



## Descripción

This module allows to fill Sales Order rapidly
by choosing product variants quantity through a Grid Entry.
    



## Modelos

### sale.order


- Hereda de:

  - sale.order




#### Campos
- **report_grids** (Boolean)
- **grid_product_tmpl_id** (Many2one) → product.template
- **grid_update** (Boolean)
- **grid** (Char) → Matrix local storage





### sale.order.line


- Hereda de:

  - sale.order.line




#### Campos
- **product_add_mode** (Selection)





### product.template


- Hereda de:

  - product.template




#### Campos
- **product_add_mode** (Selection)







