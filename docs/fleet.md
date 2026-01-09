# Módulo: Fleet

## Información General
- **Nombre técnico:** fleet
- **Versión:** 0.1
- **Categoría:** Human Resources/Fleet
- **Dependencias:** base, mail


## Propósito
Manage your fleet and track car costs



## Descripción

Vehicle, leasing, insurances, cost
With this module, Odoo helps you managing all your vehicles, the
contracts associated to those vehicle as well as services, costs
and many other features necessary to the management of your fleet
of vehicle(s)

Main Features
-------------
* Add vehicles to your fleet
* Manage contracts for vehicles
* Reminder when a contract reach its expiration date
* Add services, odometer values for all vehicles
* Show all costs associated to a vehicle or to a type of service
* Analysis graph for costs




## Modelos

### fleet.vehicle.tag


- Hereda de: Base



- Campos:

  - **name** (Char) → Tag Name


  - **color** (Integer) → Color





### fleet.vehicle.log.contract


- Hereda de:


  - mail.thread

  - mail.activity.mixin





- Campos:

  - **vehicle_id** (Many2one) → fleet.vehicle


  - **cost_subtype_id** (Many2one) → fleet.service.type


  - **amount** (Monetary) → Cost


  - **date** (Date)


  - **company_id** (Many2one) → res.company


  - **currency_id** (Many2one) → res.currency


  - **name** (Char)


  - **active** (Boolean)


  - **user_id** (Many2one) → res.users


  - **start_date** (Date) → Contract Start Date


  - **expiration_date** (Date) → Contract Expiration Date


  - **days_left** (Integer)


  - **expires_today** (Boolean)


  - **has_open_contract** (Boolean)


  - **insurer_id** (Many2one) → res.partner


  - **purchaser_id** (Many2one)


  - **ins_ref** (Char) → Reference


  - **state** (Selection)


  - **notes** (Html) → Terms and Conditions


  - **cost_generated** (Monetary) → Recurring Cost


  - **cost_frequency** (Selection)


  - **service_ids** (Many2many) → fleet.service.type





### mail.activity.type


- Hereda de:

  - mail.activity.type




- No agrega campos



### fleet.vehicle


- Hereda de:


  - mail.thread

  - mail.activity.mixin

  - avatar.mixin





- Campos:

  - **name** (Char)


  - **description** (Html) → Vehicle Description


  - **active** (Boolean) → Active


  - **manager_id** (Many2one) → res.users


  - **company_id** (Many2one) → res.company


  - **currency_id** (Many2one) → res.currency


  - **country_id** (Many2one) → res.country


  - **country_code** (Char)


  - **license_plate** (Char)


  - **vin_sn** (Char) → Chassis Number


  - **trailer_hook** (Boolean)


  - **driver_id** (Many2one) → res.partner


  - **future_driver_id** (Many2one) → res.partner


  - **model_id** (Many2one) → fleet.vehicle.model


  - **brand_id** (Many2one) → fleet.vehicle.model.brand


  - **log_drivers** (One2many) → fleet.vehicle.assignation.log


  - **log_services** (One2many) → fleet.vehicle.log.services


  - **log_contracts** (One2many) → fleet.vehicle.log.contract


  - **contract_count** (Integer)


  - **service_count** (Integer)


  - **odometer_count** (Integer)


  - **history_count** (Integer)


  - **next_assignation_date** (Date) → Assignment Date


  - **order_date** (Date) → Order Date


  - **acquisition_date** (Date) → Registration Date


  - **write_off_date** (Date) → Cancellation Date


  - **first_contract_date** (Date)


  - **color** (Char)


  - **state_id** (Many2one) → fleet.vehicle.state


  - **location** (Char)


  - **seats** (Integer) → Seats Number


  - **model_year** (Char) → Model Year


  - **doors** (Integer) → Doors Number


  - **tag_ids** (Many2many) → fleet.vehicle.tag


  - **odometer** (Float)


  - **odometer_unit** (Selection)


  - **transmission** (Selection)


  - **fuel_type** (Selection)


  - **power_unit** (Selection)


  - **horsepower** (Integer)


  - **horsepower_tax** (Float) → Horsepower Taxation


  - **power** (Integer) → Power


  - **co2** (Float) → CO2 Emissions


  - **co2_standard** (Char) → CO2 Standard


  - **category_id** (Many2one) → fleet.vehicle.model.category


  - **image_128** (Image)


  - **contract_renewal_due_soon** (Boolean)


  - **contract_renewal_overdue** (Boolean)


  - **contract_state** (Selection)


  - **car_value** (Float)


  - **net_car_value** (Float)


  - **residual_value** (Float)


  - **plan_to_change_car** (Boolean)


  - **plan_to_change_bike** (Boolean)


  - **vehicle_type** (Selection)


  - **frame_type** (Selection)


  - **electric_assistance** (Boolean)


  - **frame_size** (Float)


  - **service_activity** (Selection)


  - **vehicle_properties** (Properties) → Properties


  - **vehicle_range** (Integer)





### fleet.vehicle.model.category


- Hereda de: Base



- Campos:

  - **name** (Char)


  - **sequence** (Integer)





### fleet.service.type


- Hereda de: Base



- Campos:

  - **name** (Char)


  - **category** (Selection)





### fleet.vehicle.log.services


- Hereda de:


  - mail.thread

  - mail.activity.mixin





- Campos:

  - **active** (Boolean)


  - **vehicle_id** (Many2one) → fleet.vehicle


  - **manager_id** (Many2one) → res.users


  - **amount** (Monetary) → Cost


  - **description** (Char) → Description


  - **odometer_id** (Many2one) → fleet.vehicle.odometer


  - **odometer** (Float)


  - **odometer_unit** (Selection)


  - **date** (Date)


  - **company_id** (Many2one) → res.company


  - **currency_id** (Many2one) → res.currency


  - **purchaser_id** (Many2one) → res.partner


  - **inv_ref** (Char) → Vendor Reference


  - **vendor_id** (Many2one) → res.partner


  - **notes** (Text)


  - **service_type_id** (Many2one) → fleet.service.type


  - **state** (Selection)





### fleet.vehicle.model


- Hereda de:


  - mail.thread

  - mail.activity.mixin

  - avatar.mixin





- Campos:

  - **name** (Char) → Model name


  - **brand_id** (Many2one) → fleet.vehicle.model.brand


  - **category_id** (Many2one) → fleet.vehicle.model.category


  - **vendors** (Many2many) → res.partner


  - **image_128** (Image)


  - **active** (Boolean)


  - **vehicle_type** (Selection)


  - **transmission** (Selection)


  - **vehicle_count** (Integer)


  - **model_year** (Integer)


  - **color** (Char)


  - **seats** (Integer)


  - **doors** (Integer)


  - **trailer_hook** (Boolean)


  - **default_co2** (Float) → CO2 Emissions


  - **co2_standard** (Char)


  - **default_fuel_type** (Selection)


  - **power** (Integer) → Power


  - **horsepower** (Integer)


  - **horsepower_tax** (Float) → Horsepower Taxation


  - **electric_assistance** (Boolean)


  - **power_unit** (Selection)


  - **vehicle_properties_definition** (PropertiesDefinition) → Vehicle Properties


  - **vehicle_range** (Integer)





### fleet.vehicle.assignation.log


- Hereda de: Base



- Campos:

  - **vehicle_id** (Many2one) → fleet.vehicle


  - **driver_id** (Many2one) → res.partner


  - **date_start** (Date)


  - **date_end** (Date)





### fleet.vehicle.odometer


- Hereda de: Base



- Campos:

  - **name** (Char)


  - **date** (Date)


  - **value** (Float) → Odometer Value


  - **vehicle_id** (Many2one) → fleet.vehicle


  - **unit** (Selection)


  - **driver_id** (Many2one)





### fleet.vehicle.model.brand


- Hereda de: Base



- Campos:

  - **name** (Char) → Name


  - **active** (Boolean)


  - **image_128** (Image) → Logo


  - **model_count** (Integer)


  - **model_ids** (One2many) → fleet.vehicle.model





### ['res.config.settings']


- Hereda de:


  - res.config.settings





- Campos:

  - **delay_alert_contract** (Integer)





### res.partner


- Hereda de:

  - res.partner




- Campos:

  - **plan_to_change_car** (Boolean) → Plan To Change Car


  - **plan_to_change_bike** (Boolean) → Plan To Change Bike





### fleet.vehicle.state


- Hereda de: Base



- Campos:

  - **name** (Char)


  - **sequence** (Integer)








## Vistas


### fleet.vehicle.log.contract

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | fleet.vehicle.log_contract.form | `fleet.fleet_vehicle_log_contract_view_form` | - |
| list | fleet.vehicle.log.contract.list | `fleet.fleet_vehicle_log_contract_view_tree` | - |
| kanban | fleet.vehicle.log.contract.kanban | `fleet.fleet_vehicle_log_contract_view_kanban` | - |
| graph | fleet.vehicle.log.contract.graph | `fleet.fleet_vehicle_log_contract_view_graph` | - |
| search | fleet.vehicle.log.contract.search | `fleet.fleet_vehicle_log_contract_view_search` | - |
| activity | fleet.vehicle.log.contract.activity | `fleet.fleet_vehicle_log_contract_view_activity` | - |
| pivot | - | `fleet.fleet_vehicle_log_contract_view_pivot` | - |



#### Filtros de búsqueda (fleet.fleet_vehicle_log_contract_view_search)

**Filtros:**
- **In Progress** (`[('state', '=', 'open')]`)
- **Expired** (`[('state', '=', 'expired')]`)
- **Archived** (`[('active', '=', False)]`)
- **Late Activities** (`[('my_activity_date_deadline', '<', context_today().strftime('%Y-%m-%d'))]`)
- **Today Activities** (`[('my_activity_date_deadline', '=', context_today().strftime('%Y-%m-%d'))]`)
- **Future Activities** (`[('my_activity_date_deadline', '>', context_today().strftime('%Y-%m-%d'))]`)


**Agrupar por:**
- Vehicle


### fleet.vehicle.log.services

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | fleet.vehicle.log.services.form | `fleet.fleet_vehicle_log_services_view_form` | - |
| list | fleet.vehicle.log.services.list | `fleet.fleet_vehicle_log_services_view_tree` | - |
| kanban | fleet.vehicle.log.services.kanban | `fleet.fleet_vehicle_log_services_view_kanban` | - |
| graph | fleet.vehicle.log.services.graph | `fleet.fleet_vehicle_log_services_view_graph` | - |
| activity | - | `fleet.fleet_vehicle_log_services_view_activity` | - |
| pivot | - | `fleet.fleet_vehicle_log_services_view_pivot` | - |
| search | fleet.vehicle.log.services.search | `fleet.fleet_vehicle_log_services_view_search` | - |



#### Filtros de búsqueda (fleet.fleet_vehicle_log_services_view_search)

**Filtros:**
- **Archived** (`[('active', '=', False)]`)


**Agrupar por:**
- Service Type
- Fleet Manager


### fleet.vehicle.model

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | fleet.vehicle.model.form | `fleet.fleet_vehicle_model_view_form` | - |
| list | fleet.vehicle.model.list | `fleet.fleet_vehicle_model_view_tree` | - |
| kanban | fleet.vehicle.model.kanban | `fleet.fleet_vehicle_model_view_kanban` | - |
| search | fleet.vehicle.model.search | `fleet.fleet_vehicle_model_view_search` | - |



#### Botones (fleet.fleet_vehicle_model_view_form)
- **action_model_vehicle** (object)


#### Filtros de búsqueda (fleet.fleet_vehicle_model_view_search)

**Filtros:**
- **Contains Vehicle** (`[('vehicle_count', '!=', 0)]`)
- **Archived** (`[('active','=',False)]`)


**Agrupar por:**
- Manufacturers
- Category
- Vehicle Type


### fleet.vehicle.model.brand

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | fleet.vehicle.model.brand.list | `fleet.fleet_vehicle_model_brand_view_tree` | - |
| form | fleet.vehicle.model.brand.form | `fleet.fleet_vehicle_model_brand_view_form` | - |
| kanban | fleet.vehicle.model.brandkanban | `fleet.fleet_vehicle_model_brand_view_kanban` | - |
| search | fleet.vehicle.model.brand.view.search | `fleet.fleet_vehicle_model_brand_view_search` | - |



#### Botones (fleet.fleet_vehicle_model_brand_view_form)
- **action_brand_model** (object)


#### Filtros de búsqueda (fleet.fleet_vehicle_model_brand_view_search)

**Filtros:**
- **With Models** (`[('model_count', '>', 0)]`)
- **Archived** (`[('active','=',False)]`)


### fleet.vehicle.model.category

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | fleet.vehicle.model.category.view.list | `fleet.fleet_vehicle_model_category_view_tree` | - |
| form | fleet.vehicle.model.category.view.form | `fleet.fleet_vehicle_model_category_view_form` | - |



### fleet.vehicle.cost.report

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| search | fleet.vehicle.cost.view.search | `fleet.fleet_costs_report_view_search` | - |
| pivot | fleet.vehicle.cost.view.pivot | `fleet.fleet_costs_report_view_pivot` | - |
| graph | fleet.vehicle.cost.view.graph | `fleet.fleet_costs_report_view_graph` | - |
| list | fleet.vehicle.cost.report.view.list | `fleet.fleet_vechicle_costs_report_view_tree` | - |
| form | fleet.vehicle.cost.report.form | `fleet.fleet_vechicle_costs_report_view_form` | - |



#### Filtros de búsqueda (fleet.fleet_costs_report_view_search)

**Filtros:**
- **Service** (`[('cost_type', '=', 'service')]`)
- **Contract** (`[('cost_type', '=', 'contract')]`)
- **filter_date_start**


**Agrupar por:**
- Vehicle
- Driver


### fleet.vehicle

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | fleet.vehicle.form | `fleet.fleet_vehicle_view_form` | - |
| list | fleet.vehicle.list | `fleet.fleet_vehicle_view_tree` | - |
| search | fleet.vehicle.search | `fleet.fleet_vehicle_view_search` | - |
| kanban | fleet.vehicle.kanban | `fleet.fleet_vehicle_view_kanban` | - |
| activity | fleet.vehicle.activity | `fleet.fleet_vehicle_view_activity` | - |
| pivot | - | `fleet.fleet_vehicle_view_pivot` | - |



#### Botones (fleet.fleet_vehicle_view_form)
- **Apply New Driver** (object)
- **open_assignation_logs** (object)
- **return_action_to_open** (object)
- **return_action_to_open** (object)
- **return_action_to_open** (object)
- **return_action_to_open** (object)
- **return_action_to_open** (object)


#### Filtros de búsqueda (fleet.fleet_vehicle_view_search)

**Filtros:**
- **Available** (`['&', ('future_driver_id', '=', False), '|', ('driver_id', '=', False), '|', '&', ('plan_to_change_car', '=', True), ('vehicle_type', '=', 'car'), '&', ('plan_to_change_bike', '=', True), ('vehicle_type', '=', 'bike')]`)
- **Bikes** (`[('vehicle_type', '=', 'bike')]`)
- **Cars** (`[('vehicle_type', '=', 'car')]`)
- **Trailer Hook** (`[('trailer_hook', '=', True)]`)
- **Planned for Change** (`['|', '&', ('vehicle_type', '=', 'bike'), ('plan_to_change_bike', '=', True), '&', ('vehicle_type', '=', 'car'), ('plan_to_change_car', '=', True)]`)
- **Need Action** (`['|', ('contract_renewal_due_soon', '=', True), ('contract_renewal_overdue', '=', True)]`)
- **Archived** (`[('active', '=', False)]`)
- **Late Activities** (`[('my_activity_date_deadline', '<', context_today().strftime('%Y-%m-%d'))]`)
- **Today Activities** (`[('my_activity_date_deadline', '=', context_today().strftime('%Y-%m-%d'))]`)
- **Future Activities** (`[('my_activity_date_deadline', '>', context_today().strftime('%Y-%m-%d'))]`)


**Agrupar por:**
- Status
- Model
- Brand
- Fuel Type


### fleet.vehicle.odometer

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | fleet.vehicle.odometer.form | `fleet.fleet_vehicle_odometer_view_form` | - |
| list | fleet.vehicle.odometer.list | `fleet.fleet_vehicle_odometer_view_tree` | - |
| kanban | fleet.vehicle.odometer.kanban | `fleet.fleet_vehicle_odometer_view_kanban` | - |
| search | fleet.vehicle.odometer.search | `fleet.fleet_vehicle_odometer_view_search` | - |
| graph | fleet.vehicle.odometer.graph | `fleet.fleet_vehicle_odometer_view_graph` | - |



#### Filtros de búsqueda (fleet.fleet_vehicle_odometer_view_search)


**Agrupar por:**
- Vehicle


### fleet.service.type

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | fleet.service.type.list | `fleet.fleet_vehicle_service_types_view_tree` | - |
| search | - | `fleet.fleet_vehicle_service_types_view_search` | - |



#### Filtros de búsqueda (fleet.fleet_vehicle_service_types_view_search)


**Agrupar por:**
- groupby_category


### fleet.vehicle.state

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | fleet.vehicle.state.list | `fleet.fleet_vehicle_state_view_tree` | - |
| form | fleet.vehicle.state.form | `fleet.fleet_vehicle_state_view_form` | - |



### fleet.vehicle.tag

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | fleet.vehicle.tag.form | `fleet.fleet_vehicle_tag_view_view_form` | - |
| list | fleet.vehicle.tag.list | `fleet.fleet_vehicle_tag_view_view_tree` | - |



### fleet.vehicle.assignation.log

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | fleet.vehicle.assignation.log.view.list | `fleet.fleet_vehicle_assignation_log_view_list` | - |



### fleet.vehicle.send.mail

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | - | `fleet.fleet_vehicle_send_mail_view_form` | - |



#### Botones (fleet.fleet_vehicle_send_mail_view_form)
- **Send** (object)
- **Save as new template** (object)

