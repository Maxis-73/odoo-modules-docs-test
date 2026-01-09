# Módulo: Timesheets/attendances reporting

## Información General
- **Nombre técnico:** hr_timesheet_attendance
- **Versión:** 1.1
- **Categoría:** Hidden
- **Dependencias:** hr_timesheet, hr_attendance




## Descripción

    Module linking the attendance module to the timesheet app.
    



## Modelos

### ir.ui.menu


- Hereda de:

  - ir.ui.menu




- No agrega campos






## Vistas


### hr.timesheet.attendance.report

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| search | Search for HR timesheet attendance report | `hr_timesheet_attendance.view_hr_timesheet_attendance_report_search` | - |
| pivot | HR timesheet attendance report: Pivot | `hr_timesheet_attendance.view_hr_timesheet_attendance_report_pivot` | - |
| graph | hr.timesheet.attendance.report.view.graph | `hr_timesheet_attendance.hr_timesheet_attendance_report_view_graph` | - |



#### Filtros de búsqueda (hr_timesheet_attendance.view_hr_timesheet_attendance_report_search)

**Filtros:**
- **My Team** (`[('employee_id.parent_id.user_id', '=', uid)]`)
- **My Department** (`[('employee_id.member_of_department', '=', True)]`)
- **Date**
- **This Week** (`[                             ('date', '>=', context_today() + relativedelta(weeks=-1,days=1,weekday=0)),                             ('date', '<', context_today() + relativedelta(days=1,weekday=0)),                         ]`)
- **Today** (`[                             ('date', '>=', context_today()),                             ('date', '<', context_today() + relativedelta(days=1)),                         ]`)
- **Last Week** (`[                             ('date', '>=', context_today() + relativedelta(weeks=-2,days=1,weekday=0)),                             ('date', '<', context_today() + relativedelta(weeks=-1,days=1,weekday=0)),                         ]`)


**Agrupar por:**
- Employee
- Date

