# Módulo: Warehouse Management: Batch Transfer

## Información General
- **Nombre técnico:** stock_picking_batch
- **Versión:** 1.0
- **Categoría:** Inventory/Inventory
- **Dependencias:** stock




## Descripción

This module adds the batch transfer option in warehouse management
==================================================================
    



## Modelos

### stock.warehouse


- Hereda de:

  - stock.warehouse




- No agrega campos




### stock.picking.batch


- Hereda de:


  - mail.thread

  - mail.activity.mixin





#### Campos
- **name** (Char)
- **description** (Char) → Description
- **user_id** (Many2one) → res.users
- **company_id** (Many2one) → res.company
- **picking_ids** (One2many) → stock.picking
- **show_check_availability** (Boolean)
- **show_allocation** (Boolean)
- **allowed_picking_ids** (One2many) → stock.picking
- **move_ids** (One2many) → stock.move
- **move_line_ids** (One2many) → stock.move.line
- **state** (Selection)
- **picking_type_id** (Many2one) → stock.picking.type
- **warehouse_id** (Many2one) → stock.warehouse
- **picking_type_code** (Selection)
- **scheduled_date** (Datetime) → Scheduled Date
- **is_wave** (Boolean) → This batch is a wave
- **show_lots_text** (Boolean)
- **estimated_shipping_weight** (Float) → shipping_weight
- **estimated_shipping_volume** (Float) → shipping_volume
- **properties** (Properties) → Properties





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | stock.picking.batch.form | `stock_picking_batch.stock_picking_batch_form` | - |
| list | stock.picking.batch.list | `stock_picking_batch.stock_picking_batch_tree` | - |
| kanban | stock.picking.batch.kanban | `stock_picking_batch.stock_picking_batch_kanban` | - |
| calendar | stock.picking.batch.calendar | `stock_picking_batch.stock_picking_batch_calendar` | - |
| search | stock.picking.batch.filter | `stock_picking_batch.stock_picking_batch_filter` | - |



**Botones (stock_picking_batch.stock_picking_batch_form):**
- **Confirm** (object)
- **Validate** (object)
- **Check Availability** (object)
- **Validate** (object)
- **Check Availability** (object)
- **Print** (object)
- **Print Labels** (object)
- **Cancel** (object)
- **Allocation** (object) - Grupos: `stock.group_reception_report`
- **Put in Pack** (object) - Grupos: `stock.group_tracking_lot`


**Filtros de búsqueda (stock_picking_batch.stock_picking_batch_filter):**

- **To Do** (`['&',('user_id', 'in', [uid, False]),('state','not in',['done','cancel'])]`)
- **My Transfers** (`[('user_id', '=', uid)]`)
- **Draft** (`[('state', '=', 'draft')]`)
- **In Progress** (`[('state', '=', 'in_progress')]`)
- **Done** (`[('state', '=', 'done')]`)
- **Late Activities** (`[('my_activity_date_deadline', '<', context_today().strftime('%Y-%m-%d'))]`)
- **Today Activities** (`[('my_activity_date_deadline', '=', context_today().strftime('%Y-%m-%d'))]`)
- **Future Activities** (`[('my_activity_date_deadline', '>', context_today().strftime('%Y-%m-%d'))]`)


*Agrupar por:*
- Responsible
- State



### stock.move


- Hereda de:

  - stock.move




- No agrega campos




### stock.picking.type


- Hereda de:

  - stock.picking.type




#### Campos
- **count_picking_batch** (Integer)
- **count_picking_wave** (Integer)
- **auto_batch** (Boolean) → Automatic Batches
- **batch_group_by_partner** (Boolean) → Contact
- **batch_group_by_destination** (Boolean) → Destination Country
- **batch_group_by_src_loc** (Boolean) → Group by Source Location
- **batch_group_by_dest_loc** (Boolean) → Group by Destination Location
- **wave_group_by_product** (Boolean) → Product
- **wave_group_by_category** (Boolean) → Product Category
- **wave_category_ids** (Many2many) → product.category
- **wave_group_by_location** (Boolean) → Location
- **wave_location_ids** (Many2many) → stock.location
- **batch_max_lines** (Integer) → Maximum lines
- **batch_max_pickings** (Integer) → Maximum transfers
- **batch_auto_confirm** (Boolean) → Auto-confirm
- **batch_properties_definition** (PropertiesDefinition) → Batch Properties





### stock.picking


- Hereda de:

  - stock.picking




#### Campos
- **batch_id** (Many2one) → stock.picking.batch
- **batch_sequence** (Integer)





### stock.move.line


- Hereda de:

  - stock.move.line




#### Campos
- **batch_id** (Many2one)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | stock_picking_batch.move.line.list | `stock_picking_batch.view_move_line_tree` | - |









## Vistas Adicionales


### stock.add.to.wave

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | stock.add.to.wave.form | `stock_picking_batch.stock_add_to_wave_form` | - |



**Botones (stock_picking_batch.stock_add_to_wave_form):**
- **Confirm** (object)


### stock.picking.to.batch

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | stock.picking.to.batch.form | `stock_picking_batch.stock_picking_to_batch_form` | - |



**Botones (stock_picking_batch.stock_picking_to_batch_form):**
- **Confirm** (object)



