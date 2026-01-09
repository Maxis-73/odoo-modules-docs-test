# Módulo: Purchase Stock

## Información General
- **Nombre técnico:** purchase_stock
- **Versión:** 1.2
- **Categoría:** Inventory/Purchase
- **Dependencias:** stock_account, purchase


## Propósito
Purchase Orders, Receipts, Vendor Bills for Stock





## Modelos

### purchase.order


- Hereda de:

  - purchase.order




#### Campos
- **incoterm_location** (Char)
- **incoming_picking_count** (Integer) → Incoming Shipment count
- **picking_ids** (Many2many) → stock.picking
- **dest_address_id** (Many2one) → res.partner
- **picking_type_id** (Many2one) → stock.picking.type
- **default_location_dest_id_usage** (Selection)
- **group_id** (Many2one) → procurement.group
- **is_shipped** (Boolean)
- **effective_date** (Datetime) → Arrival
- **on_time_rate** (Float)
- **receipt_status** (Selection)





### stock.move


- Hereda de:

  - stock.move




#### Campos
- **purchase_line_id** (Many2one) → purchase.order.line
- **created_purchase_line_ids** (Many2many) → purchase.order.line





### stock.valuation.layer


- Hereda de:

  - stock.valuation.layer




- No agrega campos




### stock.rule


- Hereda de:

  - stock.rule




#### Campos
- **action** (Selection)





### account.move


- Hereda de:

  - account.move




- No agrega campos




### product.category


- Hereda de:

  - product.category




#### Campos
- **property_account_creditor_price_difference_categ** (Many2one) → account.account





### product.template


- Hereda de:

  - product.template




#### Campos
- **property_account_creditor_price_difference** (Many2one) → account.account
- **route_ids** (Many2many)





### product.product


- Hereda de:

  - product.product




#### Campos
- **purchase_order_line_ids** (One2many) → purchase.order.line





### product.supplierinfo


- Hereda de:

  - product.supplierinfo




#### Campos
- **last_purchase_date** (Date) → Last Purchase
- **show_set_supplier_button** (Boolean) → Show Set Supplier Button





### stock.picking


- Hereda de:

  - stock.picking




#### Campos
- **purchase_id** (Many2one) → purchase.order
- **days_to_arrive** (Datetime)
- **delay_pass** (Datetime)





### stock.warehouse


- Hereda de:

  - stock.warehouse




#### Campos
- **buy_to_resupply** (Boolean) → Buy to Resupply
- **buy_pull_id** (Many2one) → stock.rule





### stock.return.picking


- Hereda de:

  - stock.return.picking




- No agrega campos




### stock.warehouse.orderpoint


- Hereda de:

  - stock.warehouse.orderpoint




#### Campos
- **show_supplier** (Boolean) → Show supplier column
- **supplier_id** (Many2one) → product.supplierinfo
- **vendor_id** (Many2one)
- **purchase_visibility_days** (Float)
- **product_supplier_id** (Many2one) → res.partner





### stock.lot


- Hereda de:

  - stock.lot




#### Campos
- **purchase_order_ids** (Many2many) → purchase.order
- **purchase_order_count** (Integer) → Purchase order count





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | stock.production.lot.view.form | `purchase_stock.stock_production_lot_view_form` | stock.view_production_lot_form |




### procurement.group


- Hereda de:

  - procurement.group




#### Campos
- **purchase_line_ids** (One2many) → purchase.order.line





### res.config.settings


- Hereda de:

  - res.config.settings




#### Campos
- **module_stock_dropshipping** (Boolean) → Dropshipping
- **days_to_purchase** (Float)
- **is_installed_sale** (Boolean)





### account.move.line


- Hereda de:

  - account.move.line




- No agrega campos




### res.company


- Hereda de:

  - res.company




#### Campos
- **days_to_purchase** (Float)





### purchase.order.line


- Hereda de:

  - purchase.order.line




#### Campos
- **qty_received_method** (Selection)
- **move_ids** (One2many) → stock.move
- **orderpoint_id** (Many2one) → stock.warehouse.orderpoint
- **move_dest_ids** (Many2many) → stock.move
- **product_description_variants** (Char) → Custom Description
- **propagate_cancel** (Boolean) → Propagate cancellation
- **forecasted_issue** (Boolean)
- **is_storable** (Boolean)
- **location_final_id** (Many2one) → stock.location
- **group_id** (Many2one) → procurement.group





### res.partner


- Hereda de:

  - res.partner




#### Campos
- **purchase_line_ids** (One2many) → purchase.order.line
- **on_time_rate** (Float) → On-Time Delivery Rate





### stock.replenish.mixin


- Hereda de:

  - stock.replenish.mixin




#### Campos
- **supplier_id** (Many2one) → product.supplierinfo
- **show_vendor** (Boolean)










## Vistas Adicionales


### vendor.delay.report

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| search | vendor.delay.report.search | `purchase_stock.vendor_delay_report_filter` | - |
| graph | vendor.delay.report.view.graph | `purchase_stock.vendor_delay_report_view_graph` | - |



**Filtros de búsqueda (purchase_stock.vendor_delay_report_filter):**

- **Effective Date Last Year** (`[('date', '>=', ((context_today()-relativedelta(years=1)).strftime('%Y-%m-%d')))]`)



