# Módulo: Purchase Requisition Stock

## Información General
- **Nombre técnico:** purchase_requisition_stock
- **Versión:** 1.2
- **Categoría:** Inventory/Purchase
- **Dependencias:** purchase_requisition, purchase_stock






## Modelos

### purchase.order


- Hereda de:

  - purchase.order




#### Campos
- **on_time_rate_perc** (Float)





### purchase.order.line


- Hereda de:

  - purchase.order.line




#### Campos
- **on_time_rate_perc** (Float)





### stock.rule


- Hereda de:

  - stock.rule




- No agrega campos




### stock.move


- Hereda de:

  - stock.move




#### Campos
- **requisition_line_ids** (One2many) → purchase.requisition.line





### purchase.requisition


- Hereda de:

  - purchase.requisition




#### Campos
- **warehouse_id** (Many2one) → stock.warehouse
- **picking_type_id** (Many2one) → stock.picking.type





### purchase.requisition.line


- Hereda de:

  - purchase.requisition.line




#### Campos
- **move_dest_id** (Many2one) → stock.move







