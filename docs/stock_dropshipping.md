# Módulo: Drop Shipping

## Información General
- **Nombre técnico:** stock_dropshipping
- **Versión:** 1.0
- **Categoría:** Inventory/Inventory
- **Dependencias:** sale_purchase_stock


## Propósito
Drop Shipping



## Descripción

Manage drop shipping orders

This module adds a pre-configured Drop Shipping operation type
as well as a procurement route that allow configuring Drop
Shipping products and orders.

When drop shipping is used the goods are directly transferred
from vendors to customers (direct delivery) without
going through the retailer's warehouse. In this case no
internal transfer document is needed.





## Modelos

### sale.order


- Hereda de:

  - sale.order




- Campos:

  - **dropship_picking_count** (Integer) → Dropship Count





### sale.order.line


- Hereda de:

  - sale.order.line




- No agrega campos



### purchase.order


- Hereda de:

  - purchase.order




- Campos:

  - **dropship_picking_count** (Integer) → Dropship Count





### product.product


- Hereda de:

  - product.product




- No agrega campos



### stock.rule


- Hereda de:

  - stock.rule




- No agrega campos



### procurement.group


- Hereda de:

  - procurement.group




- No agrega campos



### stock.picking


- Hereda de:

  - stock.picking




- Campos:

  - **is_dropship** (Boolean) → Is a Dropship





### stock.picking.type


- Hereda de:

  - stock.picking.type




- Campos:

  - **code** (Selection)





### stock.lot


- Hereda de:

  - stock.lot




- No agrega campos



### stock.move


- Hereda de:

  - stock.move




- No agrega campos



### res.company


- Hereda de:

  - res.company




- No agrega campos



### stock.replenish.mixin


- Hereda de:

  - stock.replenish.mixin




- No agrega campos





