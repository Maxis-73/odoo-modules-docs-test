# Módulo: Remote Work

## Información General
- **Nombre técnico:** hr_homeworking
- **Versión:** 2.0
- **Categoría:** Human Resources/Remote Work
- **Dependencias:** hr






## Modelos

### hr.employee.base


- Hereda de:

  - hr.employee.base




- Campos:

  - **monday_location_id** (Many2one) → hr.work.location


  - **tuesday_location_id** (Many2one) → hr.work.location


  - **wednesday_location_id** (Many2one) → hr.work.location


  - **thursday_location_id** (Many2one) → hr.work.location


  - **friday_location_id** (Many2one) → hr.work.location


  - **saturday_location_id** (Many2one) → hr.work.location


  - **sunday_location_id** (Many2one) → hr.work.location


  - **exceptional_location_id** (Many2one) → hr.work.location


  - **hr_icon_display** (Selection)


  - **today_location_name** (Char)





### ['res.users']


- Hereda de:


  - res.users





- Campos:

  - **monday_location_id** (Many2one) → hr.work.location


  - **tuesday_location_id** (Many2one) → hr.work.location


  - **wednesday_location_id** (Many2one) → hr.work.location


  - **thursday_location_id** (Many2one) → hr.work.location


  - **friday_location_id** (Many2one) → hr.work.location


  - **saturday_location_id** (Many2one) → hr.work.location


  - **sunday_location_id** (Many2one) → hr.work.location





### hr.work.location


- Hereda de:

  - hr.work.location




- No agrega campos



### hr.employee.location


- Hereda de: Base



- Campos:

  - **work_location_id** (Many2one) → hr.work.location


  - **work_location_name** (Char)


  - **work_location_type** (Selection)


  - **employee_id** (Many2one) → hr.employee


  - **employee_name** (Char)


  - **date** (Date)


  - **day_week_string** (Char)





### res.partner


- Hereda de:

  - res.partner




- No agrega campos





