# Módulo: Dropship and Subcontracting Management

## Información General
- **Nombre técnico:** mrp_subcontracting_dropshipping
- **Versión:** 0.1
- **Categoría:** Inventory/Purchase
- **Dependencias:** mrp_subcontracting, stock_dropshipping




## Descripción

This bridge module allows to manage subcontracting with the dropshipping module.
    



## Modelos

### stock.warehouse


- Hereda de:

  - stock.warehouse




#### Campos
- **subcontracting_dropshipping_to_resupply** (Boolean) → Dropship Subcontractors
- **subcontracting_dropshipping_pull_id** (Many2one) → stock.rule





### stock.move


- Hereda de:

  - stock.move




- No agrega campos




### stock.warehouse.orderpoint


- Hereda de:

  - stock.warehouse.orderpoint




- No agrega campos




### purchase.order


- Hereda de:

  - purchase.order




#### Campos
- **default_location_dest_id_is_subcontracting_loc** (Boolean)





### stock.rule


- Hereda de:

  - stock.rule




- No agrega campos




### stock.picking


- Hereda de:

  - stock.picking




- No agrega campos




### res.company


- Hereda de:

  - res.company




#### Campos
- **dropship_subcontractor_pick_type_id** (Many2one) → stock.picking.type





### stock.replenish.mixin


- Hereda de:

  - stock.replenish.mixin




- No agrega campos






