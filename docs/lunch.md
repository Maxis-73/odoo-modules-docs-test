# Módulo: Lunch

## Información General
- **Nombre técnico:** lunch
- **Versión:** 1.0
- **Categoría:** Human Resources/Lunch
- **Dependencias:** mail


## Propósito
Handle lunch orders of your employees



## Descripción

The base module to manage lunch.
================================

Many companies order sandwiches, pizzas and other, from usual vendors, for their employees to offer them more facilities.

However lunches management within the company requires proper administration especially when the number of employees or vendors is important.

The “Lunch Order” module has been developed to make this management easier but also to offer employees more tools and usability.

In addition to a full meal and vendor management, this module offers the possibility to display warning and provides quick order selection based on employee’s preferences.

If you want to save your employees' time and avoid them to always have coins in their pockets, this module is essential.
    



## Modelos

### lunch.alert


- Hereda de: Base



#### Campos
- **name** (Char) → Alert Name
- **message** (Html) → Message
- **mode** (Selection)
- **recipients** (Selection)
- **notification_time** (Float)
- **notification_moment** (Selection)
- **tz** (Selection)
- **cron_id** (Many2one) → ir.cron
- **until** (Date) → Show Until
- **mon** (Boolean)
- **tue** (Boolean)
- **wed** (Boolean)
- **thu** (Boolean)
- **fri** (Boolean)
- **sat** (Boolean)
- **sun** (Boolean)
- **available_today** (Boolean) → Is Displayed Today
- **active** (Boolean) → Active
- **location_ids** (Many2many) → lunch.location





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| search | lunch.alert.search | `lunch.lunch_alert_view_search` | - |
| list | lunch.alert.list | `lunch.lunch_alert_view_tree` | - |
| form | lunch.alert.form | `lunch.lunch_alert_view_form` | - |
| kanban | lunch.alert.kanban | `lunch.lunch_alert_view_kanban` | - |



**Filtros de búsqueda (lunch.lunch_alert_view_search):**

- **Currently inactive** (`[('available_today', '=', False)]`)
- **Active** (`[('active', '=', True)]`)
- **Archived** (`[('active', '=', False)]`)



### lunch.topping


- Hereda de: Base



#### Campos
- **name** (Char) → Name
- **company_id** (Many2one) → res.company
- **currency_id** (Many2one) → res.currency
- **price** (Monetary) → Price
- **supplier_id** (Many2one) → lunch.supplier
- **topping_category** (Integer) → Topping Category





### lunch.supplier


- Hereda de:


  - mail.thread

  - mail.activity.mixin





#### Campos
- **partner_id** (Many2one) → res.partner
- **name** (Char) → Name
- **email** (Char)
- **email_formatted** (Char)
- **phone** (Char)
- **street** (Char)
- **street2** (Char)
- **zip_code** (Char)
- **city** (Char)
- **state_id** (Many2one) → res.country.state
- **country_id** (Many2one) → res.country
- **company_id** (Many2one) → res.company
- **responsible_id** (Many2one) → res.users
- **send_by** (Selection)
- **automatic_email_time** (Float) → Order Time
- **cron_id** (Many2one) → ir.cron
- **mon** (Boolean)
- **tue** (Boolean)
- **wed** (Boolean)
- **thu** (Boolean)
- **fri** (Boolean)
- **sat** (Boolean)
- **sun** (Boolean)
- **recurrency_end_date** (Date) → Until
- **available_location_ids** (Many2many) → lunch.location
- **available_today** (Boolean) → This is True when if the supplier is available today
- **order_deadline_passed** (Boolean)
- **tz** (Selection)
- **active** (Boolean)
- **moment** (Selection)
- **delivery** (Selection)
- **topping_label_1** (Char) → Extra 1 Label
- **topping_label_2** (Char) → Extra 2 Label
- **topping_label_3** (Char) → Extra 3 Label
- **topping_ids_1** (One2many) → lunch.topping
- **topping_ids_2** (One2many) → lunch.topping
- **topping_ids_3** (One2many) → lunch.topping
- **topping_quantity_1** (Selection)
- **topping_quantity_2** (Selection)
- **topping_quantity_3** (Selection)
- **show_order_button** (Boolean)
- **show_confirm_button** (Boolean)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | lunch.supplier.view.list | `lunch.lunch_supplier_view_tree` | - |
| form | lunch.supplier.view.form | `lunch.lunch_supplier_view_form` | - |
| kanban | lunch.supplier.view.kanban | `lunch.lunch_supplier_view_kanban` | - |
| search | lunch.supplier.view.search | `lunch.lunch_supplier_view_search` | - |



**Filtros de búsqueda (lunch.lunch_supplier_view_search):**

- **Archived** (`[('active', '=', False)]`)



### lunch.location


- Hereda de: Base



#### Campos
- **name** (Char) → Location Name
- **address** (Text) → Address
- **company_id** (Many2one) → res.company





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| search | lunch.location.view.search | `lunch.lunch_location_view_search` | - |
| form | lunch.location.view.form | `lunch.lunch_location_form_view` | - |
| list | lunch.location.view.form | `lunch.lunch_location_tree_view` | - |
| kanban | lunch.location.view.kanban | `lunch.lunch_location_kanban_view` | - |




### res.users


- Hereda de:

  - res.users




#### Campos
- **last_lunch_location_id** (Many2one) → lunch.location
- **favorite_lunch_product_ids** (Many2many) → lunch.product





### lunch.product.category


- Hereda de:

  - image.mixin




#### Campos
- **name** (Char) → Product Category
- **company_id** (Many2one) → res.company
- **currency_id** (Many2one) → res.currency
- **product_count** (Integer)
- **active** (Boolean)
- **image_1920** (Image)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | Product category List | `lunch.lunch_product_category_view_tree` | - |
| form | Product category Form | `lunch.lunch_product_category_view_form` | - |
| kanban | Product category Kanban | `lunch.lunch_product_category_view_kanban` | - |
| search | lunch.product.category.search | `lunch.lunch_product_category_view_search` | - |



**Botones (lunch.lunch_product_category_view_form):**
- **%(lunch.lunch_product_action_statbutton)d** (action)


**Filtros de búsqueda (lunch.lunch_product_category_view_search):**

- **Archived** (`[('active', '=', False)]`)



### lunch.cashmove


- Hereda de: Base



#### Campos
- **currency_id** (Many2one) → res.currency
- **user_id** (Many2one) → res.users
- **date** (Date) → Date
- **amount** (Float) → Amount
- **description** (Text) → Description





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| search | lunch.cashmove.search | `lunch.lunch_cashmove_view_search` | - |
| list | lunch.cashmove.list | `lunch.lunch_cashmove_view_tree` | - |
| form | lunch.cashmove.form | `lunch.lunch_cashmove_view_form` | - |
| kanban | lunch.cashmove.kanban | `lunch.view_lunch_cashmove_kanban` | - |



**Filtros de búsqueda (lunch.lunch_cashmove_view_search):**


*Agrupar por:*
- My Account grouped
- By User



### res.config.settings


- Hereda de:

  - res.config.settings




#### Campos
- **currency_id** (Many2one) → res.currency
- **company_lunch_minimum_threshold** (Float)
- **company_lunch_notify_message** (Html)





### res.company


- Hereda de:

  - res.company




#### Campos
- **lunch_minimum_threshold** (Float)
- **lunch_notify_message** (Html)





### lunch.order


- Hereda de: Base



#### Campos
- **name** (Char)
- **topping_ids_1** (Many2many) → lunch.topping
- **topping_ids_2** (Many2many) → lunch.topping
- **topping_ids_3** (Many2many) → lunch.topping
- **product_id** (Many2one) → lunch.product
- **category_id** (Many2one)
- **date** (Date) → Order Date
- **supplier_id** (Many2one)
- **available_today** (Boolean)
- **available_on_date** (Boolean)
- **order_deadline_passed** (Boolean)
- **user_id** (Many2one) → res.users
- **lunch_location_id** (Many2one) → lunch.location
- **note** (Text) → Notes
- **price** (Monetary) → Total Price
- **active** (Boolean) → Active
- **state** (Selection)
- **notified** (Boolean)
- **company_id** (Many2one) → res.company
- **currency_id** (Many2one)
- **quantity** (Float) → Quantity
- **display_toppings** (Text) → Extras
- **product_description** (Html) → Description
- **topping_label_1** (Char)
- **topping_label_2** (Char)
- **topping_label_3** (Char)
- **topping_quantity_1** (Selection)
- **topping_quantity_2** (Selection)
- **topping_quantity_3** (Selection)
- **image_1920** (Image)
- **image_128** (Image)
- **available_toppings_1** (Boolean)
- **available_toppings_2** (Boolean)
- **available_toppings_3** (Boolean)
- **display_reorder_button** (Boolean)
- **display_add_button** (Boolean)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| search | lunch.order.search | `lunch.lunch_order_view_search` | - |
| list | lunch.order.list | `lunch.lunch_order_view_tree` | - |
| kanban | lunch.order.kanban | `lunch.lunch_order_view_kanban` | - |
| pivot | lunch.order.pivot | `lunch.lunch_order_view_pivot` | - |
| graph | lunch.order.graph | `lunch.lunch_order_view_graph` | - |
| form | lunch.order.view.form | `lunch.lunch_order_view_form` | - |



**Filtros de búsqueda (lunch.lunch_order_view_search):**

- **My Orders** (`[('user_id', '=', uid)]`)
- **Not Received** (`[('state', '!=', ('confirmed'))]`)
- **Received** (`[('state', '=', 'confirmed')]`)
- **Cancelled** (`[('state', '=', 'cancelled')]`)
- **Today** (`[('date', '=', context_today().strftime('%Y-%m-%d'))]`)
- **Archived** (`[('active', '=', False)]`)


*Agrupar por:*
- User
- Vendor
- Order Date


**Botones (lunch.lunch_order_view_form):**
- **Add To Cart** (object)



### lunch.product


- Hereda de:

  - image.mixin




#### Campos
- **name** (Char) → Product Name
- **category_id** (Many2one) → lunch.product.category
- **description** (Html) → Description
- **price** (Float) → Price
- **supplier_id** (Many2one) → lunch.supplier
- **active** (Boolean)
- **company_id** (Many2one) → res.company
- **currency_id** (Many2one) → res.currency
- **new_until** (Date) → New Until
- **is_new** (Boolean)
- **favorite_user_ids** (Many2many) → res.users
- **is_favorite** (Boolean)
- **last_order_date** (Date)
- **product_image** (Image)
- **is_available_at** (Many2one) → lunch.location





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| search | lunch.product.search | `lunch.lunch_product_view_search` | - |
| list | lunch.product.list | `lunch.lunch_product_view_tree` | - |
| form | lunch.product.form | `lunch.lunch_product_view_form` | - |
| kanban | lunch.product.kanban | `lunch.view_lunch_product_kanban_order` | - |
| kanban | lunch.product.kanban | `lunch.view_lunch_product_kanban` | - |



**Filtros de búsqueda (lunch.lunch_product_view_search):**

- **Available Today** (`[('supplier_id.available_today', '=', True)]`)
- **Monday** (`[('supplier_id.mon', '=', True)]`)
- **Tuesday** (`[('supplier_id.tue', '=', True)]`)
- **Wednesday** (`[('supplier_id.wed', '=', True)]`)
- **Thursday** (`[('supplier_id.thu', '=', True)]`)
- **Friday** (`[('supplier_id.fri', '=', True)]`)
- **Saturday** (`[('supplier_id.sat', '=', True)]`)
- **Sunday** (`[('supplier_id.sun', '=', True)]`)
- **Archived** (`[('active', '=', False)]`)


*Agrupar por:*
- Vendor
- Category








## Vistas Adicionales


### lunch.cashmove.report

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| search | lunch.cashmove.report.search | `lunch.lunch_cashmove_report_view_search` | - |
| search | lunch.cashmove.report.search | `lunch.lunch_cashmove_report_view_search_2` | - |
| list | lunch.cashmove.report.list | `lunch.lunch_cashmove_report_view_tree` | - |
| list | lunch.cashmove.report.list | `lunch.lunch_cashmove_report_view_tree_2` | - |
| form | lunch.cashmove.report.form | `lunch.lunch_cashmove_report_view_form` | - |
| kanban | lunch.cashmove.report.kanban | `lunch.view_lunch_cashmove_report_kanban` | - |



**Filtros de búsqueda (lunch.lunch_cashmove_report_view_search):**

- **Payment** (`[('amount', '>', 0)]`)


*Agrupar por:*
- My Account grouped
- By User


**Filtros de búsqueda (lunch.lunch_cashmove_report_view_search_2):**


*Agrupar por:*
- By Employee



