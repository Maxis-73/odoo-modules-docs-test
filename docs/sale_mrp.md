# Módulo: Sales and MRP Management

## Información General
- **Nombre técnico:** sale_mrp
- **Versión:** 1.0
- **Categoría:** Hidden
- **Dependencias:** mrp, sale_stock




## Descripción

This module provides facility to the user to install mrp and sales modulesat a time.

It is basically used when we want to keep track of production orders generated
from sales order. It adds sales name and sales Reference on production order.
    



## Modelos

### mrp.bom


- Hereda de:

  - mrp.bom




- No agrega campos



### sale.order


- Hereda de:

  - sale.order




- Campos:

  - **mrp_production_count** (Integer) → Count of MO generated


  - **mrp_production_ids** (Many2many) → mrp.production





### mrp.production


- Hereda de:

  - mrp.production




- Campos:

  - **sale_order_count** (Integer) → Count of Source SO


  - **sale_line_id** (Many2one) → sale.order.line





### sale.order.line


- Hereda de:

  - sale.order.line




- No agrega campos



### account.move.line


- Hereda de:

  - account.move.line




- No agrega campos



### stock.rule


- Hereda de:

  - stock.rule




- No agrega campos



### stock.move.line


- Hereda de:

  - stock.move.line




- No agrega campos





