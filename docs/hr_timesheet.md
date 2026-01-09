# Módulo: Task Logs

## Información General
- **Nombre técnico:** hr_timesheet
- **Versión:** 1.1
- **Categoría:** Services/Timesheets
- **Dependencias:** hr, hr_hourly_cost, analytic, project, uom


## Propósito
Track employee time on tasks



## Descripción

This module implements a timesheet system.
==========================================

Each employee can encode and track their time spent on the different projects.

Lots of reporting on time and employee tracking are provided.

It is completely integrated with the cost accounting module. It allows you to set
up a management by affair.
    



## Modelos

### uom.uom


- Hereda de:

  - uom.uom




#### Campos
- **timesheet_widget** (Char) → Widget





### project.collaborator


- Hereda de:

  - project.collaborator




- No agrega campos




### account.analytic.line


- Hereda de:

  - account.analytic.line




#### Campos
- **task_id** (Many2one) → project.task
- **parent_task_id** (Many2one) → project.task
- **project_id** (Many2one) → project.project
- **user_id** (Many2one)
- **employee_id** (Many2one) → hr.employee
- **job_title** (Char)
- **department_id** (Many2one) → hr.department
- **manager_id** (Many2one) → hr.employee
- **encoding_uom_id** (Many2one) → uom.uom
- **partner_id** (Many2one)
- **readonly_timesheet** (Boolean)
- **milestone_id** (Many2one) → project.milestone
- **message_partner_ids** (Many2many) → res.partner





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | account.analytic.line.list.hr_timesheet | `hr_timesheet.hr_timesheet_line_tree` | - |
| pivot | account.analytic.line.pivot | `hr_timesheet.view_hr_timesheet_line_pivot` | - |
| pivot | account.analytic.line.pivot | `hr_timesheet.view_my_timesheet_line_pivot` | - |
| graph | account.analytic.line.graph | `hr_timesheet.view_hr_timesheet_line_graph` | - |
| graph | account.analytic.line.graph | `hr_timesheet.view_hr_timesheet_line_graph_my` | - |
| graph | account.analytic.line.graph | `hr_timesheet.view_hr_timesheet_line_graph_all` | - |
| form | account.analytic.line.form | `hr_timesheet.hr_timesheet_line_form` | - |
| kanban | account.analytic.line.kanban | `hr_timesheet.view_kanban_account_analytic_line` | - |




### account.analytic.applicability


- Hereda de:

  - account.analytic.applicability




#### Campos
- **business_domain** (Selection)





### project.project


- Hereda de:

  - project.project




#### Campos
- **allow_timesheets** (Boolean) → Timesheets
- **account_id** (Many2one)
- **analytic_account_active** (Boolean) → Active Account
- **timesheet_ids** (One2many) → account.analytic.line
- **timesheet_encode_uom_id** (Many2one) → uom.uom
- **total_timesheet_time** (Integer)
- **encode_uom_in_days** (Boolean)
- **is_internal_project** (Boolean)
- **remaining_hours** (Float)
- **is_project_overtime** (Boolean) → Project in Overtime
- **allocated_hours** (Float)
- **effective_hours** (Float)





### hr.employee


- Hereda de:

  - hr.employee




#### Campos
- **has_timesheet** (Boolean)





### project.update


- Hereda de:

  - project.update




#### Campos
- **display_timesheet_stats** (Boolean)
- **allocated_time** (Integer) → Allocated Time
- **timesheet_time** (Integer) → Timesheet Time
- **timesheet_percentage** (Integer)
- **uom_id** (Many2one) → uom.uom





### res.config.settings


- Hereda de:

  - res.config.settings




#### Campos
- **module_project_timesheet_holidays** (Boolean) → Time Off
- **reminder_user_allow** (Boolean)
- **reminder_allow** (Boolean)
- **project_time_mode_id** (Many2one) → uom.uom
- **is_encode_uom_days** (Boolean)
- **timesheet_encode_method** (Selection)





### ir.ui.menu


- Hereda de:

  - ir.ui.menu




- No agrega campos




### res.company


- Hereda de:

  - res.company




#### Campos
- **project_time_mode_id** (Many2one) → uom.uom
- **timesheet_encode_uom_id** (Many2one) → uom.uom
- **internal_project_id** (Many2one) → project.project





### ir.http


- Hereda de:

  - ir.http




- No agrega campos




### project.task


- Hereda de:

  - project.task




#### Campos
- **project_id** (Many2one)
- **analytic_account_active** (Boolean) → Active Analytic Account
- **allow_timesheets** (Boolean) → Allow timesheets
- **remaining_hours** (Float) → Time Remaining
- **remaining_hours_percentage** (Float)
- **effective_hours** (Float) → Time Spent
- **total_hours_spent** (Float) → Total Time Spent
- **progress** (Float) → Progress
- **overtime** (Float)
- **subtask_effective_hours** (Float) → Time Spent on Sub-tasks
- **timesheet_ids** (One2many) → account.analytic.line
- **encode_uom_in_days** (Boolean)
- **display_name** (Char)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | project.sharing.project.task.view.form.inherit | `hr_timesheet.project_sharing_inherit_project_task_view_form` | project.project_sharing_project_task_view_form |
| form | project.task.form.inherited | `hr_timesheet.view_task_form2_inherited` | project.view_task_form2 |



**Botones (hr_timesheet.view_task_form2_inherited):**
- **action_view_subtask_timesheet** (object)








## Vistas Adicionales


### hr.employee.delete.wizard

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | Delete Employee | `hr_timesheet.hr_employee_delete_wizard_form` | - |



**Botones (hr_timesheet.hr_employee_delete_wizard_form):**
- **Archive Employees** (object)
- **See Timesheets** (object) - Grupos: `hr_timesheet.group_hr_timesheet_approver`
- **See Timesheets** (object) - Grupos: `hr_timesheet.group_hr_timesheet_approver`
- **Ok** (object)


### timesheets.analysis.report

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | timesheets.analysis.report.list | `hr_timesheet.timesheets_analysis_report_list` | - |
| form | timesheets.analysis.report.form | `hr_timesheet.timesheets_analysis_report_form` | - |
| pivot | timesheets.analysis.report.pivot | `hr_timesheet.timesheets_analysis_report_pivot_employee` | - |
| graph | timesheets.analysis.report.graph | `hr_timesheet.timesheets_analysis_report_graph_employee` | - |
| pivot | timesheets.analysis.report.pivot | `hr_timesheet.timesheets_analysis_report_pivot_project` | - |
| graph | timesheets.analysis.report.graph | `hr_timesheet.timesheets_analysis_report_graph_project` | - |
| pivot | timesheets.analysis.report.pivot | `hr_timesheet.timesheets_analysis_report_pivot_task` | - |
| graph | timesheets.analysis.report.graph | `hr_timesheet.timesheets_analysis_report_graph_task` | - |
| search | timesheets.analysis.report.search | `hr_timesheet.hr_timesheet_report_search` | hr_timesheet.hr_timesheet_line_search |



### report.project.task.user

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| pivot | report.project.task.user.pivot.inherited | `hr_timesheet.view_task_project_user_pivot_inherited` | project.view_task_project_user_pivot |




