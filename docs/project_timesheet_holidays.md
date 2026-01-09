# Módulo: Timesheet when on Time Off

## Información General
- **Nombre técnico:** project_timesheet_holidays
- **Versión:** 1.0
- **Categoría:** Human Resources
- **Dependencias:** hr_timesheet, hr_holidays


## Propósito
Schedule timesheet when on time off



## Descripción

Bridge module to integrate leaves in timesheet

This module allows to automatically log timesheets when employees are
on leaves. Project and task can be configured company-wide.
    



## Modelos

### hr.employee


- Hereda de:

  - hr.employee




- No agrega campos



### account.analytic.line


- Hereda de:

  - account.analytic.line




- Campos:

  - **holiday_id** (Many2one) → hr.leave


  - **global_leave_id** (Many2one) → resource.calendar.leaves


  - **task_id** (Many2one)





### res.config.settings


- Hereda de:

  - res.config.settings




- Campos:

  - **internal_project_id** (Many2one)


  - **leave_timesheet_task_id** (Many2one)





### resource.calendar.leaves


- Hereda de:

  - resource.calendar.leaves




- Campos:

  - **timesheet_ids** (One2many) → account.analytic.line





### res.company


- Hereda de:

  - res.company




- Campos:

  - **leave_timesheet_task_id** (Many2one) → project.task





### hr.leave.type


- Hereda de:

  - hr.leave.type




- Campos:

  - **timesheet_generate** (Boolean) → Generate Timesheets


  - **timesheet_project_id** (Many2one) → project.project


  - **timesheet_task_id** (Many2one) → project.task





### hr.leave


- Hereda de:

  - hr.leave




- Campos:

  - **timesheet_ids** (One2many) → account.analytic.line





### project.task


- Hereda de:

  - project.task




- Campos:

  - **leave_types_count** (Integer)


  - **is_timeoff_task** (Boolean) → Is Time off Task







