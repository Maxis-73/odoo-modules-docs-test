# Módulo: Delivery Stock Picking Batch

## Información General
- **Nombre técnico:** delivery_stock_picking_batch
- **Versión:** 1.0
- **Categoría:** Hidden
- **Dependencias:** stock_delivery, stock_picking_batch


## Propósito
Batch Transfer, Carrier



## Descripción

This module makes the link between the batch pickings and carrier applications.

Allows to prepare batches depending on their carrier




## Modelos

### stock.picking.batch


- Hereda de:

  - stock.picking.batch




- No agrega campos




### stock.picking.type


- Hereda de:

  - stock.picking.type




#### Campos
- **batch_group_by_carrier** (Boolean) → Carrier
- **batch_max_weight** (Integer) → Maximum weight
- **weight_uom_name** (Char)





### stock.picking


- Hereda de:

  - stock.picking




- No agrega campos






