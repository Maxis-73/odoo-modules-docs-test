# Módulo: Sales and Warehouse Management

## Información General
- **Nombre técnico:** sale_stock
- **Versión:** 1.0
- **Categoría:** Hidden
- **Dependencias:** sale, stock_account


## Propósito
Quotation, Sales Orders, Delivery & Invoicing Control



## Descripción

Manage sales quotations and orders

This module makes the link between the sales and warehouses management applications.

Preferences
-----------
* Shipping: Choice of delivery at once or partial delivery
* Invoicing: choose how invoices will be paid
* Incoterms: International Commercial terms





## Modelos

### sale.order


- Hereda de:

  - sale.order




- Campos:

  - **incoterm** (Many2one) → account.incoterms


  - **incoterm_location** (Char)


  - **picking_policy** (Selection)


  - **warehouse_id** (Many2one) → stock.warehouse


  - **picking_ids** (One2many) → stock.picking


  - **delivery_count** (Integer)


  - **delivery_status** (Selection)


  - **procurement_group_id** (Many2one) → procurement.group


  - **effective_date** (Datetime) → Effective Date


  - **expected_date** (Datetime)


  - **json_popover** (Char) → JSON data for the popover widget


  - **show_json_popover** (Boolean) → Has late picking





### stock.warehouse


- Hereda de:

  - stock.warehouse




- No agrega campos



### sale.order.line


- Hereda de:

  - sale.order.line




- Campos:

  - **qty_delivered_method** (Selection)


  - **route_id** (Many2one) → stock.route


  - **move_ids** (One2many) → stock.move


  - **virtual_available_at_date** (Float)


  - **scheduled_date** (Datetime)


  - **forecast_expected_date** (Datetime)


  - **free_qty_today** (Float)


  - **qty_available_today** (Float)


  - **warehouse_id** (Many2one) → stock.warehouse


  - **qty_to_deliver** (Float)


  - **is_mto** (Boolean)


  - **display_qty_widget** (Boolean)


  - **is_storable** (Boolean)


  - **customer_lead** (Float)





### product.template


- Hereda de:

  - product.template




- No agrega campos



### account.move


- Hereda de:

  - account.move




- No agrega campos



### account.move.line


- Hereda de:

  - account.move.line




- No agrega campos



### stock.valuation.layer


- Hereda de:

  - stock.valuation.layer




- No agrega campos



### ['res.users']


- Hereda de:


  - res.users





- Campos:

  - **property_warehouse_id** (Many2one) → stock.warehouse





### stock.route


- Hereda de:

  - stock.route




- Campos:

  - **sale_selectable** (Boolean) → Selectable on Sales Order Line





### stock.move


- Hereda de:

  - stock.move




- Campos:

  - **sale_line_id** (Many2one) → sale.order.line





### stock.move.line


- Hereda de:

  - stock.move.line




- No agrega campos



### procurement.group


- Hereda de:

  - procurement.group




- Campos:

  - **sale_id** (Many2one) → sale.order





### stock.rule


- Hereda de:

  - stock.rule




- No agrega campos



### stock.picking


- Hereda de:

  - stock.picking




- Campos:

  - **sale_id** (Many2one) → sale.order





### stock.lot


- Hereda de:

  - stock.lot




- Campos:

  - **sale_order_ids** (Many2many) → sale.order


  - **sale_order_count** (Integer) → Sale order count





### res.config.settings


- Hereda de:

  - res.config.settings




- Campos:

  - **security_lead** (Float)


  - **use_security_lead** (Boolean)


  - **default_picking_policy** (Selection)





### res.company


- Hereda de:

  - res.company




- Campos:

  - **security_lead** (Float) → Sales Safety Days








## Vistas


### stock.lot

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | stock.production.lot.view.form | `sale_stock.stock_production_lot_view_form` | stock.view_production_lot_form |


