# Módulo: Manufacturing

## Información General
- **Nombre técnico:** mrp
- **Versión:** 2.0
- **Categoría:** Manufacturing/Manufacturing
- **Dependencias:** product, stock, resource


## Propósito
Manufacturing Orders & BOMs





## Modelos

### stock.traceability.report


- Hereda de:

  - stock.traceability.report




- No agrega campos



### mrp.bom


- Hereda de:


  - mail.thread

  - product.catalog.mixin





- Campos:

  - **code** (Char) → Reference


  - **active** (Boolean) → Active


  - **type** (Selection)


  - **product_tmpl_id** (Many2one) → product.template


  - **product_id** (Many2one) → product.product


  - **bom_line_ids** (One2many) → mrp.bom.line


  - **byproduct_ids** (One2many) → mrp.bom.byproduct


  - **product_qty** (Float) → Quantity


  - **product_uom_id** (Many2one) → uom.uom


  - **product_uom_category_id** (Many2one)


  - **sequence** (Integer) → Sequence


  - **operation_ids** (One2many) → mrp.routing.workcenter


  - **ready_to_produce** (Selection)


  - **picking_type_id** (Many2one) → stock.picking.type


  - **company_id** (Many2one) → res.company


  - **consumption** (Selection)


  - **possible_product_template_attribute_value_ids** (Many2many) → product.template.attribute.value


  - **allow_operation_dependencies** (Boolean) → Operation Dependencies


  - **produce_delay** (Integer) → Manufacturing Lead Time


  - **days_to_prepare_mo** (Integer)





### mrp.bom.line


- Hereda de: Base



- Campos:

  - **product_id** (Many2one) → product.product


  - **product_tmpl_id** (Many2one) → product.template


  - **company_id** (Many2one)


  - **product_qty** (Float) → Quantity


  - **product_uom_id** (Many2one) → uom.uom


  - **product_uom_category_id** (Many2one)


  - **sequence** (Integer) → Sequence


  - **bom_id** (Many2one) → mrp.bom


  - **parent_product_tmpl_id** (Many2one) → product.template


  - **possible_bom_product_template_attribute_value_ids** (Many2many)


  - **bom_product_template_attribute_value_ids** (Many2many) → product.template.attribute.value


  - **allowed_operation_ids** (One2many) → mrp.routing.workcenter


  - **operation_id** (Many2one) → mrp.routing.workcenter


  - **child_bom_id** (Many2one) → mrp.bom


  - **child_line_ids** (One2many) → mrp.bom.line


  - **attachments_count** (Integer) → Attachments Count


  - **tracking** (Selection)


  - **manual_consumption** (Boolean) → Highlight Consumption





### mrp.bom.byproduct


- Hereda de: Base



- Campos:

  - **product_id** (Many2one) → product.product


  - **company_id** (Many2one)


  - **product_qty** (Float) → Quantity


  - **product_uom_category_id** (Many2one)


  - **product_uom_id** (Many2one) → uom.uom


  - **bom_id** (Many2one) → mrp.bom


  - **allowed_operation_ids** (One2many) → mrp.routing.workcenter


  - **operation_id** (Many2one) → mrp.routing.workcenter


  - **possible_bom_product_template_attribute_value_ids** (Many2many)


  - **bom_product_template_attribute_value_ids** (Many2many) → product.template.attribute.value


  - **sequence** (Integer) → Sequence


  - **cost_share** (Float) → Cost Share (%)





### product.document


- Hereda de:

  - product.document




- Campos:

  - **attached_on_mrp** (Selection)





### stock.warehouse


- Hereda de:

  - stock.warehouse




- Campos:

  - **manufacture_to_resupply** (Boolean) → Manufacture to Resupply


  - **manufacture_pull_id** (Many2one) → stock.rule


  - **manufacture_mto_pull_id** (Many2one) → stock.rule


  - **pbm_mto_pull_id** (Many2one) → stock.rule


  - **sam_rule_id** (Many2one) → stock.rule


  - **manu_type_id** (Many2one) → stock.picking.type


  - **pbm_type_id** (Many2one) → stock.picking.type


  - **sam_type_id** (Many2one) → stock.picking.type


  - **manufacture_steps** (Selection)


  - **pbm_route_id** (Many2one) → stock.route


  - **pbm_loc_id** (Many2one) → stock.location


  - **sam_loc_id** (Many2one) → stock.location





### stock.warehouse.orderpoint


- Hereda de:

  - stock.warehouse.orderpoint




- No agrega campos



### mrp.production


- Hereda de:


  - mail.thread

  - mail.activity.mixin

  - product.catalog.mixin





- Campos:

  - **name** (Char) → Reference


  - **priority** (Selection)


  - **backorder_sequence** (Integer) → Backorder Sequence


  - **origin** (Char) → Source


  - **product_id** (Many2one) → product.product


  - **product_variant_attributes** (Many2many) → product.template.attribute.value


  - **valid_product_template_attribute_line_ids** (Many2many)


  - **never_product_template_attribute_value_ids** (Many2many) → product.template.attribute.value


  - **workcenter_id** (Many2one) → mrp.workcenter


  - **product_tracking** (Selection)


  - **product_tmpl_id** (Many2one) → product.template


  - **product_qty** (Float) → Quantity To Produce


  - **product_uom_id** (Many2one) → uom.uom


  - **lot_producing_id** (Many2one) → stock.lot


  - **qty_producing** (Float)


  - **product_uom_category_id** (Many2one)


  - **product_uom_qty** (Float)


  - **picking_type_id** (Many2one) → stock.picking.type


  - **use_create_components_lots** (Boolean)


  - **location_src_id** (Many2one) → stock.location


  - **warehouse_id** (Many2one)


  - **location_dest_id** (Many2one) → stock.location


  - **location_final_id** (Many2one) → stock.location


  - **date_deadline** (Datetime) → Deadline


  - **date_start** (Datetime) → Start


  - **date_finished** (Datetime) → End


  - **duration_expected** (Float) → Expected Duration


  - **duration** (Float) → Real Duration


  - **bom_id** (Many2one) → mrp.bom


  - **state** (Selection)


  - **reservation_state** (Selection)


  - **move_raw_ids** (One2many) → stock.move


  - **move_finished_ids** (One2many) → stock.move


  - **all_move_raw_ids** (One2many) → stock.move


  - **all_move_ids** (One2many) → stock.move


  - **move_byproduct_ids** (One2many) → stock.move


  - **finished_move_line_ids** (One2many) → stock.move.line


  - **workorder_ids** (One2many) → mrp.workorder


  - **move_dest_ids** (One2many) → stock.move


  - **unreserve_visible** (Boolean) → Allowed to Unreserve Production


  - **reserve_visible** (Boolean) → Allowed to Reserve Production


  - **user_id** (Many2one) → res.users


  - **company_id** (Many2one) → res.company


  - **qty_produced** (Float)


  - **procurement_group_id** (Many2one) → procurement.group


  - **product_description_variants** (Char) → Custom Description


  - **orderpoint_id** (Many2one) → stock.warehouse.orderpoint


  - **propagate_cancel** (Boolean) → Propagate cancel and split


  - **delay_alert_date** (Datetime) → Delay Alert Date


  - **json_popover** (Char) → JSON data for the popover widget


  - **scrap_ids** (One2many) → stock.scrap


  - **scrap_count** (Integer)


  - **unbuild_ids** (One2many) → mrp.unbuild


  - **unbuild_count** (Integer)


  - **is_locked** (Boolean) → Is Locked


  - **is_planned** (Boolean) → Its Operations are Planned


  - **show_final_lots** (Boolean) → Show Final Lots


  - **production_location_id** (Many2one) → stock.location


  - **picking_ids** (Many2many) → stock.picking


  - **delivery_count** (Integer)


  - **consumption** (Selection)


  - **mrp_production_child_count** (Integer) → Number of generated MO


  - **mrp_production_source_count** (Integer) → Number of source MO


  - **mrp_production_backorder_count** (Integer) → Count of linked backorder


  - **show_lock** (Boolean) → Show Lock/unlock buttons


  - **components_availability** (Char)


  - **components_availability_state** (Selection)


  - **production_capacity** (Float)


  - **show_lot_ids** (Boolean) → Display the serial number shortcut on the moves


  - **forecasted_issue** (Boolean)


  - **show_allocation** (Boolean)


  - **allow_workorder_dependencies** (Boolean) → Allow Work Order Dependencies


  - **show_produce** (Boolean)


  - **show_produce_all** (Boolean)


  - **is_outdated_bom** (Boolean) → Outdated BoM


  - **is_delayed** (Boolean)


  - **search_date_category** (Selection)





### stock.move.line


- Hereda de:

  - stock.move.line




- Campos:

  - **workorder_id** (Many2one) → mrp.workorder


  - **production_id** (Many2one) → mrp.production


  - **description_bom_line** (Char)





### stock.move


- Hereda de:

  - stock.move




- Campos:

  - **created_production_id** (Many2one) → mrp.production


  - **production_id** (Many2one) → mrp.production


  - **raw_material_production_id** (Many2one) → mrp.production


  - **unbuild_id** (Many2one) → mrp.unbuild


  - **consume_unbuild_id** (Many2one) → mrp.unbuild


  - **allowed_operation_ids** (One2many) → mrp.routing.workcenter


  - **operation_id** (Many2one) → mrp.routing.workcenter


  - **workorder_id** (Many2one) → mrp.workorder


  - **bom_line_id** (Many2one) → mrp.bom.line


  - **byproduct_id** (Many2one) → mrp.bom.byproduct


  - **unit_factor** (Float) → Unit Factor


  - **is_done** (Boolean) → Done


  - **order_finished_lot_id** (Many2one) → stock.lot


  - **should_consume_qty** (Float) → Quantity To Consume


  - **cost_share** (Float) → Cost Share (%)


  - **product_qty_available** (Float) → Product On Hand Quantity


  - **product_virtual_available** (Float) → Product Forecasted Quantity


  - **description_bom_line** (Char) → Kit


  - **manual_consumption** (Boolean) → Manual Consumption





### stock.quant


- Hereda de:

  - stock.quant




- No agrega campos



### stock.scrap


- Hereda de:

  - stock.scrap




- Campos:

  - **production_id** (Many2one) → mrp.production


  - **workorder_id** (Many2one) → mrp.workorder


  - **product_is_kit** (Boolean)


  - **product_template** (Many2one)


  - **bom_id** (Many2one) → mrp.bom





### mrp.workorder


- Hereda de: Base



- Campos:

  - **name** (Char) → Work Order


  - **sequence** (Integer) → Sequence


  - **barcode** (Char)


  - **workcenter_id** (Many2one) → mrp.workcenter


  - **working_state** (Selection)


  - **product_id** (Many2one)


  - **product_tracking** (Selection)


  - **product_uom_id** (Many2one) → uom.uom


  - **production_id** (Many2one) → mrp.production


  - **production_availability** (Selection)


  - **production_state** (Selection)


  - **production_bom_id** (Many2one) → mrp.bom


  - **qty_production** (Float) → Original Production Quantity


  - **company_id** (Many2one)


  - **qty_producing** (Float)


  - **qty_remaining** (Float) → Quantity To Be Produced


  - **qty_produced** (Float) → Quantity


  - **is_produced** (Boolean)


  - **state** (Selection)


  - **leave_id** (Many2one) → resource.calendar.leaves


  - **date_start** (Datetime) → Start


  - **date_finished** (Datetime) → End


  - **duration_expected** (Float) → Expected Duration


  - **duration** (Float) → Real Duration


  - **duration_unit** (Float) → Duration Per Unit


  - **duration_percent** (Integer) → Duration Deviation (%)


  - **progress** (Float) → Progress Done (%)


  - **operation_id** (Many2one) → mrp.routing.workcenter


  - **has_worksheet** (Boolean)


  - **worksheet** (Binary) → Worksheet


  - **worksheet_type** (Selection)


  - **worksheet_google_slide** (Char) → Worksheet URL


  - **operation_note** (Html) → Description


  - **move_raw_ids** (One2many) → stock.move


  - **move_finished_ids** (One2many) → stock.move


  - **move_line_ids** (One2many) → stock.move.line


  - **finished_lot_id** (Many2one) → stock.lot


  - **time_ids** (One2many) → mrp.workcenter.productivity


  - **is_user_working** (Boolean) → Is the Current User Working


  - **working_user_ids** (One2many) → res.users


  - **last_working_user_id** (One2many) → res.users


  - **costs_hour** (Float)


  - **scrap_ids** (One2many) → stock.scrap


  - **scrap_count** (Integer)


  - **production_date** (Datetime) → Production Date


  - **json_popover** (Char) → Popover Data JSON


  - **show_json_popover** (Boolean) → Show Popover?


  - **consumption** (Selection)


  - **qty_reported_from_previous_wo** (Float) → Carried Quantity


  - **is_planned** (Boolean)


  - **allow_workorder_dependencies** (Boolean)


  - **blocked_by_workorder_ids** (Many2many) → mrp.workorder


  - **needed_by_workorder_ids** (Many2many) → mrp.workorder





### stock.warehouse.orderpoint


- Hereda de:

  - stock.warehouse.orderpoint




- Campos:

  - **show_bom** (Boolean) → Show BoM column


  - **bom_id** (Many2one) → mrp.bom


  - **manufacturing_visibility_days** (Float)





### mrp.routing.workcenter


- Hereda de:


  - mail.thread

  - mail.activity.mixin





- Campos:

  - **name** (Char) → Operation


  - **active** (Boolean)


  - **workcenter_id** (Many2one) → mrp.workcenter


  - **sequence** (Integer) → Sequence


  - **bom_id** (Many2one) → mrp.bom


  - **company_id** (Many2one) → res.company


  - **worksheet_type** (Selection)


  - **note** (Html) → Description


  - **worksheet** (Binary) → PDF


  - **worksheet_google_slide** (Char) → Google Slide


  - **time_mode** (Selection)


  - **time_mode_batch** (Integer) → Based on


  - **time_computed_on** (Char) → Computed on last


  - **time_cycle_manual** (Float) → Manual Duration


  - **time_cycle** (Float) → Duration


  - **workorder_count** (Integer) → # Work Orders


  - **workorder_ids** (One2many) → mrp.workorder


  - **possible_bom_product_template_attribute_value_ids** (Many2many)


  - **bom_product_template_attribute_value_ids** (Many2many) → product.template.attribute.value


  - **allow_operation_dependencies** (Boolean)


  - **blocked_by_operation_ids** (Many2many) → mrp.routing.workcenter


  - **needed_by_operation_ids** (Many2many) → mrp.routing.workcenter





### mrp.workcenter


- Hereda de:


  - mail.thread

  - resource.mixin





- Campos:

  - **name** (Char) → Work Center


  - **time_efficiency** (Float) → Time Efficiency


  - **active** (Boolean) → Active


  - **code** (Char) → Code


  - **note** (Html) → Description


  - **default_capacity** (Float) → Capacity


  - **sequence** (Integer) → Sequence


  - **color** (Integer) → Color


  - **currency_id** (Many2one) → res.currency


  - **costs_hour** (Float)


  - **time_start** (Float) → Setup Time


  - **time_stop** (Float) → Cleanup Time


  - **routing_line_ids** (One2many) → mrp.routing.workcenter


  - **has_routing_lines** (Boolean)


  - **order_ids** (One2many) → mrp.workorder


  - **workorder_count** (Integer) → # Work Orders


  - **workorder_ready_count** (Integer) → # Ready Work Orders


  - **workorder_progress_count** (Integer) → Total Running Orders


  - **workorder_pending_count** (Integer) → Total Pending Orders


  - **workorder_late_count** (Integer) → Total Late Orders


  - **time_ids** (One2many) → mrp.workcenter.productivity


  - **working_state** (Selection)


  - **blocked_time** (Float) → Blocked Time


  - **productive_time** (Float) → Productive Time


  - **oee** (Float)


  - **oee_target** (Float)


  - **performance** (Integer) → Performance


  - **workcenter_load** (Float) → Work Center Load


  - **alternative_workcenter_ids** (Many2many) → mrp.workcenter


  - **tag_ids** (Many2many) → mrp.workcenter.tag


  - **capacity_ids** (One2many) → mrp.workcenter.capacity


  - **kanban_dashboard_graph** (Text)


  - **resource_calendar_id** (Many2one)





### mrp.workcenter.tag


- Hereda de: Base



- Campos:

  - **name** (Char) → Tag Name


  - **color** (Integer) → Color Index





### mrp.workcenter.productivity.loss.type


- Hereda de: Base



- Campos:

  - **loss_type** (Selection)





### mrp.workcenter.productivity.loss


- Hereda de: Base



- Campos:

  - **name** (Char) → Blocking Reason


  - **sequence** (Integer) → Sequence


  - **manual** (Boolean) → Is a Blocking Reason


  - **loss_id** (Many2one) → mrp.workcenter.productivity.loss.type


  - **loss_type** (Selection)





### mrp.workcenter.productivity


- Hereda de: Base



- Campos:

  - **production_id** (Many2one) → mrp.production


  - **workcenter_id** (Many2one) → mrp.workcenter


  - **company_id** (Many2one) → res.company


  - **workorder_id** (Many2one) → mrp.workorder


  - **user_id** (Many2one) → res.users


  - **loss_id** (Many2one) → mrp.workcenter.productivity.loss


  - **loss_type** (Selection)


  - **description** (Text) → Description


  - **date_start** (Datetime) → Start Date


  - **date_end** (Datetime) → End Date


  - **duration** (Float) → Duration





### mrp.workcenter.capacity


- Hereda de: Base



- Campos:

  - **workcenter_id** (Many2one) → mrp.workcenter


  - **product_id** (Many2one) → product.product


  - **product_uom_id** (Many2one) → uom.uom


  - **capacity** (Float) → Capacity


  - **time_start** (Float) → Setup Time (minutes)


  - **time_stop** (Float) → Cleanup Time (minutes)





### stock.rule


- Hereda de:

  - stock.rule




- Campos:

  - **action** (Selection)





### procurement.group


- Hereda de:

  - procurement.group




- Campos:

  - **mrp_production_ids** (One2many) → mrp.production





### stock.picking.type


- Hereda de:

  - stock.picking.type




- Campos:

  - **code** (Selection)


  - **count_mo_todo** (Integer)


  - **count_mo_waiting** (Integer)


  - **count_mo_late** (Integer)


  - **count_mo_in_progress** (Integer)


  - **count_mo_to_close** (Integer)


  - **use_create_components_lots** (Boolean)


  - **auto_print_done_production_order** (Boolean) → Auto Print Done Production Order


  - **auto_print_done_mrp_product_labels** (Boolean) → Auto Print Produced Product Labels


  - **mrp_product_label_to_print** (Selection)


  - **auto_print_done_mrp_lot** (Boolean) → Auto Print Produced Lot Label


  - **done_mrp_lot_label_to_print** (Selection)


  - **auto_print_mrp_reception_report** (Boolean) → Auto Print Allocation Report


  - **auto_print_mrp_reception_report_labels** (Boolean) → Auto Print Allocation Report Labels


  - **auto_print_generated_mrp_lot** (Boolean) → Auto Print Generated Lot/SN Label


  - **generated_mrp_lot_label_to_print** (Selection)





### stock.picking


- Hereda de:

  - stock.picking




- Campos:

  - **has_kits** (Boolean)


  - **production_count** (Integer) → Count of MO generated


  - **production_ids** (Many2many) → mrp.production





### product.template


- Hereda de:

  - product.template




- Campos:

  - **bom_line_ids** (One2many) → mrp.bom.line


  - **bom_ids** (One2many) → mrp.bom


  - **bom_count** (Integer) → # Bill of Material


  - **used_in_bom_count** (Integer) → # of BoM Where is Used


  - **mrp_product_qty** (Float) → Manufactured


  - **is_kits** (Boolean)





### product.product


- Hereda de:

  - product.product




- Campos:

  - **variant_bom_ids** (One2many) → mrp.bom


  - **bom_line_ids** (One2many) → mrp.bom.line


  - **bom_count** (Integer) → # Bill of Material


  - **used_in_bom_count** (Integer) → # BoM Where Used


  - **mrp_product_qty** (Float) → Manufactured


  - **is_kits** (Boolean)


  - **product_catalog_product_is_in_bom** (Boolean)


  - **product_catalog_product_is_in_mo** (Boolean)





### res.config.settings


- Hereda de:

  - res.config.settings




- Campos:

  - **manufacturing_lead** (Float)


  - **use_manufacturing_lead** (Boolean)


  - **group_mrp_byproducts** (Boolean) → By-Products


  - **module_mrp_mps** (Boolean) → Master Production Schedule


  - **module_mrp_plm** (Boolean) → Product Lifecycle Management (PLM)


  - **module_quality_control** (Boolean) → Quality


  - **module_quality_control_worksheet** (Boolean) → Quality Worksheet


  - **module_mrp_subcontracting** (Boolean) → Subcontracting


  - **group_mrp_routings** (Boolean) → MRP Work Orders


  - **group_unlocked_by_default** (Boolean) → Unlock Manufacturing Orders


  - **group_mrp_reception_report** (Boolean) → Allocation Report for Manufacturing Orders


  - **group_mrp_workorder_dependencies** (Boolean) → Work Order Dependencies





### res.company


- Hereda de:

  - res.company




- Campos:

  - **manufacturing_lead** (Float) → Manufacturing Lead Time





### mrp.unbuild


- Hereda de:


  - mail.thread

  - mail.activity.mixin





- Campos:

  - **name** (Char) → Reference


  - **product_id** (Many2one) → product.product


  - **company_id** (Many2one) → res.company


  - **product_qty** (Float) → Quantity


  - **product_uom_id** (Many2one) → uom.uom


  - **bom_id** (Many2one) → mrp.bom


  - **mo_id** (Many2one) → mrp.production


  - **mo_bom_id** (Many2one) → mrp.bom


  - **lot_id** (Many2one) → stock.lot


  - **has_tracking** (Selection)


  - **location_id** (Many2one) → stock.location


  - **location_dest_id** (Many2one) → stock.location


  - **consume_line_ids** (One2many) → stock.move


  - **produce_line_ids** (One2many) → stock.move


  - **state** (Selection)





### stock.lot


- Hereda de:

  - stock.lot




- No agrega campos



### stock.replenish.mixin


- Hereda de:

  - stock.replenish.mixin




- Campos:

  - **bom_id** (Many2one) → mrp.bom


  - **show_bom** (Boolean)








## Vistas


### mrp.unbuild

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| search | mrp.unbuild.search | `mrp.mrp_unbuild_search_view` | - |
| kanban | mrp.unbuild.kanban | `mrp.mrp_unbuild_kanban_view` | - |
| form | mrp.unbuild.form | `mrp.mrp_unbuild_form_view` | - |
| form | mrp.unbuild.form.simplified | `mrp.mrp_unbuild_form_view_simplified` | - |
| list | mrp.unbuild.list | `mrp.mrp_unbuild_tree_view` | - |



#### Filtros de búsqueda (mrp.mrp_unbuild_search_view)

**Filtros:**
- **Draft** (`[('state', '=', 'draft')]`)
- **Done** (`[('state', '=', 'done')]`)
- **Late Activities** (`[('my_activity_date_deadline', '<', context_today().strftime('%Y-%m-%d'))]`)
- **Today Activities** (`[('my_activity_date_deadline', '=', context_today().strftime('%Y-%m-%d'))]`)
- **Future Activities** (`[('my_activity_date_deadline', '>', context_today().strftime('%Y-%m-%d'))]`)


**Agrupar por:**
- Product
- Manufacturing Order


#### Botones (mrp.mrp_unbuild_form_view)
- **Unbuild** (object)
- **%(action_mrp_unbuild_moves)d** (action)


#### Botones (mrp.mrp_unbuild_form_view_simplified)
- **Unbuild** (object)


### mrp.production

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| activity | mrp.production.view.activity | `mrp.mrp_production_view_activity` | - |
| list | mrp.production.list | `mrp.mrp_production_tree_view` | - |
| form | mrp.production.form | `mrp.mrp_production_form_view` | - |
| kanban | mrp.production.kanban | `mrp.mrp_production_kanban_view` | - |
| calendar | mrp.production.calendar | `mrp.view_production_calendar` | - |
| pivot | mrp.production.pivot | `mrp.view_production_pivot` | - |
| graph | mrp.production.graph | `mrp.view_production_graph` | - |
| search | mrp.production.select | `mrp.view_mrp_production_filter` | - |



#### Botones (mrp.mrp_production_form_view)
- **Produce** (object)
- **Produce All** (object)
- **Produce** (object)
- **Produce All** (object)
- **Confirm** (object)
- **Plan** (object)
- **Unplan** (object)
- **Start** (object)
- **Check availability** (object)
- **Unreserve** (object)
- **Cancel** (object)
- **Unbuild** (object)
- **Allocation** (object) - Grupos: `mrp.group_mrp_reception_report`
- **action_view_mrp_production_childs** (object)
- **action_view_mrp_production_sources** (object)
- **action_view_mrp_production_backorders** (object)
- **action_view_mrp_production_unbuilds** (object)
- **action_see_move_scrap** (object)
- **action_view_mo_delivery** (object) - Grupos: `base.group_user`
- **Traceability** (action) - Grupos: `stock.group_production_lot`
- **%(action_mrp_production_moves)d** (action)
- **%(action_report_mo_overview)d** (action)
- **%(mrp.action_change_production_qty)d** (action)
- **action_product_forecast_report** (object)
- **action_product_forecast_report** (object)
- **action_generate_bom** (object) - Grupos: `mrp.group_mrp_manager`
- **Update BoM** (object)
- **action_generate_serial** (object)
- **Catalog** (object)
- **action_product_forecast_report** (object)
- **action_product_forecast_report** (object)
- **Catalog** (object)


#### Filtros de búsqueda (mrp.view_mrp_production_filter)

**Filtros:**
- **To Do** (`[('state', 'in', ('draft', 'confirmed', 'progress', 'to_close'))]`)
- **Unbuilt** (`[('unbuild_ids.state', '=', 'done')]`)
- **Done** (`[('state', '=', 'done')]`)
- **Cancelled** (`[('state', '=', 'cancel')]`)
- **Starred** (`[('priority', '=', '1')]`)
- **Draft** (`[('state', '=', 'draft')]`)
- **Confirmed** (`[('state', '=', 'confirmed')]`)
- **Planned** (`[('is_planned', '=', True)]`)
- **In Progress** (`[('state', '=', 'progress')]`)
- **To Close** (`[('state', '=', 'to_close')]`)
- **MO Pending** (`[('reservation_state', '=', 'waiting')]`)
- **MO Ready** (`[('reservation_state', '=', 'assigned')]`)
- **Before** (`[('search_date_category', '=', 'before')]`)
- **Yesterday** (`[('search_date_category', '=', 'yesterday')]`)
- **Today** (`[('search_date_category', '=', 'today')]`)
- **Tomorrow** (`[('search_date_category', '=', 'day_1')]`)
- **The day after tomorrow** (`[('search_date_category', '=', 'day_2')]`)
- **After** (`[('search_date_category', '=', 'after')]`)
- **Late** (`[('date_start', '<', context_today()), ('state', '=', 'confirmed')]`)
- **Delayed Productions** (`['|', ('delay_alert_date', '!=', False), ('is_delayed', '=', True)]`)
- **Components Available** (`[('components_availability_state', '=', 'available')]`)
- **Late Availability** (`[('components_availability_state', '=', 'late')]`)
- **My MOs** (`[('user_id', '=', uid)]`)
- **Late Activities** (`[('my_activity_date_deadline', '<', context_today().strftime('%Y-%m-%d'))]`)
- **Today Activities** (`[('my_activity_date_deadline', '=', context_today().strftime('%Y-%m-%d'))]`)
- **Future Activities** (`[('my_activity_date_deadline', '>', context_today().strftime('%Y-%m-%d'))]`)
- **Date**
- **Date: Last 365 Days** (`[('date_start', '>', (datetime.datetime.now() + relativedelta(days=-365)).to_utc().strftime('%Y-%m-%d %H:%M:%S'))]`)
- **Warnings** (`[('activity_exception_decoration', '!=', False)]`)


**Agrupar por:**
- Product
- Status
- Material Availability
- Procurement Group
- Date


### mrp.bom.byproduct

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | mrp.bom.byproduct.form | `mrp.mrp_bom_byproduct_form_view` | - |



### mrp.bom

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | mrp.bom.form | `mrp.mrp_bom_form_view` | - |
| list | mrp.bom.list | `mrp.mrp_bom_tree_view` | - |
| kanban | mrp.bom.kanban | `mrp.mrp_bom_kanban_view` | - |
| search | mrp.bom.select | `mrp.view_mrp_bom_filter` | - |



#### Botones (mrp.mrp_bom_form_view)
- **%(action_mrp_routing_time)d** (action) - Grupos: `mrp.group_mrp_routings`
- **%(action_report_mrp_bom)d** (action)
- **Catalog** (object)
- **action_see_attachments** (object)
- **Catalog** (object)
- **Compute** (object)


#### Filtros de búsqueda (mrp.view_mrp_bom_filter)

**Filtros:**
- **Manufacturing** (`[('type', '=', 'normal')]`)
- **Kit** (`[('type', '=', 'phantom')]`)
- **Archived** (`[('active', '=', False)]`)


**Agrupar por:**
- Product
- BoM Type
- Unit of Measure


### mrp.bom.line

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | mrp.bom.line.view.form | `mrp.mrp_bom_line_view_form` | - |



### mrp.workcenter

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | mrp.workcenter.list | `mrp.mrp_workcenter_tree_view` | - |
| kanban | mrp.workcenter.kanban | `mrp.mrp_workcenter_view_kanban` | - |
| kanban | mrp.workcenter.kanban | `mrp.mrp_workcenter_kanban` | - |
| form | mrp.workcenter.form | `mrp.mrp_workcenter_view` | - |
| search | mrp.workcenter.search | `mrp.view_mrp_workcenter_search` | - |



#### Botones (mrp.mrp_workcenter_view)
- **action_show_operations** (object)
- **%(mrp_workcenter_productivity_report_oee)d** (action)
- **%(mrp_workcenter_productivity_report_blocked)d** (action)
- **%(action_mrp_workcenter_load_report_graph)d** (action)
- **%(mrp_workorder_report)d** (action)


#### Filtros de búsqueda (mrp.view_mrp_workcenter_search)

**Filtros:**
- **Archived** (`[('active', '=', False)]`)


**Agrupar por:**
- Company


### mrp.workcenter.productivity

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| graph | mrp.workcenter.productivity.graph | `mrp.oee_pie_view` | - |
| search | mrp.workcenter.productivity.search | `mrp.oee_search_view` | - |
| form | mrp.workcenter.productivity.form | `mrp.oee_form_view` | - |
| list | mrp.workcenter.productivity.list | `mrp.oee_tree_view` | - |
| graph | mrp.workcenter.productivity.graph | `mrp.oee_graph_view` | - |
| pivot | mrp.workcenter.productivity.pivot | `mrp.oee_pivot_view` | - |
| form | mrp.workcenter.productivity.form | `mrp.mrp_workcenter_block_wizard_form` | - |



#### Filtros de búsqueda (mrp.oee_search_view)

**Filtros:**
- **Availability Losses** (`[('loss_type','=','availability')]`)
- **Performance Losses** (`[('loss_type','=','performance')]`)
- **Quality Losses** (`[('loss_type','=','quality')]`)
- **Fully Productive** (`[('loss_type','=','productive')]`)
- **Date**


**Agrupar por:**
- User
- Workcenter
- Loss Reason


#### Botones (mrp.mrp_workcenter_block_wizard_form)
- **Block** (object)


### mrp.workcenter.productivity.loss

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | mrp.workcenter.productivity.loss.form | `mrp.oee_loss_form_view` | - |
| list | mrp.workcenter.productivity.loss.list | `mrp.oee_loss_tree_view` | - |
| kanban | mrp.workcenter.productivity.loss.kanban | `mrp.view_mrp_workcenter_productivity_loss_kanban` | - |
| search | mrp.workcenter.productivity.loss.search | `mrp.oee_loss_search_view` | - |



### mrp.routing.workcenter

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | mrp.routing.workcenter.list | `mrp.mrp_routing_workcenter_tree_view` | - |
| form | mrp.routing.workcenter.form | `mrp.mrp_routing_workcenter_form_view` | - |
| search | mrp.routing.workcenter.filter | `mrp.mrp_routing_workcenter_filter` | - |



#### Filtros de búsqueda (mrp.mrp_routing_workcenter_filter)

**Filtros:**
- **Archived** (`[('active', '=', False)]`)


**Agrupar por:**
- Bill of Material
- Workcenter


### mrp.workorder

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| search | mrp.production.work.order.search | `mrp.view_mrp_production_work_order_search` | - |
| list | mrp.production.work.order.list.editable | `mrp.mrp_production_workorder_tree_editable_view` | - |
| form | mrp.production.work.order.form | `mrp.mrp_production_workorder_form_view_inherit` | - |
| search | mrp.production.work.order.select | `mrp.view_mrp_production_workorder_form_view_filter` | - |
| calendar | mrp.production.work.order.calendar | `mrp.workcenter_line_calendar` | - |
| graph | mrp.production.work.order.graph | `mrp.workcenter_line_graph` | - |
| pivot | mrp.production.work.order.pivot | `mrp.workcenter_line_pivot` | - |
| kanban | mrp.production.work.order.kanban | `mrp.workcenter_line_kanban` | - |
| pivot | report.workcenter.load.pivot | `mrp.view_workcenter_load_pivot` | - |
| graph | report.workcenter.load.graph | `mrp.view_work_center_load_graph` | - |



#### Filtros de búsqueda (mrp.view_mrp_production_work_order_search)

**Filtros:**
- **Ready** (`[('state','=','ready')]`)
- **Waiting** (`[('state','=','waiting')]`)
- **Pending** (`[('state','=','pending')]`)
- **In Progress** (`[('state','=','progress')]`)
- **Done** (`[('state','=', 'done')]`)
- **Late** (`[('date_start','<=',time.strftime('%Y-%m-%d'))]`)
- **Start Date**


**Agrupar por:**
- Work center
- Product


#### Botones (mrp.mrp_production_workorder_form_view_inherit)
- **action_see_move_scrap** (object)
- **View WorkOrder** (object)


#### Filtros de búsqueda (mrp.view_mrp_production_workorder_form_view_filter)

**Filtros:**
- **In Progress** (`[('state', '=', 'progress')]`)
- **Ready** (`[('state', '=', 'ready')]`)
- **Waiting** (`[('state', '=', 'waiting')]`)
- **Pending** (`[('state', '=', 'pending'), ('production_state', '!=', 'draft')]`)
- **Draft** (`[('state', '=', 'pending'), ('production_state', '=', 'draft')]`)
- **Finished** (`[('state', '=', 'done')]`)
- **Late** (`['&', ('date_start', '<', datetime.datetime.now()), ('state', '=', 'ready')]`)


**Agrupar por:**
- Work Center
- Manufacturing Order
- Status
- Date


### mrp.consumption.warning

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | Consumption Warning | `mrp.view_mrp_consumption_warning_form` | - |



#### Botones (mrp.view_mrp_consumption_warning_form)
- **Force** (object) - Grupos: `mrp.group_mrp_manager`
- **Confirm** (object)
- **Set Quantities & Validate** (object)
- **Discard** (object)


### mrp.production.backorder

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | Create Backorder | `mrp.view_mrp_production_backorder_form` | - |



#### Botones (mrp.view_mrp_production_backorder_form)
- **Create backorder** (object)
- **Validate** (object)
- **No Backorder** (object)


### mrp.batch.produce

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | view_mrp_batch_produce_form | `mrp.view_mrp_batch_produce_form` | - |



#### Botones (mrp.view_mrp_batch_produce_form)
- **Generate** (object)
- **Prepare MO** (object)
- **Produce** (object)


### mrp.production.split.multi

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | mrp.production.split.multi.form | `mrp.view_mrp_production_split_multi_form` | - |



#### Botones (mrp.view_mrp_production_split_multi_form)
- **action_prepare_split** (object)


### mrp.production.split

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | Split Production | `mrp.view_mrp_production_split_form` | - |



#### Botones (mrp.view_mrp_production_split_form)
- **Split** (object)
- **Discard** (object)


### change.production.qty

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | Change Quantity To Produce | `mrp.view_change_production_qty_wizard` | - |



#### Botones (mrp.view_change_production_qty_wizard)
- **Set Quantity** (object)

