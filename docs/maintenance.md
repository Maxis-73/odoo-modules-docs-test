# Módulo: Maintenance

## Información General
- **Nombre técnico:** maintenance
- **Versión:** 1.0
- **Categoría:** Manufacturing/Maintenance
- **Dependencias:** mail


## Propósito
Track equipment and manage maintenance requests



## Descripción

Track equipment and maintenance requests



## Modelos

### maintenance.stage


- Hereda de: Base



- Campos:

  - **name** (Char) → Name


  - **sequence** (Integer) → Sequence


  - **fold** (Boolean) → Folded in Maintenance Pipe


  - **done** (Boolean) → Request Done





### maintenance.equipment.category


- Hereda de:


  - mail.alias.mixin

  - mail.thread





- Campos:

  - **name** (Char) → Category Name


  - **company_id** (Many2one) → res.company


  - **technician_user_id** (Many2one) → res.users


  - **color** (Integer) → Color Index


  - **note** (Html) → Comments


  - **equipment_ids** (One2many) → maintenance.equipment


  - **equipment_count** (Integer)


  - **maintenance_ids** (One2many) → maintenance.request


  - **maintenance_count** (Integer)


  - **maintenance_open_count** (Integer)


  - **alias_id** (Many2one)


  - **fold** (Boolean)


  - **equipment_properties_definition** (PropertiesDefinition) → Equipment Properties





### maintenance.mixin


- Hereda de: Base



- Campos:

  - **company_id** (Many2one) → res.company


  - **effective_date** (Date) → Effective Date


  - **maintenance_team_id** (Many2one) → maintenance.team


  - **technician_user_id** (Many2one) → res.users


  - **maintenance_ids** (One2many) → maintenance.request


  - **maintenance_count** (Integer)


  - **maintenance_open_count** (Integer)


  - **expected_mtbf** (Integer)


  - **mtbf** (Integer)


  - **mttr** (Integer)


  - **estimated_next_failure** (Date)


  - **latest_failure_date** (Date)





### maintenance.equipment


- Hereda de:


  - mail.thread

  - mail.activity.mixin

  - maintenance.mixin





- Campos:

  - **name** (Char) → Equipment Name


  - **active** (Boolean)


  - **owner_user_id** (Many2one) → res.users


  - **category_id** (Many2one) → maintenance.equipment.category


  - **partner_id** (Many2one) → res.partner


  - **partner_ref** (Char) → Vendor Reference


  - **location** (Char) → Location


  - **model** (Char) → Model


  - **serial_no** (Char) → Serial Number


  - **assign_date** (Date) → Assigned Date


  - **cost** (Float) → Cost


  - **note** (Html) → Note


  - **warranty_date** (Date) → Warranty Expiration Date


  - **color** (Integer) → Color Index


  - **scrap_date** (Date) → Scrap Date


  - **maintenance_ids** (One2many) → maintenance.request


  - **equipment_properties** (Properties) → Properties


  - **match_serial** (Boolean)





### maintenance.request


- Hereda de:


  - mail.thread.cc

  - mail.activity.mixin





- Campos:

  - **name** (Char) → Subjects


  - **company_id** (Many2one) → res.company


  - **description** (Html) → Description


  - **request_date** (Date) → Request Date


  - **owner_user_id** (Many2one) → res.users


  - **category_id** (Many2one) → maintenance.equipment.category


  - **equipment_id** (Many2one) → maintenance.equipment


  - **user_id** (Many2one) → res.users


  - **stage_id** (Many2one) → maintenance.stage


  - **priority** (Selection)


  - **color** (Integer) → Color Index


  - **close_date** (Date) → Close Date


  - **kanban_state** (Selection)


  - **archive** (Boolean)


  - **maintenance_type** (Selection)


  - **schedule_date** (Datetime) → Scheduled Date


  - **maintenance_team_id** (Many2one) → maintenance.team


  - **duration** (Float)


  - **done** (Boolean)


  - **instruction_type** (Selection)


  - **instruction_pdf** (Binary) → PDF


  - **instruction_google_slide** (Char) → Google Slide


  - **instruction_text** (Html) → Text


  - **recurring_maintenance** (Boolean)


  - **repeat_interval** (Integer)


  - **repeat_unit** (Selection)


  - **repeat_type** (Selection)


  - **repeat_until** (Date)





### maintenance.team


- Hereda de: Base



- Campos:

  - **name** (Char) → Team Name


  - **active** (Boolean)


  - **company_id** (Many2one) → res.company


  - **member_ids** (Many2many) → res.users


  - **color** (Integer) → Color Index


  - **request_ids** (One2many) → maintenance.request


  - **equipment_ids** (One2many) → maintenance.equipment


  - **todo_request_ids** (One2many) → maintenance.request


  - **todo_request_count** (Integer)


  - **todo_request_count_date** (Integer)


  - **todo_request_count_high_priority** (Integer)


  - **todo_request_count_block** (Integer)


  - **todo_request_count_unscheduled** (Integer)





### res.config.settings


- Hereda de:

  - res.config.settings




- Campos:

  - **module_maintenance_worksheet** (Boolean)








## Vistas


### maintenance.request

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| search | equipment.request.search | `maintenance.hr_equipment_request_view_search` | - |
| activity | maintenance.request.view.activity | `maintenance.maintenance_request_view_activity` | - |
| form | equipment.request.form | `maintenance.hr_equipment_request_view_form` | - |
| kanban | equipment.request.kanban | `maintenance.hr_equipment_request_view_kanban` | - |
| list | equipment.request.list | `maintenance.hr_equipment_request_view_tree` | - |
| graph | equipment.request.graph | `maintenance.hr_equipment_request_view_graph` | - |
| pivot | equipment.request.pivot | `maintenance.hr_equipment_request_view_pivot` | - |
| calendar | equipment.request.calendar | `maintenance.hr_equipment_view_calendar` | - |



#### Filtros de búsqueda (maintenance.hr_equipment_request_view_search)

**Filtros:**
- **My Maintenances** (`[('user_id', '=', uid)]`)
- **To Do** (`[('stage_id.done', '=', False)]`)
- **Done** (`[('stage_id.done', '=', True)]`)
- **Blocked** (`[('stage_id.done', '=', False), ('kanban_state', '=', 'blocked')]`)
- **Ready** (`[('stage_id.done', '=', False), ('kanban_state', '=', 'done')]`)
- **High-priority** (`[('stage_id.done', '=', False), ('priority', '=', '3')]`)
- **Unscheduled** (`[('stage_id.done', '=', False), ('schedule_date', '=', False)]`)
- **filter_request_date**
- **filter_schedule_date**
- **filter_close_date**
- **Unread Messages** (`[('message_needaction', '=', True)]`)
- **Late Activities** (`[('my_activity_date_deadline', '<', context_today().strftime('%Y-%m-%d'))]`)
- **Today Activities** (`[('my_activity_date_deadline', '=', context_today().strftime('%Y-%m-%d'))]`)
- **Future Activities** (`[('my_activity_date_deadline', '>', context_today().strftime('%Y-%m-%d'))]`)
- **Active** (`[('archive', '=', False)]`)
- **Cancelled** (`[('archive', '=', True)]`)


**Agrupar por:**
- Assigned to
- Category
- Stage
- Created By


#### Botones (maintenance.hr_equipment_request_view_form)
- **Cancel** (object)
- **Reopen Request** (object)


### maintenance.equipment

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | equipment.form | `maintenance.hr_equipment_view_form` | - |
| kanban | equipment.kanban | `maintenance.hr_equipment_view_kanban` | - |
| list | equipment.list | `maintenance.hr_equipment_view_tree` | - |
| search | equipment.search | `maintenance.hr_equipment_view_search` | - |



#### Botones (maintenance.hr_equipment_view_form)
- **action_open_matched_serial** (object)
- **%(hr_equipment_request_action_from_equipment)d** (action)


#### Filtros de búsqueda (maintenance.hr_equipment_view_search)

**Filtros:**
- **My Equipment** (`[('owner_user_id', '=', uid)]`)
- **Assigned** (`[('owner_user_id', '!=', False)]`)
- **Unassigned** (`[('owner_user_id', '=', False)]`)
- **Under Maintenance** (`[('maintenance_open_count', '>', 0)]`)
- **Unread Messages** (`[('message_needaction','=',True)]`)
- **Late Activities** (`[('my_activity_date_deadline', '<', context_today().strftime('%Y-%m-%d'))]`)
- **Today Activities** (`[('my_activity_date_deadline', '=', context_today().strftime('%Y-%m-%d'))]`)
- **Future Activities** (`[('my_activity_date_deadline', '>', context_today().strftime('%Y-%m-%d'))]`)
- **Archived** (`[('active','=',False)]`)


**Agrupar por:**
- Technician
- Category
- Owner
- Vendor


### maintenance.equipment.category

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | equipment.category.form | `maintenance.hr_equipment_category_view_form` | - |
| list | equipment.category.list | `maintenance.hr_equipment_category_view_tree` | - |
| search | equipment.category.search | `maintenance.hr_equipment_category_view_search` | - |
| kanban | maintenance.equipment.category.kanban | `maintenance.view_maintenance_equipment_category_kanban` | - |



#### Botones (maintenance.hr_equipment_category_view_form)
- **%(hr_equipment_action_from_category_form)d** (action)
- **%(hr_equipment_request_action_link)d** (action)


#### Filtros de búsqueda (maintenance.hr_equipment_category_view_search)


**Agrupar por:**
- Responsible


### maintenance.stage

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| search | equipment.stage.search | `maintenance.hr_equipment_stage_view_search` | - |
| list | equipment.stage.list | `maintenance.hr_equipment_stage_view_tree` | - |
| kanban | equipment.stage.kanban | `maintenance.hr_equipment_stage_view_kanban` | - |



### maintenance.team

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | maintenance.team.form | `maintenance.maintenance_team_view_form` | - |
| list | maintenance.team.list | `maintenance.maintenance_team_view_tree` | - |
| kanban | maintenance.team.kanban | `maintenance.maintenance_team_view_kanban` | - |
| kanban | maintenance.team.kanban | `maintenance.maintenance_team_kanban` | - |
| search | maintenance.team.search | `maintenance.maintenance_team_view_search` | - |



#### Filtros de búsqueda (maintenance.maintenance_team_view_search)

**Filtros:**
- **Archived** (`[('active', '=', False)]`)

