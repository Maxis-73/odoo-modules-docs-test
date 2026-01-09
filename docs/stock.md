# Módulo: Inventory

## Información General
- **Nombre técnico:** stock
- **Versión:** 1.1
- **Categoría:** Inventory/Inventory
- **Dependencias:** product, barcodes_gs1_nomenclature, digest


## Propósito
Manage your stock and logistics activities





## Modelos

### stock.warehouse


- Hereda de: Base



- Campos:

  - **name** (Char) → Warehouse


  - **active** (Boolean) → Active


  - **company_id** (Many2one) → res.company


  - **partner_id** (Many2one) → res.partner


  - **view_location_id** (Many2one) → stock.location


  - **lot_stock_id** (Many2one) → stock.location


  - **code** (Char) → Short Name


  - **route_ids** (Many2many) → stock.route


  - **reception_steps** (Selection)


  - **delivery_steps** (Selection)


  - **wh_input_stock_loc_id** (Many2one) → stock.location


  - **wh_qc_stock_loc_id** (Many2one) → stock.location


  - **wh_output_stock_loc_id** (Many2one) → stock.location


  - **wh_pack_stock_loc_id** (Many2one) → stock.location


  - **mto_pull_id** (Many2one) → stock.rule


  - **pick_type_id** (Many2one) → stock.picking.type


  - **pack_type_id** (Many2one) → stock.picking.type


  - **out_type_id** (Many2one) → stock.picking.type


  - **in_type_id** (Many2one) → stock.picking.type


  - **int_type_id** (Many2one) → stock.picking.type


  - **qc_type_id** (Many2one) → stock.picking.type


  - **store_type_id** (Many2one) → stock.picking.type


  - **xdock_type_id** (Many2one) → stock.picking.type


  - **crossdock_route_id** (Many2one) → stock.route


  - **reception_route_id** (Many2one) → stock.route


  - **delivery_route_id** (Many2one) → stock.route


  - **resupply_wh_ids** (Many2many) → stock.warehouse


  - **resupply_route_ids** (One2many) → stock.route


  - **sequence** (Integer)





### stock.move


- Hereda de: Base



- Campos:

  - **name** (Char) → Description


  - **sequence** (Integer) → Sequence


  - **priority** (Selection)


  - **date** (Datetime) → Date Scheduled


  - **date_deadline** (Datetime) → Deadline


  - **company_id** (Many2one) → res.company


  - **product_id** (Many2one) → product.product


  - **never_product_template_attribute_value_ids** (Many2many) → product.template.attribute.value


  - **description_picking** (Text) → Description of Picking


  - **product_qty** (Float) → Real Quantity


  - **product_uom_qty** (Float) → Demand


  - **product_uom** (Many2one) → uom.uom


  - **product_uom_category_id** (Many2one)


  - **product_tmpl_id** (Many2one) → product.template


  - **location_id** (Many2one) → stock.location


  - **location_dest_id** (Many2one) → stock.location


  - **location_final_id** (Many2one) → stock.location


  - **location_usage** (Selection)


  - **location_dest_usage** (Selection)


  - **partner_id** (Many2one) → res.partner


  - **move_dest_ids** (Many2many) → stock.move


  - **move_orig_ids** (Many2many) → stock.move


  - **picking_id** (Many2one) → stock.picking


  - **state** (Selection)


  - **picked** (Boolean) → Picked


  - **price_unit** (Float) → Unit Price


  - **origin** (Char) → Source Document


  - **procure_method** (Selection)


  - **scrapped** (Boolean) → Scrapped


  - **scrap_id** (Many2one) → stock.scrap


  - **group_id** (Many2one) → procurement.group


  - **rule_id** (Many2one) → stock.rule


  - **propagate_cancel** (Boolean) → Propagate cancel and split


  - **delay_alert_date** (Datetime) → Delay Alert Date


  - **picking_type_id** (Many2one) → stock.picking.type


  - **is_inventory** (Boolean) → Inventory


  - **move_line_ids** (One2many) → stock.move.line


  - **origin_returned_move_id** (Many2one) → stock.move


  - **returned_move_ids** (One2many) → stock.move


  - **availability** (Float) → Forecasted Quantity


  - **restrict_partner_id** (Many2one) → res.partner


  - **route_ids** (Many2many) → stock.route


  - **warehouse_id** (Many2one) → stock.warehouse


  - **has_tracking** (Selection)


  - **quantity** (Float) → Quantity


  - **show_operations** (Boolean)


  - **picking_code** (Selection)


  - **show_details_visible** (Boolean) → Details Visible


  - **is_storable** (Boolean)


  - **additional** (Boolean) → Whether the move was added after the picking's confirmation


  - **is_locked** (Boolean)


  - **is_initial_demand_editable** (Boolean) → Is initial demand editable


  - **is_quantity_done_editable** (Boolean) → Is quantity done editable


  - **reference** (Char)


  - **move_lines_count** (Integer)


  - **package_level_id** (Many2one) → stock.package_level


  - **picking_type_entire_packs** (Boolean)


  - **display_assign_serial** (Boolean)


  - **display_import_lot** (Boolean)


  - **next_serial** (Char) → First SN/Lot


  - **next_serial_count** (Integer) → Number of SN/Lots


  - **orderpoint_id** (Many2one) → stock.warehouse.orderpoint


  - **forecast_availability** (Float) → Forecast Availability


  - **forecast_expected_date** (Datetime) → Forecasted Expected date


  - **lot_ids** (Many2many) → stock.lot


  - **reservation_date** (Date) → Date to Reserve


  - **product_packaging_id** (Many2one) → product.packaging


  - **product_packaging_qty** (Float)


  - **product_packaging_quantity** (Float)


  - **show_quant** (Boolean) → Show Quant


  - **show_lots_m2o** (Boolean) → Show lot_id


  - **show_lots_text** (Boolean) → Show lot_name





### stock.quant


- Hereda de: Base



- Campos:

  - **product_id** (Many2one) → product.product


  - **product_tmpl_id** (Many2one) → product.template


  - **product_uom_id** (Many2one) → uom.uom


  - **is_favorite** (Boolean)


  - **company_id** (Many2one)


  - **location_id** (Many2one) → stock.location


  - **warehouse_id** (Many2one) → stock.warehouse


  - **storage_category_id** (Many2one)


  - **cyclic_inventory_frequency** (Integer)


  - **lot_id** (Many2one) → stock.lot


  - **lot_properties** (Properties)


  - **sn_duplicated** (Boolean)


  - **package_id** (Many2one) → stock.quant.package


  - **owner_id** (Many2one) → res.partner


  - **quantity** (Float) → Quantity


  - **reserved_quantity** (Float) → Reserved Quantity


  - **available_quantity** (Float) → Available Quantity


  - **in_date** (Datetime) → Incoming Date


  - **tracking** (Selection)


  - **on_hand** (Boolean) → On Hand


  - **product_categ_id** (Many2one)


  - **inventory_quantity** (Float) → Counted Quantity


  - **inventory_quantity_auto_apply** (Float) → Inventoried Quantity


  - **inventory_diff_quantity** (Float) → Difference


  - **inventory_date** (Date) → Scheduled Date


  - **last_count_date** (Date)


  - **inventory_quantity_set** (Boolean)


  - **is_outdated** (Boolean) → Quantity has been moved since last count


  - **user_id** (Many2one) → res.users





### stock.quant.package


- Hereda de: Base



- Campos:

  - **name** (Char) → Package Reference


  - **quant_ids** (One2many) → stock.quant


  - **package_type_id** (Many2one) → stock.package.type


  - **location_id** (Many2one) → stock.location


  - **company_id** (Many2one) → res.company


  - **owner_id** (Many2one) → res.partner


  - **package_use** (Selection)


  - **shipping_weight** (Float)


  - **valid_sscc** (Boolean) → Package name is valid SSCC


  - **pack_date** (Date) → Pack Date





### stock.scrap


- Hereda de:


  - mail.thread





- Campos:

  - **name** (Char) → Reference


  - **company_id** (Many2one) → res.company


  - **origin** (Char)


  - **product_id** (Many2one) → product.product


  - **product_uom_id** (Many2one) → uom.uom


  - **product_uom_category_id** (Many2one)


  - **tracking** (Selection)


  - **lot_id** (Many2one) → stock.lot


  - **package_id** (Many2one) → stock.quant.package


  - **owner_id** (Many2one) → res.partner


  - **move_ids** (One2many) → stock.move


  - **picking_id** (Many2one) → stock.picking


  - **location_id** (Many2one) → stock.location


  - **scrap_location_id** (Many2one) → stock.location


  - **scrap_qty** (Float) → Quantity


  - **state** (Selection)


  - **date_done** (Datetime) → Date


  - **should_replenish** (Boolean)


  - **scrap_reason_tag_ids** (Many2many) → stock.scrap.reason.tag





### stock.scrap.reason.tag


- Hereda de: Base



- Campos:

  - **name** (Char)


  - **sequence** (Integer)


  - **color** (Char)





### stock.package.type


- Hereda de: Base



- Campos:

  - **name** (Char) → Package Type


  - **sequence** (Integer) → Sequence


  - **height** (Float) → Height


  - **width** (Float) → Width


  - **packaging_length** (Float) → Length


  - **base_weight** (Float)


  - **max_weight** (Float) → Max Weight


  - **barcode** (Char) → Barcode


  - **weight_uom_name** (Char)


  - **length_uom_name** (Char)


  - **company_id** (Many2one) → res.company


  - **storage_category_capacity_ids** (One2many) → stock.storage.category.capacity





### barcode.rule


- Hereda de:

  - barcode.rule




- Campos:

  - **type** (Selection)





### product.removal


- Hereda de: Base



- Campos:

  - **name** (Char) → Name


  - **method** (Char) → Method





### stock.putaway.rule


- Hereda de: Base



- Campos:

  - **product_id** (Many2one) → product.product


  - **category_id** (Many2one) → product.category


  - **location_in_id** (Many2one) → stock.location


  - **location_out_id** (Many2one) → stock.location


  - **sequence** (Integer) → Priority


  - **company_id** (Many2one) → res.company


  - **package_type_ids** (Many2many) → stock.package.type


  - **storage_category_id** (Many2one) → stock.storage.category


  - **active** (Boolean) → Active


  - **sublocation** (Selection)





### stock.package_level


- Hereda de: Base



- Campos:

  - **package_id** (Many2one) → stock.quant.package


  - **picking_id** (Many2one) → stock.picking


  - **move_ids** (One2many) → stock.move


  - **move_line_ids** (One2many) → stock.move.line


  - **location_id** (Many2one) → stock.location


  - **location_dest_id** (Many2one) → stock.location


  - **is_done** (Boolean) → Done


  - **state** (Selection)


  - **is_fresh_package** (Boolean)


  - **picking_type_code** (Selection)


  - **show_lots_m2o** (Boolean)


  - **show_lots_text** (Boolean)


  - **company_id** (Many2one) → res.company





### ir.actions.report


- Hereda de:

  - ir.actions.report




- No agrega campos



### stock.warehouse.orderpoint


- Hereda de: Base



- Campos:

  - **name** (Char) → Name


  - **trigger** (Selection)


  - **active** (Boolean) → Active


  - **snoozed_until** (Date) → Snoozed


  - **warehouse_id** (Many2one) → stock.warehouse


  - **location_id** (Many2one) → stock.location


  - **product_tmpl_id** (Many2one) → product.template


  - **product_id** (Many2one) → product.product


  - **product_category_id** (Many2one) → product.category


  - **product_uom** (Many2one) → uom.uom


  - **product_uom_name** (Char)


  - **product_min_qty** (Float) → Min Quantity


  - **product_max_qty** (Float) → Max Quantity


  - **qty_multiple** (Float) → Multiple Quantity


  - **group_id** (Many2one) → procurement.group


  - **company_id** (Many2one) → res.company


  - **allowed_location_ids** (One2many) → stock.location


  - **rule_ids** (Many2many) → stock.rule


  - **lead_days_date** (Date)


  - **route_id** (Many2one) → stock.route


  - **qty_on_hand** (Float) → On Hand


  - **qty_forecast** (Float) → Forecast


  - **qty_to_order** (Float) → To Order


  - **qty_to_order_computed** (Float) → To Order Computed


  - **qty_to_order_manual** (Float) → To Order Manual


  - **days_to_order** (Float)


  - **visibility_days** (Float)


  - **unwanted_replenish** (Boolean) → Unwanted Replenish





### stock.location


- Hereda de: Base



- Campos:

  - **name** (Char) → Location Name


  - **complete_name** (Char) → Full Location Name


  - **active** (Boolean) → Active


  - **usage** (Selection)


  - **location_id** (Many2one) → stock.location


  - **child_ids** (One2many) → stock.location


  - **child_internal_location_ids** (Many2many) → stock.location


  - **comment** (Html) → Additional Information


  - **posx** (Integer) → Corridor (X)


  - **posy** (Integer) → Shelves (Y)


  - **posz** (Integer) → Height (Z)


  - **parent_path** (Char)


  - **company_id** (Many2one) → res.company


  - **scrap_location** (Boolean) → Is a Scrap Location?


  - **replenish_location** (Boolean) → Replenish Location


  - **removal_strategy_id** (Many2one) → product.removal


  - **putaway_rule_ids** (One2many) → stock.putaway.rule


  - **barcode** (Char) → Barcode


  - **quant_ids** (One2many) → stock.quant


  - **cyclic_inventory_frequency** (Integer) → Inventory Frequency


  - **last_inventory_date** (Date) → Last Inventory


  - **next_inventory_date** (Date) → Next Expected


  - **warehouse_view_ids** (One2many) → stock.warehouse


  - **warehouse_id** (Many2one) → stock.warehouse


  - **storage_category_id** (Many2one) → stock.storage.category


  - **outgoing_move_line_ids** (One2many) → stock.move.line


  - **incoming_move_line_ids** (One2many) → stock.move.line


  - **net_weight** (Float) → Net Weight


  - **forecast_weight** (Float) → Forecasted Weight


  - **is_empty** (Boolean) → Is Empty





### stock.route


- Hereda de: Base



- Campos:

  - **name** (Char) → Route


  - **active** (Boolean) → Active


  - **sequence** (Integer) → Sequence


  - **rule_ids** (One2many) → stock.rule


  - **product_selectable** (Boolean) → Applicable on Product


  - **product_categ_selectable** (Boolean) → Applicable on Product Category


  - **warehouse_selectable** (Boolean) → Applicable on Warehouse


  - **packaging_selectable** (Boolean) → Applicable on Packaging


  - **supplied_wh_id** (Many2one) → stock.warehouse


  - **supplier_wh_id** (Many2one) → stock.warehouse


  - **company_id** (Many2one) → res.company


  - **product_ids** (Many2many) → product.template


  - **categ_ids** (Many2many) → product.category


  - **packaging_ids** (Many2many) → product.packaging


  - **warehouse_domain_ids** (One2many) → stock.warehouse


  - **warehouse_ids** (Many2many) → stock.warehouse





### stock.rule


- Hereda de: Base



- Campos:

  - **name** (Char) → Name


  - **active** (Boolean) → Active


  - **group_propagation_option** (Selection)


  - **group_id** (Many2one) → procurement.group


  - **action** (Selection)


  - **sequence** (Integer) → Sequence


  - **company_id** (Many2one) → res.company


  - **location_dest_id** (Many2one) → stock.location


  - **location_src_id** (Many2one) → stock.location


  - **location_dest_from_rule** (Boolean) → Destination location origin from rule


  - **route_id** (Many2one) → stock.route


  - **route_company_id** (Many2one)


  - **procure_method** (Selection)


  - **route_sequence** (Integer) → Route Sequence


  - **picking_type_id** (Many2one) → stock.picking.type


  - **picking_type_code_domain** (Char)


  - **delay** (Integer) → Lead Time


  - **partner_address_id** (Many2one) → res.partner


  - **propagate_cancel** (Boolean) → Cancel Next Move


  - **propagate_carrier** (Boolean) → Propagation of carrier


  - **warehouse_id** (Many2one) → stock.warehouse


  - **propagate_warehouse_id** (Many2one) → stock.warehouse


  - **auto** (Selection)


  - **rule_message** (Html)


  - **push_domain** (Char) → Push Applicability





### procurement.group


- Hereda de: Base



- Campos:

  - **partner_id** (Many2one) → res.partner


  - **name** (Char) → Reference


  - **move_type** (Selection)


  - **stock_move_ids** (One2many) → stock.move





### res.users


- Hereda de:

  - res.users




- No agrega campos



### stock.picking.type


- Hereda de: Base



- Campos:

  - **name** (Char) → Operation Type


  - **color** (Integer) → Color


  - **sequence** (Integer) → Sequence


  - **sequence_id** (Many2one) → ir.sequence


  - **sequence_code** (Char) → Sequence Prefix


  - **default_location_src_id** (Many2one) → stock.location


  - **default_location_dest_id** (Many2one) → stock.location


  - **code** (Selection)


  - **return_picking_type_id** (Many2one) → stock.picking.type


  - **show_entire_packs** (Boolean) → Move Entire Packages


  - **warehouse_id** (Many2one) → stock.warehouse


  - **active** (Boolean) → Active


  - **use_create_lots** (Boolean) → Create New Lots/Serial Numbers


  - **use_existing_lots** (Boolean) → Use Existing Lots/Serial Numbers


  - **print_label** (Boolean) → Generate Shipping Labels


  - **show_operations** (Boolean) → Show Detailed Operations


  - **reservation_method** (Selection)


  - **reservation_days_before** (Integer) → Days


  - **reservation_days_before_priority** (Integer) → Days when starred


  - **auto_show_reception_report** (Boolean) → Show Reception Report at Validation


  - **auto_print_delivery_slip** (Boolean) → Auto Print Delivery Slip


  - **auto_print_return_slip** (Boolean) → Auto Print Return Slip


  - **auto_print_product_labels** (Boolean) → Auto Print Product Labels


  - **product_label_format** (Selection)


  - **auto_print_lot_labels** (Boolean) → Auto Print Lot/SN Labels


  - **lot_label_format** (Selection)


  - **auto_print_reception_report** (Boolean) → Auto Print Reception Report


  - **auto_print_reception_report_labels** (Boolean) → Auto Print Reception Report Labels


  - **auto_print_packages** (Boolean) → Auto Print Packages


  - **auto_print_package_label** (Boolean) → Auto Print Package Label


  - **package_label_to_print** (Selection)


  - **count_picking_draft** (Integer)


  - **count_picking_ready** (Integer)


  - **count_picking** (Integer)


  - **count_picking_waiting** (Integer)


  - **count_picking_late** (Integer)


  - **count_picking_backorders** (Integer)


  - **count_move_ready** (Integer)


  - **hide_reservation_method** (Boolean)


  - **barcode** (Char) → Barcode


  - **company_id** (Many2one) → res.company


  - **create_backorder** (Selection)


  - **show_picking_type** (Boolean)


  - **picking_properties_definition** (PropertiesDefinition) → Picking Properties


  - **favorite_user_ids** (Many2many) → res.users


  - **is_favorite** (Boolean)


  - **kanban_dashboard_graph** (Text)


  - **move_type** (Selection)





### stock.picking


- Hereda de:


  - mail.thread

  - mail.activity.mixin





- Campos:

  - **name** (Char) → Reference


  - **origin** (Char) → Source Document


  - **note** (Html) → Notes


  - **backorder_id** (Many2one) → stock.picking


  - **backorder_ids** (One2many) → stock.picking


  - **return_id** (Many2one) → stock.picking


  - **return_ids** (One2many) → stock.picking


  - **return_count** (Integer) → # Returns


  - **move_type** (Selection)


  - **state** (Selection)


  - **group_id** (Many2one) → procurement.group


  - **priority** (Selection)


  - **scheduled_date** (Datetime) → Scheduled Date


  - **date_deadline** (Datetime) → Deadline


  - **has_deadline_issue** (Boolean) → Is late


  - **date** (Datetime) → Creation Date


  - **date_done** (Datetime) → Date of Transfer


  - **delay_alert_date** (Datetime) → Delay Alert Date


  - **json_popover** (Char) → JSON data for the popover widget


  - **location_id** (Many2one) → stock.location


  - **location_dest_id** (Many2one) → stock.location


  - **move_ids** (One2many) → stock.move


  - **move_ids_without_package** (One2many) → stock.move


  - **has_scrap_move** (Boolean) → Has Scrap Moves


  - **picking_type_id** (Many2one) → stock.picking.type


  - **warehouse_address_id** (Many2one) → res.partner


  - **picking_type_code** (Selection)


  - **picking_type_entire_packs** (Boolean)


  - **use_create_lots** (Boolean)


  - **use_existing_lots** (Boolean)


  - **partner_id** (Many2one) → res.partner


  - **company_id** (Many2one) → res.company


  - **user_id** (Many2one) → res.users


  - **move_line_ids** (One2many) → stock.move.line


  - **move_line_ids_without_package** (One2many) → stock.move.line


  - **move_line_exist** (Boolean) → Has Pack Operations


  - **has_packages** (Boolean) → Has Packages


  - **show_check_availability** (Boolean)


  - **show_allocation** (Boolean)


  - **owner_id** (Many2one) → res.partner


  - **printed** (Boolean) → Printed


  - **signature** (Image) → Signature


  - **is_signed** (Boolean) → Is Signed


  - **is_locked** (Boolean)


  - **weight_bulk** (Float) → Bulk Weight


  - **shipping_weight** (Float) → Weight for Shipping


  - **shipping_volume** (Float) → Volume for Shipping


  - **product_id** (Many2one) → product.product


  - **lot_id** (Many2one) → stock.lot


  - **show_operations** (Boolean)


  - **show_lots_text** (Boolean)


  - **has_tracking** (Boolean)


  - **package_level_ids** (One2many) → stock.package_level


  - **package_level_ids_details** (One2many) → stock.package_level


  - **products_availability** (Char)


  - **products_availability_state** (Selection)


  - **picking_properties** (Properties) → Properties


  - **show_next_pickings** (Boolean)


  - **search_date_category** (Selection)





### product.product


- Hereda de:

  - product.product




- Campos:

  - **stock_quant_ids** (One2many) → stock.quant


  - **stock_move_ids** (One2many) → stock.move


  - **qty_available** (Float) → Quantity On Hand


  - **virtual_available** (Float) → Forecasted Quantity


  - **free_qty** (Float) → Free To Use Quantity 


  - **incoming_qty** (Float) → Incoming


  - **outgoing_qty** (Float) → Outgoing


  - **orderpoint_ids** (One2many) → stock.warehouse.orderpoint


  - **nbr_moves_in** (Integer)


  - **nbr_moves_out** (Integer)


  - **nbr_reordering_rules** (Integer) → Reordering Rules


  - **reordering_min_qty** (Float)


  - **reordering_max_qty** (Float)


  - **putaway_rule_ids** (One2many) → stock.putaway.rule


  - **storage_category_capacity_ids** (One2many) → stock.storage.category.capacity


  - **show_on_hand_qty_status_button** (Boolean)


  - **show_forecasted_qty_status_button** (Boolean)


  - **valid_ean** (Boolean) → Barcode is valid EAN


  - **lot_properties_definition** (PropertiesDefinition) → Lot Properties





### product.template


- Hereda de:

  - product.template




- Campos:

  - **is_storable** (Boolean) → Track Inventory


  - **responsible_id** (Many2one) → res.users


  - **property_stock_production** (Many2one) → stock.location


  - **property_stock_inventory** (Many2one) → stock.location


  - **sale_delay** (Integer) → Customer Lead Time


  - **tracking** (Selection)


  - **description_picking** (Text) → Description on Picking


  - **description_pickingout** (Text) → Description on Delivery Orders


  - **description_pickingin** (Text) → Description on Receptions


  - **qty_available** (Float) → Quantity On Hand


  - **virtual_available** (Float) → Forecasted Quantity


  - **incoming_qty** (Float) → Incoming


  - **outgoing_qty** (Float) → Outgoing


  - **location_id** (Many2one) → stock.location


  - **warehouse_id** (Many2one) → stock.warehouse


  - **has_available_route_ids** (Boolean) → Routes can be selected on this product


  - **route_ids** (Many2many) → stock.route


  - **nbr_moves_in** (Integer)


  - **nbr_moves_out** (Integer)


  - **nbr_reordering_rules** (Integer) → Reordering Rules


  - **reordering_min_qty** (Float)


  - **reordering_max_qty** (Float)


  - **route_from_categ_ids** (Many2many)


  - **show_on_hand_qty_status_button** (Boolean)


  - **show_forecasted_qty_status_button** (Boolean)





### product.category


- Hereda de:

  - product.category




- Campos:

  - **route_ids** (Many2many) → stock.route


  - **removal_strategy_id** (Many2one) → product.removal


  - **parent_route_ids** (Many2many) → stock.route


  - **total_route_ids** (Many2many) → stock.route


  - **putaway_rule_ids** (One2many) → stock.putaway.rule


  - **packaging_reserve_method** (Selection)


  - **filter_for_stock_putaway_rule** (Boolean) → stock.putaway.rule





### product.packaging


- Hereda de:

  - product.packaging




- Campos:

  - **package_type_id** (Many2one) → stock.package.type


  - **route_ids** (Many2many) → stock.route





### uom.uom


- Hereda de:

  - uom.uom




- No agrega campos



### res.config.settings


- Hereda de:

  - res.config.settings




- Campos:

  - **module_product_expiry** (Boolean) → Expiration Dates


  - **group_stock_production_lot** (Boolean) → Lots & Serial Numbers


  - **group_stock_lot_print_gs1** (Boolean) → Print GS1 Barcodes for Lots & Serial Numbers


  - **group_lot_on_delivery_slip** (Boolean) → Display Lots & Serial Numbers on Delivery Slips


  - **group_stock_tracking_lot** (Boolean) → Packages


  - **group_stock_tracking_owner** (Boolean) → Consignment


  - **group_stock_adv_location** (Boolean) → Multi-Step Routes


  - **group_warning_stock** (Boolean) → Warnings for Stock


  - **group_stock_sign_delivery** (Boolean) → Signature


  - **module_stock_picking_batch** (Boolean) → Batch, Wave & Cluster Transfers


  - **module_stock_barcode** (Boolean) → Barcode Scanner


  - **module_stock_barcode_barcodelookup** (Boolean) → Stock Barcode Database


  - **stock_move_email_validation** (Boolean)


  - **module_stock_sms** (Boolean) → SMS Confirmation


  - **module_delivery** (Boolean) → Delivery Methods


  - **module_delivery_dhl** (Boolean) → DHL Express Connector


  - **module_delivery_fedex** (Boolean) → FedEx Connector


  - **module_delivery_ups** (Boolean) → UPS Connector


  - **module_delivery_usps** (Boolean) → USPS Connector


  - **module_delivery_bpost** (Boolean) → bpost Connector


  - **module_delivery_easypost** (Boolean) → Easypost Connector


  - **module_delivery_sendcloud** (Boolean) → Sendcloud Connector


  - **module_delivery_shiprocket** (Boolean) → Shiprocket Connector


  - **module_delivery_starshipit** (Boolean) → Starshipit Connector


  - **module_quality_control** (Boolean) → Quality


  - **module_quality_control_worksheet** (Boolean) → Quality Worksheet


  - **group_stock_multi_locations** (Boolean) → Storage Locations


  - **annual_inventory_month** (Selection)


  - **annual_inventory_day** (Integer)


  - **group_stock_reception_report** (Boolean) → Reception Report


  - **module_stock_dropshipping** (Boolean) → Dropshipping


  - **barcode_separator** (Char) → Separator


  - **module_stock_fleet** (Boolean) → Dispatch Management System





### stock.move.line


- Hereda de: Base



- Campos:

  - **picking_id** (Many2one) → stock.picking


  - **move_id** (Many2one) → stock.move


  - **company_id** (Many2one) → res.company


  - **product_id** (Many2one) → product.product


  - **product_uom_id** (Many2one) → uom.uom


  - **product_uom_category_id** (Many2one)


  - **product_category_name** (Char)


  - **quantity** (Float) → Quantity


  - **quantity_product_uom** (Float) → Quantity in Product UoM


  - **picked** (Boolean) → Picked


  - **package_id** (Many2one) → stock.quant.package


  - **package_level_id** (Many2one) → stock.package_level


  - **lot_id** (Many2one) → stock.lot


  - **lot_name** (Char) → Lot/Serial Number Name


  - **result_package_id** (Many2one) → stock.quant.package


  - **date** (Datetime) → Date


  - **scheduled_date** (Datetime) → Scheduled Date


  - **owner_id** (Many2one) → res.partner


  - **location_id** (Many2one) → stock.location


  - **location_dest_id** (Many2one) → stock.location


  - **location_usage** (Selection)


  - **location_dest_usage** (Selection)


  - **lots_visible** (Boolean)


  - **picking_partner_id** (Many2one)


  - **picking_code** (Selection)


  - **picking_type_id** (Many2one) → stock.picking.type


  - **picking_type_use_create_lots** (Boolean)


  - **picking_type_use_existing_lots** (Boolean)


  - **picking_type_entire_packs** (Boolean)


  - **state** (Selection)


  - **is_inventory** (Boolean)


  - **is_locked** (Boolean)


  - **consume_line_ids** (Many2many) → stock.move.line


  - **produce_line_ids** (Many2many) → stock.move.line


  - **reference** (Char)


  - **tracking** (Selection)


  - **origin** (Char)


  - **description_picking** (Text)


  - **quant_id** (Many2one) → stock.quant


  - **product_packaging_qty** (Float)


  - **picking_location_id** (Many2one)


  - **picking_location_dest_id** (Many2one)





### res.company


- Hereda de:

  - res.company




- Campos:

  - **internal_transit_location_id** (Many2one) → stock.location


  - **stock_move_email_validation** (Boolean) → Email Confirmation picking


  - **stock_mail_confirmation_template_id** (Many2one) → mail.template


  - **annual_inventory_month** (Selection)


  - **annual_inventory_day** (Integer)





### res.partner


- Hereda de:

  - res.partner




- Campos:

  - **property_stock_customer** (Many2one) → stock.location


  - **property_stock_supplier** (Many2one) → stock.location


  - **picking_warn** (Selection)


  - **picking_warn_msg** (Text) → Message for Stock Picking





### stock.storage.category


- Hereda de: Base



- Campos:

  - **name** (Char) → Storage Category


  - **max_weight** (Float) → Max Weight


  - **capacity_ids** (One2many) → stock.storage.category.capacity


  - **product_capacity_ids** (One2many) → stock.storage.category.capacity


  - **package_capacity_ids** (One2many) → stock.storage.category.capacity


  - **allow_new_product** (Selection)


  - **location_ids** (One2many) → stock.location


  - **company_id** (Many2one) → res.company


  - **weight_uom_name** (Char)





### stock.storage.category.capacity


- Hereda de: Base



- Campos:

  - **storage_category_id** (Many2one) → stock.storage.category


  - **product_id** (Many2one) → product.product


  - **package_type_id** (Many2one) → stock.package.type


  - **quantity** (Float) → Quantity


  - **product_uom_id** (Many2one)


  - **company_id** (Many2one) → res.company





### stock.lot


- Hereda de:


  - mail.thread

  - mail.activity.mixin





- Campos:

  - **name** (Char) → Lot/Serial Number


  - **ref** (Char) → Internal Reference


  - **product_id** (Many2one) → product.product


  - **product_uom_id** (Many2one) → uom.uom


  - **quant_ids** (One2many) → stock.quant


  - **product_qty** (Float) → On Hand Quantity


  - **note** (Html)


  - **display_complete** (Boolean)


  - **company_id** (Many2one) → res.company


  - **delivery_ids** (Many2many) → stock.picking


  - **delivery_count** (Integer) → Delivery order count


  - **last_delivery_partner_id** (Many2one) → res.partner


  - **lot_properties** (Properties) → Properties


  - **location_id** (Many2one) → stock.location





### stock.replenish.mixin


- Hereda de: Base



- Campos:

  - **route_id** (Many2one) → stock.route


  - **allowed_route_ids** (Many2many) → stock.route








## Vistas


### stock.scrap

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| search | stock.scrap.search | `stock.stock_scrap_search_view` | - |
| form | stock.scrap.form | `stock.stock_scrap_form_view` | - |
| kanban | stock.scrap.kanban | `stock.stock_scrap_view_kanban` | - |
| list | stock.scrap.list | `stock.stock_scrap_tree_view` | - |
| form | stock.scrap.form2 | `stock.stock_scrap_form_view2` | - |



#### Filtros de búsqueda (stock.stock_scrap_search_view)


**Agrupar por:**
- Product
- Location
- Scrap Location
- Transfer


#### Botones (stock.stock_scrap_form_view)
- **Validate** (object)
- **Stock Operation** (object)
- **action_get_stock_move_lines** (object)


#### Botones (stock.stock_scrap_form_view2)
- **Scrap Products** (object)


### product.product

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | product.product.stock.list | `stock.product_product_stock_tree` | - |



### stock.picking.type

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| search | stock.picking.type.filter | `stock.view_pickingtype_filter` | - |
| list | Operation types | `stock.view_picking_type_tree` | - |
| form | Operation Types | `stock.view_picking_type_form` | - |
| kanban | stock.picking.type.kanban | `stock.stock_picking_type_kanban` | - |



#### Filtros de búsqueda (stock.view_pickingtype_filter)

**Filtros:**
- **Favorites** (`[('is_favorite', '=', True)]`)
- **Archived** (`[('active','=',False)]`)


**Agrupar por:**
- Type of Operation
- Warehouse


### procurement.group

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | procurement.group.form | `stock.procurement_group_form_view` | - |



#### Botones (stock.procurement_group_form_view)
- **Transfers** (action)


### stock.rule

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| search | stock.rule.select | `stock.view_stock_rule_filter` | - |
| list | stock.rule.list | `stock.view_stock_rule_tree` | - |
| form | stock.rule.form | `stock.view_stock_rule_form` | - |



#### Filtros de búsqueda (stock.view_stock_rule_filter)

**Filtros:**
- **Archived** (`[('active','=',False)]`)


**Agrupar por:**
- Route
- Destination Location
- Warehouse


### stock.warehouse.orderpoint

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| kanban | stock.warehouse.orderpoint.kanban | `stock.view_stock_warehouse_orderpoint_kanban` | - |
| list | stock.warehouse.orderpoint.list.editable | `stock.view_warehouse_orderpoint_tree_editable` | - |
| search | stock.warehouse.orderpoint.reorder.search | `stock.stock_reorder_report_search` | - |
| search | stock.warehouse.orderpoint.search | `stock.warehouse_orderpoint_search` | - |
| form | stock.warehouse.orderpoint.form | `stock.view_warehouse_orderpoint_form` | - |



#### Filtros de búsqueda (stock.stock_reorder_report_search)

**Filtros:**
- **Trigger Manual** (`[('trigger', '=', 'manual')]`)
- **To Reorder** (`[('qty_to_order', '>', 0.0)]`)
- **Not Snoozed** (`['|', ('snoozed_until', '=', False), ('snoozed_until', '<=', datetime.date.today().strftime('%Y-%m-%d'))]`)


**Agrupar por:**
- Warehouse
- Location
- Product
- Category


#### Filtros de búsqueda (stock.warehouse_orderpoint_search)

**Filtros:**
- **Archived** (`[('active', '=', False)]`)


**Agrupar por:**
- Warehouse
- Location
- Product


#### Botones (stock.view_warehouse_orderpoint_form)
- **Forecast Description** (action)


### stock.putaway.rule

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | stock.putaway.rule.list | `stock.stock_putaway_list` | - |
| search | stock.putaway.rule.search | `stock.view_putaway_search` | - |



#### Filtros de búsqueda (stock.view_putaway_search)

**Filtros:**
- **Rules on Products** (`[('product_id', '!=', False)]`)
- **Rules on Categories** (`[('category_id' ,'!=', False)]`)


**Agrupar por:**
- Location: When arrives to
- Location: Store to


### product.removal

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | product.removal.form | `stock.view_removal` | - |



### stock.package.type

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | stock.package.type.form | `stock.stock_package_type_form` | - |
| list | stock.package.type.list | `stock.stock_package_type_tree` | - |



### stock.package_level

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | Package Level | `stock.package_level_form_view` | - |
| list | Package Level List Picking | `stock.package_level_tree_view_picking` | - |



### stock.picking

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| activity | stock.picking.view.activity | `stock.stock_picking_view_activity` | - |
| calendar | stock.picking.calendar | `stock.stock_picking_calendar` | - |
| kanban | stock.picking.kanban | `stock.stock_picking_kanban` | - |
| list | stock.picking.list | `stock.vpicktree` | - |
| form | stock.picking.form | `stock.view_picking_form` | - |
| search | stock.picking.internal.search | `stock.view_picking_internal_search` | - |



#### Botones (stock.view_picking_form)
- **Mark as Todo** (object) - Grupos: `base.group_user`
- **Check Availability** (object) - Grupos: `base.group_user`
- **Validate** (object) - Grupos: `stock.group_stock_user`
- **Validate** (object) - Grupos: `stock.group_stock_user`
- **Print** (object) - Grupos: `stock.group_stock_user`
- **Print** (action) - Grupos: `base.group_user`
- **Return** (action) - Grupos: `base.group_user`
- **Cancel** (object) - Grupos: `base.group_user`
- **action_see_returns** (object)
- **Scraps** (object)
- **Packages** (object)
- **%(action_stock_report)d** (action) - Grupos: `stock.group_production_lot`
- **action_view_reception_report** (object) - Grupos: `stock.group_reception_report`
- **action_picking_move_tree** (object) - Grupos: `base.group_no_one`
- **action_detailed_operations** (object)
- **action_next_transfer** (object)
- **action_product_forecast_report** (object)
- **action_product_forecast_report** (object)
- **Put in Pack** (object) - Grupos: `stock.group_tracking_lot`


#### Filtros de búsqueda (stock.view_picking_internal_search)

**Filtros:**
- **To Do** (`['&',('user_id', 'in', [uid, False]),('state','not in',['done','cancel'])]`)
- **My Transfers** (`[('user_id', '=', uid)]`)
- **Starred** (`[('priority', '=', '1')]`)
- **Draft** (`[('state', '=', 'draft')]`)
- **Waiting** (`[('state', 'in', ('confirmed', 'waiting'))]`)
- **Ready** (`[('state', '=', 'assigned')]`)
- **Receipts** (`[('picking_type_code', '=', 'incoming')]`)
- **Deliveries** (`[('picking_type_code', '=', 'outgoing')]`)
- **Internal** (`[('picking_type_code', '=', 'internal')]`)
- **Before** (`[('search_date_category', '=', 'before')]`)
- **Yesterday** (`[('search_date_category', '=', 'yesterday')]`)
- **Today** (`[('search_date_category', '=', 'today')]`)
- **Tomorrow** (`[('search_date_category', '=', 'day_1')]`)
- **The day after tomorrow** (`[('search_date_category', '=', 'day_2')]`)
- **After** (`[('search_date_category', '=', 'after')]`)
- **Late** (`[('state', 'in', ('assigned', 'waiting', 'confirmed')), '|', '|', ('has_deadline_issue', '=', True), ('date_deadline', '<', current_date), ('scheduled_date', '<', current_date)]`)
- **Planning Issues** (`['|', ('delay_alert_date', '!=', False), '&', ('scheduled_date','<', time.strftime('%Y-%m-%d %H:%M:%S')), ('state', 'in', ('assigned', 'waiting', 'confirmed'))]`)
- **Late Availability** (`[('products_availability_state', '=', 'late')]`)
- **Backorders** (`[('backorder_id', '!=', False), ('state', 'in', ('assigned', 'waiting', 'confirmed'))]`)
- **Late Activities** (`[('my_activity_date_deadline', '<', context_today().strftime('%Y-%m-%d'))]`)
- **Today Activities** (`[('my_activity_date_deadline', '=', context_today().strftime('%Y-%m-%d'))]`)
- **Future Activities** (`[('my_activity_date_deadline', '>', context_today().strftime('%Y-%m-%d'))]`)
- **Warnings** (`[('activity_exception_decoration', '!=', False)]`)


**Agrupar por:**
- Status
- Scheduled Date
- Source Document
- Operation Type


### stock.warehouse

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | stock.warehouse | `stock.view_warehouse` | - |
| list | stock.warehouse.list | `stock.view_warehouse_tree` | - |
| search | stock.warehouse.search | `stock.stock_warehouse_view_search` | - |



#### Botones (stock.view_warehouse)
- **Routes** (object)


#### Filtros de búsqueda (stock.stock_warehouse_view_search)

**Filtros:**
- **Archived** (`[('active','=',False)]`)


### stock.quant

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| search | stock.quant.search | `stock.quant_search_view` | - |
| form | stock.quant.form.editable | `stock.view_stock_quant_form_editable` | - |
| list | stock.quant.list.editable | `stock.view_stock_quant_tree_editable` | - |
| list | stock.quant.list | `stock.view_stock_quant_tree_simple` | - |
| pivot | stock.quant.pivot | `stock.view_stock_quant_pivot` | - |
| graph | stock.quant.graph | `stock.stock_quant_view_graph` | - |
| form | stock.quant.duplicated.sn.warning | `stock.duplicated_sn_warning` | - |
| form | view.stock.quant.form | `stock.view_stock_quant_form` | - |
| list | stock.quant.inventory.list.editable | `stock.view_stock_quant_tree_inventory_editable` | - |



#### Filtros de búsqueda (stock.quant_search_view)

**Filtros:**
- **Internal Locations** (`[('location_id.usage','=', 'internal')]`)
- **Transit Locations** (`[('location_id.usage' ,'=', 'transit')]`)
- **On Hand** (`[('on_hand', '=', True)]`)
- **To Count** (`[('inventory_date', '<=', context_today().strftime('%Y-%m-%d'))]`)
- **To Apply** (`[('inventory_quantity_set', '=', True)]`)
- **Starred Products** (`[('is_favorite', '=', True)]`)
- **In Stock** (`[('quantity', '>', 0.0)]`)
- **Conflicts** (`[('is_outdated', '=', True)]`)
- **Negative Stock** (`[('quantity', '<', 0.0)]`)
- **Reservations** (`[('reserved_quantity', '>', 0.0)]`)
- **filter_in_date**
- **My Counts** (`[('user_id', '=', uid)]`)


**Agrupar por:**
- Product
- Product Category
- Location
- Storage Category
- Owner
- Lot/Serial Number
- Package
- Company


### stock.quant.package

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| search | stock.quant.package.search | `stock.quant_package_search_view` | - |
| form | stock.quant.package.form | `stock.view_quant_package_form` | - |
| list | stock.quant.package.list | `stock.view_quant_package_tree` | - |
| kanban | stock.quant.package.kanban | `stock.view_quant_package_kanban` | - |



#### Filtros de búsqueda (stock.quant_package_search_view)

**Filtros:**
- **In internal locations** (`['|', ('location_id.usage', '=', 'internal'), ('location_id', '=', False)]`)


**Agrupar por:**
- Location
- Package Type


#### Botones (stock.view_quant_package_form)
- **Unpack** (object)
- **Package Transfers** (object)


### stock.move.line

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | stock.move.line.list | `stock.view_move_line_tree` | - |
| list | stock.move.line.list.detailed | `stock.view_move_line_tree_detailed` | - |
| form | stock.move.line.form | `stock.view_move_line_form` | - |
| search | stock.move.line.search | `stock.stock_move_line_view_search` | - |
| kanban | stock.move.line.kanban | `stock.view_stock_move_line_kanban` | - |
| pivot | stock.move.line.pivot | `stock.view_stock_move_line_pivot` | - |
| list | stock.move.line.operations.list | `stock.view_stock_move_line_operation_tree` | - |
| list | stock.move.line.operations.list | `stock.view_stock_move_line_detailed_operation_tree` | - |



#### Filtros de búsqueda (stock.stock_move_line_view_search)

**Filtros:**
- **To Do** (`[('state', 'not in', ['done', 'draft', 'cancel'])]`)
- **Done** (`[('state', '=', 'done')]`)
- **Incoming** (`[('picking_id.picking_type_id.code', '=', 'incoming')]`)
- **Outgoing** (`[('picking_id.picking_type_id.code', '=', 'outgoing')]`)
- **Internal** (`[('picking_id.picking_type_id.code', '=', 'internal')]`)
- **Manufacturing** (`[('picking_id.picking_type_id.code', '=', 'mrp_operation')]`)
- **date**
- **Last 30 Days** (`[('date','>=', (context_today() - relativedelta(days=30)).strftime('%Y-%m-%d'))]`)
- **Last 3 Months** (`[('date','>=', (context_today() - relativedelta(months=3)).strftime('%Y-%m-%d'))]`)
- **Last 12 Months** (`[('date','>=', (context_today() - relativedelta(years=1)).strftime('%Y-%m-%d'))]`)
- **Inventory** (`[('is_inventory', '=', True)]`)


**Agrupar por:**
- Product
- Status
- Date
- Transfers
- Location
- Category


### stock.storage.category

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | stock.storage.category.form | `stock.stock_storage_category_form` | - |
| list | stock.storage.category.list | `stock.stock_storage_category_tree` | - |



#### Botones (stock.stock_storage_category_form)
- **Locations** (action)


### stock.storage.category.capacity

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | stock.storage.category.capacity.list | `stock.stock_storage_category_capacity_tree` | - |



### stock.location

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | stock.location.form | `stock.view_location_form` | - |
| search | stock.location.search | `stock.view_location_search` | - |
| list | stock.location.list | `stock.view_location_tree2` | - |



#### Botones (stock.view_location_form)
- **Putaway Rules** (action) - Grupos: `stock.group_stock_multi_locations`
- **Products** (action)
- **Current Stock** (action)


#### Filtros de búsqueda (stock.view_location_search)

**Filtros:**
- **Internal** (`[('usage', '=', 'internal')]`)
- **Customer** (`[('usage', '=', 'customer')]`)
- **Production** (`[('usage', 'in', ['inventory', 'production'])]`)
- **Vendor** (`[('usage', '=', 'supplier')]`)
- **Empty Locations** (`[('is_empty', '=', True)]`)
- **Archived** (`[('active','=',False)]`)


**Agrupar por:**
- Warehouse
- Location Type


### stock.route

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | stock.location.route.list | `stock.stock_location_route_tree` | - |
| form | stock.location.route.form | `stock.stock_location_route_form_view` | - |
| search | stock.location.route.search | `stock.stock_location_route_view_search` | - |



#### Filtros de búsqueda (stock.stock_location_route_view_search)

**Filtros:**
- **Archived** (`[('active','=',False)]`)


### stock.move

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| pivot | stock.move.pivot | `stock.view_move_pivot` | - |
| graph | stock.move.graph | `stock.view_move_graph` | - |
| list | stock.move.list | `stock.view_move_tree` | - |
| list | stock.picking.move.list | `stock.view_picking_move_tree` | - |
| kanban | stock.move.kanban | `stock.view_move_kandan` | - |
| form | stock.move.operations.form | `stock.view_stock_move_operations` | - |
| form | stock.move.form | `stock.view_move_form` | - |
| search | stock.move.search | `stock.view_move_search` | - |
| list | stock.move.tree2 | `stock.view_move_tree_receipt_picking` | - |



#### Filtros de búsqueda (stock.view_move_search)

**Filtros:**
- **Ready** (`[('state','=','assigned')]`)
- **To Do** (`[('state','in',('assigned','confirmed','waiting'))]`)
- **Done** (`[('state','=','done')]`)
- **Incoming** (`[('location_id.usage', 'not in', ('internal', 'transit')), ('location_dest_id.usage', 'in', ('internal', 'transit'))]`)
- **Outgoing** (`[('location_id.usage', 'in', ('internal', 'transit')), ('location_dest_id.usage', 'not in', ('internal', 'transit'))]`)
- **Inventory** (`[('is_inventory', '=', True)]`)
- **Date**


**Agrupar por:**
- Product
- Operation Type
- Picking
- Source Location
- Destination Location
- Status
- Creation Date
- Scheduled Date


### stock.lot

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | stock.production.lot.form | `stock.view_production_lot_form` | - |
| list | stock.production.lot.list | `stock.view_production_lot_tree` | - |
| kanban | stock.production.lot.kanban | `stock.view_production_lot_kanban` | - |
| search | Production Lots Filter | `stock.search_product_lot_filter` | - |



#### Botones (stock.view_production_lot_form)
- **action_lot_open_transfers** (object)
- **action_lot_open_quants** (object)
- **%(action_stock_report)d** (action)


#### Filtros de búsqueda (stock.search_product_lot_filter)

**Filtros:**
- **At Customer** (`[('quant_ids.location_id.usage','=','customer'), ('quant_ids.quantity', '>', 0)]`)
- **On Hand** (`[('product_qty', '>', 0)]`)
- **Creation Date**


**Agrupar por:**
- Product
- Location
- Creation date
- Company


### stock.inventory.warning

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | inventory.reset.warning.view | `stock.inventory_warning_reset_view` | - |
| form | inventory.set.warning.view | `stock.inventory_warning_set_view` | - |



#### Botones (stock.inventory_warning_reset_view)
- **Continue** (object)
- **Discard**


#### Botones (stock.inventory_warning_set_view)
- **Continue** (object)
- **Discard**


### stock.return.picking

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | Return lines | `stock.view_stock_return_picking_form` | - |



#### Botones (stock.view_stock_return_picking_form)
- **Return** (object)
- **Return All** (object)
- **Return for Exchange** (object)


### stock.inventory.conflict

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | stock.inventory.conflict.form.view | `stock.stock_inventory_conflict_form_view` | - |



#### Botones (stock.stock_inventory_conflict_form_view)
- **Keep Counted Quantity** (object)
- **Keep Difference** (object)
- **Discard**


### stock.orderpoint.snooze

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | Stock Orderpoint Snooze | `stock.view_stock_orderpoint_snooze` | - |



#### Botones (stock.view_stock_orderpoint_snooze)
- **Snooze** (object)
- **Discard**


### stock.backorder.confirmation

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | stock_backorder_confirmation | `stock.view_backorder_confirmation` | - |



#### Botones (stock.view_backorder_confirmation)
- **Create Backorder** (object)
- **No Backorder** (object)


### stock.request.count

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | stock.request.count.form.view | `stock.stock_inventory_request_count_form_view` | - |



#### Botones (stock.stock_inventory_request_count_form_view)
- **Confirm** (object)


### lot.label.layout

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | lot.label.layout.form | `stock.lot_label_layout_form_picking` | - |



#### Botones (stock.lot_label_layout_form_picking)
- **Confirm** (object)


### stock.change.product.qty

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | Change Product Quantity | `stock.view_change_product_quantity` | - |



#### Botones (stock.view_change_product_quantity)
- **Apply** (object)


### stock.quant.relocate

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | Stock Relocation | `stock.stock_quant_relocate_view_form` | - |



#### Botones (stock.stock_quant_relocate_view_form)
- **Confirm** (object)


### picking.label.type

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | picking.label.type.form | `stock.picking_label_type_form` | - |



#### Botones (stock.picking_label_type_form)
- **Confirm** (object)


### stock.warn.insufficient.qty

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | stock.warn.insufficient.qty | `stock.stock_warn_insufficient_qty_form_view` | - |



#### Botones (stock.stock_warn_insufficient_qty_form_view)
- **Discard**
- **Confirm** (object)


### stock.rules.report

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | Stock Rules Report | `stock.view_stock_rules_report` | - |



#### Botones (stock.view_stock_rules_report)
- **Overview** (object)


### stock.replenishment.info

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | Stock Replenishment Information | `stock.view_stock_replenishment_info` | - |



### stock.replenishment.option

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | stock.replenishment.option.list.view | `stock.replenishment_option_tree_view` | - |
| form | stock.replenishment.warning.view | `stock.replenishment_option_warning_view` | - |



#### Botones (stock.replenishment_option_warning_view)
- **order_avbl** (object)
- **order_all** (object)


### product.replenish

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | Replenish | `stock.view_product_replenish` | - |



#### Botones (stock.view_product_replenish)
- **Confirm** (object)


### stock.package.destination

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | stock.package.destination.view | `stock.stock_package_destination_form_view` | - |



#### Botones (stock.stock_package_destination_form_view)
- **Confirm** (object)
- **Discard**


### stock.quantity.history

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | Inventory Report at Date | `stock.view_stock_quantity_history` | - |



#### Botones (stock.view_stock_quantity_history)
- **Confirm** (object)


### stock.track.confirmation

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | stock.track.confirmation.view.form | `stock.view_stock_track_confirmation` | - |



#### Botones (stock.view_stock_track_confirmation)
- **Apply** (object)


### stock.inventory.adjustment.name

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | stock.inventory.adjustment.name.form.view | `stock.stock_inventory_adjustment_name_form_view` | - |



#### Botones (stock.stock_inventory_adjustment_name_form_view)
- **Update Quantities** (object)
- **Discard**


### stock.lot.report

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | stock.lot.report.view.list | `stock.stock_lot_customer_report_view_list` | - |
| search | Customer Lots Filter | `stock.search_customer_lot_filter` | - |



#### Filtros de búsqueda (stock.search_customer_lot_filter)

**Filtros:**
- **Delivery Date**
- **Unreturned** (`[('has_return', '=', False)]`)


**Agrupar por:**
- Product
- Address
- Lot / Serial Number
- Delivery date


### report.stock.quantity

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| graph | stock_report_view_graph | `stock.stock_report_view_graph` | - |


