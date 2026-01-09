# Módulo: Purchase and Subcontracting Management

## Información General
- **Nombre técnico:** mrp_subcontracting_purchase
- **Versión:** 0.1
- **Categoría:** Manufacturing/Purchase
- **Dependencias:** mrp_subcontracting, purchase_mrp




## Descripción

This bridge module adds some smart buttons between Purchase and Subcontracting
    



## Modelos

### purchase.order


- Hereda de:

  - purchase.order




- Campos:

  - **subcontracting_resupply_picking_count** (Integer) → Count of Subcontracting Resupply





### stock.move


- Hereda de:

  - stock.move




- No agrega campos



### stock.valuation.layer


- Hereda de:

  - stock.valuation.layer




- No agrega campos



### stock.rule


- Hereda de:

  - stock.rule




- No agrega campos



### stock.picking


- Hereda de:

  - stock.picking




- Campos:

  - **subcontracting_source_purchase_count** (Integer) → Number of subcontracting PO Source





### account.move.line


- Hereda de:

  - account.move.line




- No agrega campos





