# Módulo: Purchase and MRP Management

## Información General
- **Nombre técnico:** purchase_mrp
- **Versión:** 1.0
- **Categoría:** Inventory/Purchase
- **Dependencias:** mrp, purchase_stock




## Descripción

This module provides facility to the user to install mrp and purchase modules at a time.
========================================================================================

It is basically used when we want to keep track of production orders generated
from purchase order.
    



## Modelos

### mrp.bom


- Hereda de:

  - mrp.bom




- No agrega campos




### mrp.bom.line


- Hereda de:

  - mrp.bom.line




#### Campos
- **cost_share** (Float) → Cost Share (%)





### mrp.production


- Hereda de:

  - mrp.production




#### Campos
- **purchase_order_count** (Integer) → Count of generated PO





### stock.move


- Hereda de:

  - stock.move




- No agrega campos




### account.move.line


- Hereda de:

  - account.move.line




- No agrega campos




### purchase.order


- Hereda de:

  - purchase.order




#### Campos
- **mrp_production_count** (Integer) → Count of MO Source





### purchase.order.line


- Hereda de:

  - purchase.order.line




- No agrega campos






