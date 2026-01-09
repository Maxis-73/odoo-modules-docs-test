# Módulo: Time Off

## Información General
- **Nombre técnico:** hr_holidays
- **Versión:** 1.6
- **Categoría:** Human Resources/Time Off
- **Dependencias:** hr, calendar, resource


## Propósito
Allocate PTOs and follow leaves requests



## Descripción

Manage time off requests and allocations
=====================================

This application controls the time off schedule of your company. It allows employees to request time off. Then, managers can review requests for time off and approve or reject them. This way you can control the overall time off planning for the company or department.

You can configure several kinds of time off (sickness, paid days, ...) and allocate time off to an employee or department quickly using time off allocation. An employee can also make a request for more days off by making a new time off allocation. It will increase the total of available days for that time off type (if the request is accepted).

You can keep track of time off in different ways by following reports:

* Time Off Summary
* Time Off by Department
* Time Off Analysis

A synchronization with an internal agenda (Meetings of the CRM module) is also possible in order to automatically create a meeting when a time off request is accepted by setting up a type of meeting in time off Type.




## Modelos

### hr.leave.mandatory.day


- Hereda de: Base



#### Campos
- **name** (Char)
- **company_id** (Many2one) → res.company
- **start_date** (Date)
- **end_date** (Date)
- **color** (Integer)
- **resource_calendar_id** (Many2one) → resource.calendar
- **department_ids** (Many2many) → hr.department





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | - | `hr_holidays.hr_leave_mandatory_day_view_form` | - |
| list | - | `hr_holidays.hr_leave_mandatory_day_view_list` | - |
| search | - | `hr_holidays.hr_leave_mandatory_day_view_search` | - |



**Filtros de búsqueda (hr_holidays.hr_leave_mandatory_day_view_search):**

- **Period**


*Agrupar por:*
- Department
- Company



### hr.department


- Hereda de:

  - hr.department




#### Campos
- **absence_of_today** (Integer)
- **leave_to_approve_count** (Integer)
- **allocation_to_approve_count** (Integer)





### mail.activity.type


- Hereda de:

  - mail.activity.type




- No agrega campos




### hr.leave.accrual.level


- Hereda de: Base



#### Campos
- **sequence** (Integer)
- **accrual_plan_id** (Many2one) → hr.leave.accrual.plan
- **accrued_gain_time** (Selection)
- **start_count** (Integer) → Start after
- **start_type** (Selection)
- **added_value** (Float) → Rate
- **added_value_type** (Selection)
- **frequency** (Selection)
- **week_day** (Selection)
- **first_day** (Integer)
- **first_day_display** (Selection)
- **second_day** (Integer)
- **second_day_display** (Selection)
- **first_month_day** (Integer)
- **first_month_day_display** (Selection)
- **first_month** (Selection)
- **second_month_day** (Integer)
- **second_month_day_display** (Selection)
- **second_month** (Selection)
- **yearly_month** (Selection)
- **yearly_day** (Integer)
- **yearly_day_display** (Selection)
- **cap_accrued_time** (Boolean) → Cap accrued time
- **maximum_leave** (Float) → Limit to
- **cap_accrued_time_yearly** (Boolean)
- **maximum_leave_yearly** (Float)
- **action_with_unused_accruals** (Selection)
- **postpone_max_days** (Integer) → Maximum amount of accruals to transfer
- **can_modify_value_type** (Boolean)
- **accrual_validity** (Boolean)
- **accrual_validity_count** (Integer) → Accrual Validity Count
- **accrual_validity_type** (Selection)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | hr.leave.accrual.level.form | `hr_holidays.hr_accrual_level_view_form` | - |




### hr.leave.allocation


- Hereda de:


  - mail.thread

  - mail.activity.mixin





#### Campos
- **name** (Char)
- **is_name_custom** (Boolean)
- **name_validity** (Char) → Description with validity
- **state** (Selection)
- **date_from** (Date) → Start Date
- **date_to** (Date) → End Date
- **holiday_status_id** (Many2one) → hr.leave.type
- **employee_id** (Many2one) → hr.employee
- **employee_company_id** (Many2one)
- **active_employee** (Boolean) → Active Employee
- **manager_id** (Many2one) → hr.employee
- **notes** (Text) → Reasons
- **number_of_days** (Float) → Number of Days
- **number_of_days_display** (Float) → Duration (days)
- **number_of_hours_display** (Float) → Duration (hours)
- **duration_display** (Char) → Allocated (Days/Hours)
- **last_executed_carryover_date** (Date)
- **approver_id** (Many2one) → hr.employee
- **second_approver_id** (Many2one) → hr.employee
- **validation_type** (Selection)
- **can_approve** (Boolean) → Can Approve
- **type_request_unit** (Selection)
- **department_id** (Many2one) → hr.department
- **lastcall** (Date) → Date of the last accrual allocation
- **actual_lastcall** (Date)
- **nextcall** (Date) → Date of the next accrual allocation
- **already_accrued** (Boolean)
- **yearly_accrued_amount** (Float)
- **allocation_type** (Selection)
- **is_officer** (Boolean)
- **accrual_plan_id** (Many2one) → hr.leave.accrual.plan
- **max_leaves** (Float)
- **leaves_taken** (Float)
- **expiring_carryover_days** (Float) → The number of carried over days that will expire on carried_over_days_expiration_date
- **carried_over_days_expiration_date** (Date) → Carried over days expiration date





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| search | hr.holidays.filter_allocations | `hr_holidays.view_hr_leave_allocation_filter` | - |
| form | hr.leave.allocation.view.form | `hr_holidays.hr_leave_allocation_view_form` | - |
| list | hr.leave.allocation.view.list | `hr_holidays.hr_leave_allocation_view_tree` | - |
| kanban | hr.leave.allocation.view.kanban | `hr_holidays.hr_leave_allocation_view_kanban` | - |
| activity | hr.leave.allocation.view.activity | `hr_holidays.hr_leave_allocation_view_activity` | - |



**Filtros de búsqueda (hr_holidays.view_hr_leave_allocation_filter):**

- **Waiting For Me** (`[                         ('state','in',['confirm']),                         '|',                         ('employee_id.user_id', '!=', uid),                         '&',                         ('employee_id.user_id', '=', uid),                         ('employee_id.leave_manager_id', '=', uid)]`)
- **Waiting For Me** (`[                         ('state','in',['confirm','validate1']),                         '|',                             ('employee_id.user_id', '!=', uid),                             '|',                                 '&',                                     ('state','=','confirm'),                                     ('holiday_status_id.leave_validation_type','=','hr'),                                 ('state','=','validate1')]`)
- **First Approval** (`[('state','in',('confirm','validate1'))]`)
- **Second Approval** (`[('state', '=', 'validate1')]`)
- **Approved** (`[('state', '=', 'validate')]`)
- **Currently Valid** (`[                         ('date_from', '<=', context_today().strftime('%Y-%m-%d')),                         '|',                         ('date_to', '=', False),                         ('date_to', '>=', context_today().strftime('%Y-%m-%d')),                     ]`)
- **Unread Messages** (`[('message_needaction','=',True)]`)
- **My Team** (`['|', ('employee_id.leave_manager_id', '=', uid), ('employee_id.user_id', '=', uid)]`)
- **My Department** (`[('employee_id.parent_id.user_id', '=', uid)]`)
- **Refused** (`[('state', '=', 'refuse')]`)
- **My Allocations** (`[('employee_id.user_id', '=', uid)]`)
- **Late Activities** (`[('my_activity_date_deadline', '<', context_today().strftime('%Y-%m-%d'))]`)
- **Today Activities** (`[('my_activity_date_deadline', '=', context_today().strftime('%Y-%m-%d'))]`)
- **Future Activities** (`[('my_activity_date_deadline', '>', context_today().strftime('%Y-%m-%d'))                         ]`)
- **To Approve or Approved Allocations** (`[('state', 'in', ('confirm', 'validate'))]`)


*Agrupar por:*
- Employee
- Time Off Type
- Allocation Type
- Status
- Start Date



### mail.message.subtype


- Hereda de:

  - mail.message.subtype




- No agrega campos




### hr.leave.type


- Hereda de: Base



#### Campos
- **name** (Char) → Time Off Type
- **sequence** (Integer)
- **create_calendar_meeting** (Boolean)
- **color** (Integer)
- **icon_id** (Many2one) → ir.attachment
- **active** (Boolean) → Active
- **show_on_dashboard** (Boolean)
- **max_leaves** (Float)
- **leaves_taken** (Float)
- **virtual_remaining_leaves** (Float)
- **allocation_count** (Integer)
- **group_days_leave** (Float)
- **company_id** (Many2one) → res.company
- **country_id** (Many2one) → res.country
- **country_code** (Char)
- **responsible_ids** (Many2many) → res.users
- **leave_validation_type** (Selection)
- **requires_allocation** (Selection)
- **employee_requests** (Selection)
- **allocation_validation_type** (Selection)
- **has_valid_allocation** (Boolean)
- **time_type** (Selection)
- **request_unit** (Selection)
- **unpaid** (Boolean) → Is Unpaid
- **include_public_holidays_in_duration** (Boolean) → Public Holiday Included
- **leave_notif_subtype_id** (Many2one) → mail.message.subtype
- **allocation_notif_subtype_id** (Many2one) → mail.message.subtype
- **support_document** (Boolean)
- **accruals_ids** (One2many) → hr.leave.accrual.plan
- **accrual_count** (Float)
- **allows_negative** (Boolean)
- **max_allowed_negative** (Integer)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| search | hr.leave.type.filter | `hr_holidays.view_holidays_status_filter` | - |
| form | hr.leave.type.form | `hr_holidays.edit_holiday_status_form` | - |
| kanban | hr.leave.type.kanban | `hr_holidays.hr_holiday_status_view_kanban` | - |
| list | hr.leave.type.normal.list | `hr_holidays.view_holiday_status_normal_tree` | - |



**Filtros de búsqueda (hr_holidays.view_holidays_status_filter):**

- **Archived** (`[('active','=',False)]`)


**Botones (hr_holidays.edit_holiday_status_form):**
- **action_see_days_allocated** (object)
- **action_see_group_leaves** (object)
- **action_see_accrual_plans** (object)



### hr.employee


- Hereda de:

  - hr.employee




#### Campos
- **current_leave_id** (Many2one) → hr.leave.type





### hr.leave


- Hereda de:


  - mail.thread.main.attachment

  - mail.activity.mixin





#### Campos
- **name** (Char) → Description
- **private_name** (Char) → Time Off Description
- **state** (Selection)
- **user_id** (Many2one) → res.users
- **manager_id** (Many2one) → hr.employee
- **holiday_status_id** (Many2one) → hr.leave.type
- **color** (Integer) → Color
- **validation_type** (Selection)
- **employee_id** (Many2one) → hr.employee
- **employee_company_id** (Many2one)
- **company_id** (Many2one) → res.company
- **active_employee** (Boolean)
- **tz_mismatch** (Boolean)
- **tz** (Selection)
- **department_id** (Many2one) → hr.department
- **notes** (Text) → Reasons
- **resource_calendar_id** (Many2one) → resource.calendar
- **date_from** (Datetime) → Start Date
- **date_to** (Datetime) → End Date
- **number_of_days** (Float) → Duration (Days)
- **number_of_hours** (Float) → Duration (Hours)
- **last_several_days** (Boolean) → All day
- **duration_display** (Char) → Requested (Days/Hours)
- **meeting_id** (Many2one) → calendar.event
- **first_approver_id** (Many2one) → hr.employee
- **second_approver_id** (Many2one) → hr.employee
- **can_reset** (Boolean) → Can reset
- **can_approve** (Boolean) → Can Approve
- **can_cancel** (Boolean) → Can Cancel
- **attachment_ids** (One2many) → ir.attachment
- **supported_attachment_ids** (Many2many) → ir.attachment
- **supported_attachment_ids_count** (Integer)
- **leave_type_request_unit** (Selection)
- **leave_type_support_document** (Boolean)
- **request_date_from** (Date) → Request Start Date
- **request_date_to** (Date) → Request End Date
- **request_hour_from** (Float)
- **request_hour_to** (Float)
- **request_date_from_period** (Selection)
- **request_unit_half** (Boolean) → Half Day
- **request_unit_hours** (Boolean) → Custom Hours
- **is_hatched** (Boolean) → Hatched
- **is_striked** (Boolean) → Striked
- **has_mandatory_day** (Boolean)
- **leave_type_increases_duration** (Boolean)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| graph | hr.holidays.graph | `hr_holidays.view_evaluation_report_graph` | - |
| search | hr.holidays.filter | `hr_holidays.view_hr_holidays_filter` | - |
| kanban | hr.leave.view.kanban | `hr_holidays.hr_leave_view_kanban` | - |
| activity | hr.leave.view.activity | `hr_holidays.hr_leave_view_activity` | - |
| form | hr.leave.view.form | `hr_holidays.hr_leave_view_form` | - |
| calendar | hr.leave.view.dashboard | `hr_holidays.hr_leave_view_dashboard` | - |
| calendar | hr.leave.view.dashboard | `hr_holidays.hr_leave_employee_view_dashboard` | - |
| calendar | hr.leave.view.calendar | `hr_holidays.hr_leave_view_calendar` | - |
| list | hr.holidays.view.list | `hr_holidays.hr_leave_view_tree` | - |
| pivot | hr.holidays.report_pivot | `hr_holidays.view_holiday_pivot` | - |
| graph | hr.holidays.report_graph | `hr_holidays.view_holiday_graph` | - |
| list | hr.holidays.report_list | `hr_holidays.view_holiday_list` | - |



**Filtros de búsqueda (hr_holidays.view_hr_holidays_filter):**

- **Waiting For Me** (`[                         ('state','in',['confirm']),                         '|',                         ('employee_id.user_id', '!=', uid),                         '&',                         ('employee_id.user_id', '=', uid),                         ('employee_id.leave_manager_id', '=', uid)]`)
- **Waiting For Me** (`[                         ('state','in',['confirm','validate1']),                         '|',                             ('employee_id.user_id', '!=', uid),                             '|',                                 '&',                                     ('state','=','confirm'),                                     ('holiday_status_id.leave_validation_type','=','hr'),                                 ('state','=','validate1')]`)
- **First Approval** (`[('state', '=', 'confirm')]`)
- **Second Approval** (`[('state', '=', 'validate1')]`)
- **Approved** (`[('state', '=', 'validate')]`)
- **My Time Off** (`[('employee_id.user_id', '=', uid)]`)
- **My Team** (`['|', ('employee_id.leave_manager_id', '=', uid), ('employee_id.user_id', '=', uid)]`)
- **My Department** (`[('employee_id.member_of_department', '=', True)]`)
- **Current Year**
- **Cancelled** (`[('state', '=', 'cancel')]`)
- **Refused** (`[('state', '=', 'refuse')]`)
- **Late Activities** (`[('my_activity_date_deadline', '<', context_today().strftime('%Y-%m-%d'))]`)
- **Today Activities** (`[('my_activity_date_deadline', '=', context_today().strftime('%Y-%m-%d'))]`)
- **Future Activities** (`[('my_activity_date_deadline', '>', context_today().strftime('%Y-%m-%d'))                         ]`)


*Agrupar por:*
- Employee
- Type
- Status
- Company
- Start Date


**Botones (hr_holidays.hr_leave_view_form):**
- **Approve** (object)
- **Validate** (object) - Grupos: `hr_holidays.group_hr_holidays_user`
- **Refuse** (object)
- **Cancel** (object)
- **Reset** (object)



### res.users


- Hereda de:

  - res.users




#### Campos
- **leave_manager_id** (Many2one)
- **show_leaves** (Boolean)
- **allocation_count** (Float)
- **leave_date_to** (Date)
- **current_leave_state** (Selection)
- **is_absent** (Boolean)
- **allocation_remaining_display** (Char)
- **allocation_display** (Char)
- **hr_icon_display** (Selection)





### hr.leave.accrual.plan


- Hereda de: Base



#### Campos
- **active** (Boolean)
- **name** (Char) → Name
- **time_off_type_id** (Many2one) → hr.leave.type
- **employees_count** (Integer) → Employees
- **level_ids** (One2many) → hr.leave.accrual.level
- **allocation_ids** (One2many) → hr.leave.allocation
- **company_id** (Many2one) → res.company
- **transition_mode** (Selection)
- **show_transition_mode** (Boolean)
- **is_based_on_worked_time** (Boolean) → Based on worked time
- **accrued_gain_time** (Selection)
- **carryover_date** (Selection)
- **carryover_day** (Integer)
- **carryover_day_display** (Selection)
- **carryover_month** (Selection)
- **added_value_type** (Selection)
- **level_count** (Integer) → Levels





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | hr.leave.accrual.plan.list | `hr_holidays.hr_accrual_plan_view_tree` | - |
| form | hr.leave.accrual.plan.form | `hr_holidays.hr_accrual_plan_view_form` | - |
| search | hr.leave.accrual.plan.search | `hr_holidays.hr_accrual_plan_view_search` | - |



**Botones (hr_holidays.hr_accrual_plan_view_form):**
- **action_open_accrual_plan_employees** (object) - Grupos: `hr.group_hr_user`


**Filtros de búsqueda (hr_holidays.hr_accrual_plan_view_search):**

- **Archived** (`[('active','=',False)]`)


*Agrupar por:*
- Company



### calendar.event


- Hereda de:

  - calendar.event




- No agrega campos




### resource.calendar.leaves


- Hereda de:

  - resource.calendar.leaves




#### Campos
- **holiday_id** (Many2one) → hr.leave





### resource.calendar


- Hereda de:

  - resource.calendar




#### Campos
- **associated_leaves_count** (Integer) → Time Off Count





### hr.employee.base


- Hereda de:

  - hr.employee.base




#### Campos
- **leave_manager_id** (Many2one) → res.users
- **remaining_leaves** (Float)
- **current_leave_state** (Selection)
- **leave_date_from** (Date) → From Date
- **leave_date_to** (Date) → To Date
- **leaves_count** (Float) → Number of Time Off
- **allocation_count** (Float) → Total number of days allocated.
- **allocations_count** (Integer) → Total number of allocations
- **show_leaves** (Boolean) → Able to see Remaining Time Off
- **is_absent** (Boolean) → Absent Today
- **allocation_display** (Char)
- **allocation_remaining_display** (Char)
- **hr_icon_display** (Selection)





### res.partner


- Hereda de:

  - res.partner




- No agrega campos









## Vistas Adicionales


### hr.leave.generate.multi.wizard

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | - | `hr_holidays.hr_leave_generate_multi_wizard_view_form` | - |



**Botones (hr_holidays.hr_leave_generate_multi_wizard_view_form):**
- **Generate Time Off** (object)


### hr.holidays.summary.employee

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | hr.holidays.summary.employee.form | `hr_holidays.view_hr_holidays_summary_employee` | - |



**Botones (hr_holidays.view_hr_holidays_summary_employee):**
- **Print** (object)


### hr.leave.allocation.generate.multi.wizard

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | - | `hr_holidays.hr_leave_allocation_generate_multi_wizard_view_form` | - |



**Botones (hr_holidays.hr_leave_allocation_generate_multi_wizard_view_form):**
- **Create Allocations** (object)


### hr.holidays.cancel.leave

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | - | `hr_holidays.hr_holidays_cancel_leave_form` | - |



**Botones (hr_holidays.hr_holidays_cancel_leave_form):**
- **Cancel Time Off** (object)


### hr.leave.report

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| search | hr.holidays.filter | `hr_holidays.view_hr_holidays_filter_report` | - |
| list | report.hr.holidays.report.leave_all.list | `hr_holidays.hr_leave_report_tree` | - |
| graph | report.hr.holidays.report.leave_all.graph | `hr_holidays.hr_leave_report_graph` | - |
| pivot | report.hr.holidays.report.leave_all.pivot | `hr_holidays.hr_leave_report_pivot` | - |



**Filtros de búsqueda (hr_holidays.view_hr_holidays_filter_report):**

- **To Approve** (`[('state','in',('confirm','validate1'))]`)
- **Approved Requests** (`[('state', '=', 'validate')]`)
- **Time off** (`[('leave_type', '=', 'request')]`)
- **Allocations** (`[('leave_type', '=', 'allocation')]`)
- **My Department** (`[('department_id.manager_id.user_id', '=', uid)]`)
- **Current Year**
- **My Requests** (`[('employee_id.user_id', '=', uid)]`)


*Agrupar por:*
- Employee
- Type
- Company
- Start Date


### hr.leave.report.calendar

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| calendar | hr.leave.report.calendar.view | `hr_holidays.hr_leave_report_calendar_view` | - |
| form | hr.leave.report.calendar.view.form | `hr_holidays.hr_leave_report_calendar_view_form` | - |
| search | hr.leave.report.calendar.view.search | `hr_holidays.hr_leave_report_calendar_view_search` | - |



**Botones (hr_holidays.hr_leave_report_calendar_view_form):**
- **Approve** (object)
- **Validate** (object)
- **Refuse** (object)


**Filtros de búsqueda (hr_holidays.hr_leave_report_calendar_view_search):**

- **My Team** (`['|', ('employee_id.user_id', '=', uid), ('employee_id.parent_id.user_id', '=', uid)]`)
- **My Department** (`[('employee_id.member_of_department', '=', True)]`)
- **Off Today** (`[('is_absent', '=', True)]`)
- **Approved** (`[('state', '=', 'validate')]`)
- **Refused** (`[('state', '=', 'refuse')]`)
- **Waiting for Approval** (`[('state','in',('confirm','validate1'))]`)


*Agrupar por:*
- Job Position
- Time Off Type
- Company
- groupby_department_id


### hr.leave.employee.type.report

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| search | hr.holidays.filter | `hr_holidays.view_search_hr_holidays_employee_type_report` | - |
| pivot | hr.leave.employee.type.report.view.pivot | `hr_holidays.hr_leave_employee_type_report` | - |



**Filtros de búsqueda (hr_holidays.view_search_hr_holidays_employee_type_report):**

- **Period**


*Agrupar por:*
- Company
- Employee



