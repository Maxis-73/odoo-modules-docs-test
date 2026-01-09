# Módulo: Work Entries

## Información General
- **Nombre técnico:** hr_work_entry
- **Versión:** N/A
- **Categoría:** Human Resources/Employees
- **Dependencias:** hr


## Propósito
Manage work entries





## Modelos

### hr.employee


- Hereda de:

  - hr.employee




- Campos:

  - **has_work_entries** (Boolean)





### resource.calendar.attendance


- Hereda de:

  - resource.calendar.attendance




- Campos:

  - **work_entry_type_id** (Many2one) → hr.work.entry.type





### resource.calendar.leaves


- Hereda de:

  - resource.calendar.leaves




- Campos:

  - **work_entry_type_id** (Many2one) → hr.work.entry.type





### hr.work.entry


- Hereda de: Base



- Campos:

  - **name** (Char)


  - **active** (Boolean)


  - **employee_id** (Many2one) → hr.employee


  - **date_start** (Datetime)


  - **date_stop** (Datetime)


  - **duration** (Float)


  - **work_entry_type_id** (Many2one) → hr.work.entry.type


  - **code** (Char)


  - **external_code** (Char)


  - **color** (Integer)


  - **state** (Selection)


  - **company_id** (Many2one) → res.company


  - **conflict** (Boolean) → Conflicts


  - **department_id** (Many2one) → hr.department


  - **country_id** (Many2one) → res.country





### hr.work.entry.type


- Hereda de: Base



- Campos:

  - **name** (Char)


  - **code** (Char)


  - **external_code** (Char)


  - **color** (Integer)


  - **sequence** (Integer)


  - **active** (Boolean) → Active


  - **country_id** (Many2one) → res.country


  - **country_code** (Char)





### hr.user.work.entry.employee


- Hereda de: Base



- Campos:

  - **user_id** (Many2one) → res.users


  - **employee_id** (Many2one) → hr.employee


  - **active** (Boolean) → Active








## Vistas


### hr.work.entry

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| calendar | hr.work.entry.calendar | `hr_work_entry.hr_work_entry_view_calendar` | - |
| form | hr.work.entry.form | `hr_work_entry.hr_work_entry_view_form` | - |
| list | hr.work.entry.list | `hr_work_entry.hr_work_entry_view_tree` | - |
| pivot | hr.work.entry.pivot | `hr_work_entry.hr_work_entry_view_pivot` | - |
| search | hr.work.entry.filter | `hr_work_entry.hr_work_entry_view_search` | - |



#### Filtros de búsqueda (hr_work_entry.hr_work_entry_view_search)

**Filtros:**
- **Draft** (`[('state', '=', 'draft')]`)
- **Validated** (`[('state', '=', 'validated')]`)
- **Conflicting** (`[('state', '=', 'conflict')]`)
- **Date**
- **Current Month** (`[                     ('date_stop', '>=', (context_today()).strftime('%Y-%m-01')),                     ('date_start', '<', (context_today() + relativedelta(months=1)).strftime('%Y-%m-01'))]`)
- **Archived** (`[('active', '=', False)]`)


**Agrupar por:**
- Employee
- Department
- Type
- Start Date


### hr.work.entry.type

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| search | hr.work.entry.type.view.search | `hr_work_entry.hr_work_entry_type_view_search` | - |
| list | hr.work.entry.type.list | `hr_work_entry.hr_work_entry_type_view_tree` | - |
| form | hr.work.entry.type.form | `hr_work_entry.hr_work_entry_type_view_form` | - |
| kanban | hr.work.entry.type.kanban.view | `hr_work_entry.hr_work_entry_type_view_kanban` | - |



#### Filtros de búsqueda (hr_work_entry.hr_work_entry_type_view_search)

**Filtros:**
- **Archived** (`[('active', '=', False)]`)

