# Módulo: Repairs

## Información General
- **Nombre técnico:** repair
- **Versión:** 1.0
- **Categoría:** Inventory/Inventory
- **Dependencias:** stock, sale_management


## Propósito
Repair damaged products



## Descripción

The aim is to have a complete module to manage all products repairs.
====================================================================

The following topics are covered by this module:
------------------------------------------------------
    * Add/remove products in the reparation
    * Impact for stocks
    * Warranty concept
    * Repair quotation report
    * Notes for the technician and for the final customer




## Modelos

### stock.traceability.report


- Hereda de:

  - stock.traceability.report




- No agrega campos




### sale.order


- Hereda de:

  - sale.order




#### Campos
- **repair_order_ids** (One2many) → repair.order
- **repair_count** (Integer) → Repair Order(s)





### sale.order.line


- Hereda de:

  - sale.order.line




- No agrega campos




### stock.warehouse


- Hereda de:

  - stock.warehouse




#### Campos
- **repair_type_id** (Many2one) → stock.picking.type
- **repair_mto_pull_id** (Many2one) → stock.rule





### stock.move


- Hereda de:

  - stock.move




#### Campos
- **repair_id** (Many2one) → repair.order
- **repair_line_type** (Selection)





### mail.compose.message


- Hereda de:

  - mail.compose.message




- No agrega campos




### stock.picking.type


- Hereda de:

  - stock.picking.type




#### Campos
- **code** (Selection)
- **count_repair_confirmed** (Integer)
- **count_repair_under_repair** (Integer)
- **count_repair_ready** (Integer)
- **count_repair_late** (Integer)
- **default_product_location_src_id** (Many2one) → stock.location
- **default_product_location_dest_id** (Many2one) → stock.location
- **default_remove_location_dest_id** (Many2one) → stock.location
- **default_recycle_location_dest_id** (Many2one) → stock.location
- **is_repairable** (Boolean) → Create Repair Orders from Returns
- **return_type_of_ids** (One2many) → stock.picking.type
- **repair_properties_definition** (PropertiesDefinition) → Repair Properties





### stock.picking


- Hereda de:

  - stock.picking




#### Campos
- **is_repairable** (Boolean)
- **repair_ids** (One2many) → repair.order
- **nbr_repairs** (Integer) → Number of repairs linked to this picking





### product.product


- Hereda de:

  - product.product




#### Campos
- **product_catalog_product_is_in_repair** (Boolean)





### product.template


- Hereda de:

  - product.template




#### Campos
- **create_repair** (Boolean) → Create Repair





### repair.order


- Hereda de:


  - mail.thread

  - mail.activity.mixin

  - product.catalog.mixin





#### Campos
- **name** (Char) → Repair Reference
- **company_id** (Many2one) → res.company
- **state** (Selection)
- **priority** (Selection)
- **partner_id** (Many2one) → res.partner
- **user_id** (Many2one) → res.users
- **internal_notes** (Html) → Internal Notes
- **tag_ids** (Many2many) → repair.tags
- **under_warranty** (Boolean) → Under Warranty
- **schedule_date** (Datetime) → Scheduled Date
- **search_date_category** (Selection)
- **repair_properties** (Properties) → Properties
- **move_id** (Many2one) → stock.move
- **product_id** (Many2one) → product.product
- **product_qty** (Float) → Product Quantity
- **product_uom** (Many2one) → uom.uom
- **product_uom_category_id** (Many2one)
- **lot_id** (Many2one) → stock.lot
- **tracking** (Selection)
- **picking_type_id** (Many2one) → stock.picking.type
- **procurement_group_id** (Many2one) → procurement.group
- **location_id** (Many2one) → stock.location
- **product_location_src_id** (Many2one) → stock.location
- **product_location_dest_id** (Many2one) → stock.location
- **location_dest_id** (Many2one) → stock.location
- **parts_location_id** (Many2one) → stock.location
- **recycle_location_id** (Many2one) → stock.location
- **move_ids** (One2many) → stock.move
- **parts_availability** (Char)
- **parts_availability_state** (Selection)
- **is_parts_available** (Boolean) → All Parts are available
- **is_parts_late** (Boolean) → Any Part is late
- **sale_order_id** (Many2one) → sale.order
- **sale_order_line_id** (Many2one) → sale.order.line
- **repair_request** (Text)
- **picking_id** (Many2one) → stock.picking
- **is_returned** (Boolean) → Returned
- **picking_product_ids** (One2many) → product.product
- **picking_product_id** (Many2one)
- **allowed_lot_ids** (One2many) → stock.lot
- **has_uncomplete_moves** (Boolean)
- **unreserve_visible** (Boolean) → Allowed to Unreserve Production
- **reserve_visible** (Boolean) → Allowed to Reserve Production





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| activity | repair.order.view.activity | `repair.repair_order_view_activity` | - |
| list | repair.list | `repair.view_repair_order_tree` | - |
| form | repair.form | `repair.view_repair_order_form` | - |
| kanban | repair.kanban | `repair.view_repair_kanban` | - |
| search | repair.select | `repair.view_repair_order_form_filter` | - |
| graph | repair.graph | `repair.view_repair_graph` | - |
| pivot | repair.pivot | `repair.view_repair_pivot` | - |



**Botones (repair.view_repair_order_form):**
- **Confirm Repair** (object)
- **Start Repair** (object)
- **End Repair** (object)
- **End Repair** (object)
- **Check availability** (object)
- **Unreserve** (object)
- **Create Quotation** (object)
- **Cancel Repair** (object)
- **Set to Draft** (object)
- **Sale Order** (object)
- **Product Moves** (action)
- **Catalog** (object)
- **action_product_forecast_report** (object)
- **action_product_forecast_report** (object)
- **action_show_details** (object)


**Filtros de búsqueda (repair.view_repair_order_form_filter):**

- **New** (`[('state', '=', 'draft')]`)
- **Confirmed** (`[('state', '=', 'confirmed')]`)
- **Under Repair** (`[('state', '=', 'under_repair')]`)
- **Repaired** (`[('state', '=', 'done')]`)
- **Cancelled** (`[('state', '=', 'cancel')]`)
- **Returned** (`[('picking_id', '!=', False), ('picking_id.state', '=', 'done')]`)
- **Before** (`[('search_date_category', '=', 'before')]`)
- **Yesterday** (`[('search_date_category', '=', 'yesterday')]`)
- **Today** (`[('search_date_category', '=', 'today')]`)
- **Tomorrow** (`[('search_date_category', '=', 'day_1')]`)
- **The day after tomorrow** (`[('search_date_category', '=', 'day_2')]`)
- **After** (`[('search_date_category', '=', 'after')]`)
- **Ready** (`[('state', '=', 'confirmed'), ('is_parts_available', '=', True)]`)
- **Late** (`[('state', '=', 'confirmed'), ('schedule_date', '<', context_today().strftime('%Y-%m-%d'))]`)
- **filter_create_date**
- **Late Activities** (`[('my_activity_date_deadline', '<', context_today().strftime('%Y-%m-%d'))]`)
- **Today Activities** (`[('my_activity_date_deadline', '=', context_today().strftime('%Y-%m-%d'))]`)
- **Future Activities** (`[('my_activity_date_deadline', '>', context_today().strftime('%Y-%m-%d'))]`)


*Agrupar por:*
- Customer
- Product
- Status
- Company



### repair.tags


- Hereda de: Base



#### Campos
- **name** (Char) → Tag Name
- **color** (Integer)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | repair.tag.form | `repair.view_repair_tag_form` | - |
| list | repair.tag.list | `repair.view_repair_tag_tree` | - |
| search | repair.tag.search | `repair.view_repair_tag_search` | - |




### stock.move.line


- Hereda de:

  - stock.move.line




- No agrega campos




### stock.lot


- Hereda de:

  - stock.lot




#### Campos
- **repair_line_ids** (Many2many) → repair.order
- **repair_part_count** (Integer) → Repair part count
- **in_repair_count** (Integer) → In repair count
- **repaired_count** (Integer) → Repaired count










