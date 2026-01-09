# Módulo: Resource

## Información General
- **Nombre técnico:** resource
- **Versión:** 1.1
- **Categoría:** Hidden
- **Dependencias:** base, web




## Descripción

Module for resource management.
===============================

A resource represent something that can be scheduled (a developer on a task or a
work center on manufacturing orders). This module manages a resource calendar
associated to every resource. It also manages the leaves of every resource.
    



## Modelos

### resource.calendar.attendance


- Hereda de: Base



#### Campos
- **name** (Char)
- **dayofweek** (Selection)
- **date_from** (Date)
- **date_to** (Date)
- **hour_from** (Float)
- **hour_to** (Float)
- **duration_hours** (Float)
- **duration_days** (Float)
- **calendar_id** (Many2one) → resource.calendar
- **day_period** (Selection)
- **resource_id** (Many2one) → resource.resource
- **week_type** (Selection)
- **two_weeks_calendar** (Boolean) → Calendar in 2 weeks mode
- **display_type** (Selection)
- **sequence** (Integer)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | resource.calendar.attendance.list | `resource.view_resource_calendar_attendance_tree` | - |
| form | resource.calendar.attendance.form | `resource.view_resource_calendar_attendance_form` | - |




### resource.calendar


- Hereda de: Base



#### Campos
- **name** (Char)
- **active** (Boolean) → Active
- **company_id** (Many2one) → res.company
- **attendance_ids** (One2many) → resource.calendar.attendance
- **leave_ids** (One2many) → resource.calendar.leaves
- **global_leave_ids** (One2many) → resource.calendar.leaves
- **hours_per_day** (Float) → Average Hour per Day
- **tz** (Selection)
- **tz_offset** (Char)
- **two_weeks_calendar** (Boolean)
- **two_weeks_explanation** (Char) → Explanation
- **flexible_hours** (Boolean)
- **full_time_required_hours** (Float)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| search | resource.calendar.search | `resource.view_resource_calendar_search` | - |
| form | resource.calendar.form | `resource.resource_calendar_form` | - |
| list | resource.calendar.list | `resource.view_resource_calendar_tree` | - |



**Filtros de búsqueda (resource.view_resource_calendar_search):**

- **Archived** (`[('active', '=', False)]`)


**Botones (resource.resource_calendar_form):**
- **Switch to 2 weeks calendar** (object)
- **Switch to 1 week calendar** (object)
- **%(resource_calendar_leaves_action_from_calendar)d** (action) - Grupos: `base.group_no_one`
- **%(resource_resource_action_from_calendar)d** (action) - Grupos: `base.group_user`



### res.users


- Hereda de:

  - res.users




#### Campos
- **resource_ids** (One2many) → resource.resource
- **resource_calendar_id** (Many2one) → resource.calendar





### resource.calendar.leaves


- Hereda de: Base



#### Campos
- **name** (Char) → Reason
- **company_id** (Many2one) → res.company
- **calendar_id** (Many2one) → resource.calendar
- **date_from** (Datetime) → Start Date
- **date_to** (Datetime) → End Date
- **resource_id** (Many2one) → resource.resource
- **time_type** (Selection)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| search | resource.calendar.leaves.search | `resource.view_resource_calendar_leaves_search` | - |
| calendar | resource.calendar.leaves.calendar | `resource.view_resource_calendar` | - |
| form | resource.calendar.leaves.form | `resource.resource_calendar_leave_form` | - |
| list | resource.calendar.leaves.list | `resource.resource_calendar_leave_tree` | - |



**Filtros de búsqueda (resource.view_resource_calendar_leaves_search):**

- **Period**


*Agrupar por:*
- Resource
- Company
- Date



### res.company


- Hereda de:

  - res.company




#### Campos
- **resource_calendar_ids** (One2many) → resource.calendar
- **resource_calendar_id** (Many2one) → resource.calendar





### resource.mixin


- Hereda de: Base



#### Campos
- **resource_id** (Many2one) → resource.resource
- **company_id** (Many2one) → res.company
- **resource_calendar_id** (Many2one) → resource.calendar
- **tz** (Selection)





### resource.resource


- Hereda de: Base



#### Campos
- **name** (Char)
- **active** (Boolean) → Active
- **company_id** (Many2one) → res.company
- **resource_type** (Selection)
- **user_id** (Many2one) → res.users
- **avatar_128** (Image)
- **share** (Boolean)
- **email** (Char)
- **phone** (Char)
- **time_efficiency** (Float) → Efficiency Factor
- **calendar_id** (Many2one) → resource.calendar
- **tz** (Selection)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| search | resource.resource.search | `resource.view_resource_resource_search` | - |
| form | resource.resource.form | `resource.resource_resource_form` | - |
| list | resource.resource.list | `resource.resource_resource_tree` | - |



**Filtros de búsqueda (resource.view_resource_resource_search):**

- **Human** (`[('resource_type','=', 'user')]`)
- **Material** (`[('resource_type','=', 'material')]`)
- **Archived** (`[('active','=',False)]`)


*Agrupar por:*
- User
- Type
- Company
- Working Time








