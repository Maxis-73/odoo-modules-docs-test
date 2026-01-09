# Módulo: Attendances

## Información General
- **Nombre técnico:** hr_attendance
- **Versión:** 2.0
- **Categoría:** Human Resources/Attendances
- **Dependencias:** hr, barcodes


## Propósito
Track employee attendance



## Descripción

This module aims to manage employee's attendances.

Keeps account of the attendances of the employees on the basis of the
actions(Check in/Check out) performed by them.
       



## Modelos

### hr.attendance


- Hereda de:

  - mail.thread




- Campos:

  - **employee_id** (Many2one) → hr.employee


  - **department_id** (Many2one) → hr.department


  - **manager_id** (Many2one) → hr.employee


  - **check_in** (Datetime)


  - **check_out** (Datetime)


  - **worked_hours** (Float)


  - **color** (Integer)


  - **overtime_hours** (Float)


  - **overtime_status** (Selection)


  - **validated_overtime_hours** (Float)


  - **no_validated_overtime_hours** (Boolean)


  - **in_latitude** (Float)


  - **in_longitude** (Float)


  - **in_country_name** (Char)


  - **in_city** (Char)


  - **in_ip_address** (Char)


  - **in_browser** (Char)


  - **in_mode** (Selection)


  - **out_latitude** (Float)


  - **out_longitude** (Float)


  - **out_country_name** (Char)


  - **out_city** (Char)


  - **out_ip_address** (Char)


  - **out_browser** (Char)


  - **out_mode** (Selection)


  - **expected_hours** (Float)





### hr.employee


- Hereda de:

  - hr.employee




- Campos:

  - **attendance_manager_id** (Many2one) → res.users


  - **attendance_ids** (One2many) → hr.attendance


  - **last_attendance_id** (Many2one) → hr.attendance


  - **last_check_in** (Datetime)


  - **last_check_out** (Datetime)


  - **attendance_state** (Selection)


  - **hours_last_month** (Float)


  - **hours_today** (Float)


  - **hours_previously_today** (Float)


  - **last_attendance_worked_hours** (Float)


  - **hours_last_month_display** (Char)


  - **overtime_ids** (One2many) → hr.attendance.overtime


  - **total_overtime** (Float)





### ['res.users']


- Hereda de:


  - res.users





- Campos:

  - **hours_last_month** (Float)


  - **hours_last_month_display** (Char)


  - **attendance_state** (Selection)


  - **last_check_in** (Datetime)


  - **last_check_out** (Datetime)


  - **total_overtime** (Float)


  - **attendance_manager_id** (Many2one)


  - **display_extra_hours** (Boolean)





### hr.attendance.overtime


- Hereda de: Base



- Campos:

  - **employee_id** (Many2one) → hr.employee


  - **company_id** (Many2one)


  - **date** (Date)


  - **duration** (Float)


  - **duration_real** (Float)


  - **adjustment** (Boolean)





### res.config.settings


- Hereda de:

  - res.config.settings




- Campos:

  - **overtime_company_threshold** (Integer)


  - **overtime_employee_threshold** (Integer)


  - **hr_attendance_display_overtime** (Boolean)


  - **attendance_kiosk_mode** (Selection)


  - **attendance_barcode_source** (Selection)


  - **attendance_kiosk_delay** (Integer)


  - **attendance_kiosk_url** (Char)


  - **attendance_kiosk_use_pin** (Boolean)


  - **attendance_from_systray** (Boolean)


  - **attendance_overtime_validation** (Selection)


  - **auto_check_out** (Boolean)


  - **auto_check_out_tolerance** (Float)


  - **absence_management** (Boolean)





### res.company


- Hereda de:

  - res.company




- Campos:

  - **overtime_company_threshold** (Integer)


  - **overtime_employee_threshold** (Integer)


  - **hr_attendance_display_overtime** (Boolean)


  - **attendance_kiosk_mode** (Selection)


  - **attendance_barcode_source** (Selection)


  - **attendance_kiosk_delay** (Integer)


  - **attendance_kiosk_key** (Char)


  - **attendance_kiosk_url** (Char)


  - **attendance_kiosk_use_pin** (Boolean)


  - **attendance_from_systray** (Boolean)


  - **attendance_overtime_validation** (Selection)


  - **auto_check_out** (Boolean)


  - **auto_check_out_tolerance** (Float)


  - **absence_management** (Boolean)





### hr.employee.base


- Hereda de:

  - hr.employee.base




- No agrega campos



### hr.employee.public


- Hereda de:

  - hr.employee.public




- Campos:

  - **attendance_state** (Selection)


  - **hours_today** (Float)


  - **last_attendance_id** (Many2one)


  - **total_overtime** (Float)


  - **attendance_manager_id** (Many2one)


  - **last_check_in** (Datetime)


  - **last_check_out** (Datetime)








## Vistas


### hr.attendance

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | hr.attendance.list | `hr_attendance.view_attendance_tree` | - |
| kanban | hr.attendance.kanban | `hr_attendance.view_hr_attendance_kanban` | - |
| form | hr.attendance.form | `hr_attendance.hr_attendance_view_form` | - |
| graph | hr.attendance.graph | `hr_attendance.hr_attendance_view_graph` | - |
| pivot | hr.attendance.pivot | `hr_attendance.hr_attendance_view_pivot` | - |
| search | hr_attendance_view_filter | `hr_attendance.hr_attendance_view_filter` | - |
| search | hr_attendance_management_view_filter | `hr_attendance.hr_attendance_management_view_filter` | - |
| list | hr.attendance.list | `hr_attendance.view_attendance_tree_management` | - |
| list | hr.attendance.list | `hr_attendance.hr_attendance_employee_simple_tree_view` | - |
| list | hr.attendance.list | `hr_attendance.hr_attendance_validated_hours_employee_simple_tree_view` | - |



#### Botones (hr_attendance.hr_attendance_view_form)
- **Approve** (object)
- **Refuse** (object)
- **View on Maps** (object)
- **View on Maps** (object)


#### Filtros de búsqueda (hr_attendance.hr_attendance_view_filter)

**Filtros:**
- **My Attendances** (`[('employee_id.user_id', '=', uid)]`)
- **My Team** (`[('employee_id.parent_id.user_id', '=', uid)]`)
- **At Work** (`[('check_out', '=', False)]`)
- **Errors** (`['|', ('worked_hours', '>=', 16), '&', ('check_out', '=', False), ('check_in', '<=',  (context_today() - datetime.timedelta(days=1)).strftime('%Y-%m-%d'))]`)
- **Automatically Checked-Out** (`[('out_mode', '=', 'auto_check_out')]`)
- **Date**
- **Active Employees** (`[('employee_id.active', '=', True)]`)
- **Archived Employees** (`[('employee_id.active', '=', False)]`)
- **Last 3 Months** (`[(                     'check_in','>=', (                         context_today() + datetime.timedelta(days=-90)                         )                     )]`)


**Agrupar por:**
- Employee
- Department
- Manager
- Method
- Date


#### Filtros de búsqueda (hr_attendance.hr_attendance_management_view_filter)

**Filtros:**
- **My Attendances** (`[('employee_id.user_id', '=', uid)]`)
- **My Team** (`[('employee_id.parent_id.user_id', '=', uid)]`)
- **To Approve** (`[('overtime_status','=', 'to_approve')]`)
- **Approved** (`[('overtime_status','=', 'approved')]`)
- **Refused** (`[('overtime_status','=', 'refused')]`)
- **Active Employees** (`[('employee_id.active', '=', True)]`)
- **Archived Employees** (`[('employee_id.active', '=', False)]`)


**Agrupar por:**
- Employee


### hr.attendance.overtime

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | hr.attendance.overtime.list | `hr_attendance.view_attendance_overtime_tree` | - |
| search | hr.attendance.overtime.search | `hr_attendance.view_attendance_overtime_search` | - |
| graph | hr.attendance.overtime.graph | `hr_attendance.view_attendance_overtime_graph` | - |
| pivot | hr.attendance.overtime.pivot | `hr_attendance.hr_attendance_overtime_view_pivot` | - |



#### Filtros de búsqueda (hr_attendance.view_attendance_overtime_search)

**Filtros:**
- **Last 3 Months** (`[(                 'date','>=', (                     context_today() + relativedelta(months=-3)                     )                 )]`)


**Agrupar por:**
- Date
- Employee


### hr.employee

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| kanban | hr.employee.kanban | `hr_attendance.hr_employees_view_kanban` | - |


