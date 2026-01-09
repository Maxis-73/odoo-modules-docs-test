# Módulo: Restaurant

## Información General
- **Nombre técnico:** pos_restaurant
- **Versión:** 1.0
- **Categoría:** Sales/Point of Sale
- **Dependencias:** point_of_sale


## Propósito
Restaurant extensions for the Point of Sale 



## Descripción


This module adds several features to the Point of Sale that are specific to restaurant management:
- Bill Printing: Allows you to print a receipt before the order is paid
- Bill Splitting: Allows you to split an order into different orders
- Kitchen Order Printing: allows you to print orders updates to kitchen or bar printers





## Modelos

### restaurant.floor


- Hereda de:


  - pos.load.mixin





- Campos:

  - **name** (Char) → Floor Name


  - **pos_config_ids** (Many2many) → pos.config


  - **background_image** (Binary) → Background Image


  - **background_color** (Char) → Background Color


  - **table_ids** (One2many) → restaurant.table


  - **sequence** (Integer) → Sequence


  - **active** (Boolean)


  - **floor_background_image** (Image)





### restaurant.table


- Hereda de:


  - pos.load.mixin





- Campos:

  - **floor_id** (Many2one) → restaurant.floor


  - **table_number** (Integer) → Table Number


  - **shape** (Selection)


  - **position_h** (Float) → Horizontal Position


  - **position_v** (Float) → Vertical Position


  - **width** (Float) → Width


  - **height** (Float) → Height


  - **seats** (Integer) → Seats


  - **color** (Char) → Color


  - **parent_id** (Many2one) → restaurant.table


  - **active** (Boolean) → Active





### pos.config


- Hereda de:

  - pos.config




- Campos:

  - **iface_splitbill** (Boolean)


  - **iface_printbill** (Boolean)


  - **floor_ids** (Many2many) → restaurant.floor


  - **set_tip_after_payment** (Boolean) → Set Tip After Payment


  - **module_pos_restaurant_appointment** (Boolean) → Table Booking


  - **takeaway** (Boolean) → Takeaway


  - **takeaway_fp_id** (Many2one) → account.fiscal.position





### pos.order


- Hereda de:

  - pos.order




- Campos:

  - **table_id** (Many2one) → restaurant.table


  - **customer_count** (Integer)


  - **takeaway** (Boolean)





### pos.payment


- Hereda de:

  - pos.payment




- No agrega campos



### account.fiscal.position


- Hereda de:

  - account.fiscal.position




- No agrega campos



### res.config.settings


- Hereda de:

  - res.config.settings




- Campos:

  - **pos_floor_ids** (Many2many)


  - **pos_iface_printbill** (Boolean)


  - **pos_iface_splitbill** (Boolean)


  - **pos_set_tip_after_payment** (Boolean)


  - **pos_module_pos_restaurant_appointment** (Boolean)


  - **pos_takeaway** (Boolean)


  - **pos_takeaway_fp_id** (Many2one)





### pos.session


- Hereda de:

  - pos.session




- No agrega campos






## Vistas


### restaurant.floor

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | Restaurant Floors | `pos_restaurant.view_restaurant_floor_form` | - |
| list | Restaurant Floors | `pos_restaurant.view_restaurant_floor_tree` | - |
| search | restaurant.floor.search | `pos_restaurant.view_restaurant_floor_search` | - |
| kanban | restaurant.floor.kanban | `pos_restaurant.view_restaurant_floor_kanban` | - |



#### Filtros de búsqueda (pos_restaurant.view_restaurant_floor_search)

**Filtros:**
- **Archived** (`[('active', '=', False)]`)


### restaurant.table

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | Restaurant Table | `pos_restaurant.view_restaurant_table_form` | - |


