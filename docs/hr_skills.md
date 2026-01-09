# Módulo: Skills Management

## Información General
- **Nombre técnico:** hr_skills
- **Versión:** 1.0
- **Categoría:** Human Resources/Employees
- **Dependencias:** hr


## Propósito
Manage skills, knowledge and resume of your employees



## Descripción

Skills and Resume for HR
========================

This module introduces skills and resume management for employees.
        



## Modelos

### hr.employee.skill


- Hereda de: Base



#### Campos
- **employee_id** (Many2one) → hr.employee
- **skill_id** (Many2one) → hr.skill
- **skill_level_id** (Many2one) → hr.skill.level
- **skill_type_id** (Many2one) → hr.skill.type
- **level_progress** (Integer)
- **color** (Integer)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | hr.employees.skill.form | `hr_skills.employee_skill_view_form` | - |




### hr.employee.skill.log


- Hereda de: Base



#### Campos
- **employee_id** (Many2one) → hr.employee
- **department_id** (Many2one) → hr.department
- **skill_id** (Many2one) → hr.skill
- **skill_level_id** (Many2one) → hr.skill.level
- **skill_type_id** (Many2one) → hr.skill.type
- **level_progress** (Integer)
- **date** (Date)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| graph | hr.employee.skill.log.view.graph | `hr_skills.hr_employee_skill_log_view_graph_employee` | - |
| graph | hr.employee.skill.log.view.graph | `hr_skills.hr_employee_skill_log_view_graph_department` | - |
| list | hr.employee.skill.log.view.list | `hr_skills.hr_employee_skill_log_view_tree` | - |
| search | hr.employee.skill.log.view.search | `hr_skills.hr_employee_skill_log_view_search` | - |



**Filtros de búsqueda (hr_skills.hr_employee_skill_log_view_search):**


*Agrupar por:*
- Employee
- Skill
- Skill Type
- Date



### hr.skill


- Hereda de: Base



#### Campos
- **name** (Char)
- **sequence** (Integer)
- **skill_type_id** (Many2one) → hr.skill.type
- **color** (Integer)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | hr.skill.list | `hr_skills.employee_skill_view_tree` | - |
| form | hr.skill.form | `hr_skills.hr_skill_view_form` | - |
| search | hr.skill.view.search | `hr_skills.hr_skill_view_search` | - |



**Filtros de búsqueda (hr_skills.hr_skill_view_search):**


*Agrupar por:*
- Skill Type



### hr.employee


- Hereda de:

  - hr.employee




#### Campos
- **resume_line_ids** (One2many) → hr.resume.line
- **employee_skill_ids** (One2many) → hr.employee.skill
- **skill_ids** (Many2many) → hr.skill





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | hr.employee.view.form.inherit.resume | `hr_skills.hr_employee_view_form` | hr.view_employee_form |




### hr.resume.line.type


- Hereda de: Base



#### Campos
- **name** (Char)
- **sequence** (Integer) → Sequence





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | hr.resume.line.type.list.view | `hr_skills.hr_resume_line_type_tree_view` | - |




### hr.skill.type


- Hereda de: Base



#### Campos
- **active** (Boolean) → Active
- **name** (Char)
- **skill_ids** (One2many) → hr.skill
- **skill_level_ids** (One2many) → hr.skill.level
- **color** (Integer) → Color





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| search | hr.skill.type.search | `hr_skills.hr_skill_type_view_search` | - |
| list | hr.skill.type.list | `hr_skills.hr_skill_type_view_tree` | - |
| form | hr.skill.type.form | `hr_skills.hr_employee_skill_type_view_form` | - |



**Filtros de búsqueda (hr_skills.hr_skill_type_view_search):**

- **Archived** (`[('active', '=', False)]`)



### hr.skill.level


- Hereda de: Base



#### Campos
- **skill_type_id** (Many2one) → hr.skill.type
- **name** (Char)
- **level_progress** (Integer)
- **default_level** (Boolean)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | hr.skill.level.list | `hr_skills.employee_skill_level_view_tree` | - |
| form | hr.skill.level.form | `hr_skills.employee_skill_level_view_form` | - |




### ['res.users']


- Hereda de:


  - res.users





#### Campos
- **resume_line_ids** (One2many)
- **employee_skill_ids** (One2many)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | hr.user.preferences.form.inherit.hr.skills | `hr_skills.res_users_view_form` | hr.res_users_view_form_profile |




### hr.resume.line


- Hereda de: Base



#### Campos
- **employee_id** (Many2one) → hr.employee
- **name** (Char)
- **date_start** (Date)
- **date_end** (Date)
- **description** (Html)
- **line_type_id** (Many2one) → hr.resume.line.type
- **display_type** (Selection)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | hr.resume.line.form | `hr_skills.resume_line_view_form` | - |




### hr.employee.public


- Hereda de:

  - hr.employee.public




#### Campos
- **resume_line_ids** (One2many) → hr.resume.line
- **employee_skill_ids** (One2many) → hr.employee.skill





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | hr.employee.public.view.form.inherit.resume | `hr_skills.hr_employee_public_view_form_inherit` | hr.hr_employee_public_view_form |




### ['resource.resource']


- Hereda de:


  - resource.resource





#### Campos
- **employee_skill_ids** (One2many)










## Vistas Adicionales


### hr.employee.cv.wizard

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | hr.employee.cv.wizard.view.form | `hr_skills.hr_employee_cv_wizard_view_form` | - |



**Botones (hr_skills.hr_employee_cv_wizard_view_form):**
- **Print** (object)


### hr.employee.skill.report

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| pivot | - | `hr_skills.hr_employee_skill_report_view_pivot` | - |
| graph | - | `hr_skills.hr_employee_skill_report_view_graph` | - |
| list | - | `hr_skills.hr_employee_skill_report_view_list` | - |
| search | - | `hr_skills.hr_employee_skill_report_view_search` | - |



**Filtros de búsqueda (hr_skills.hr_employee_skill_report_view_search):**

- **Employees with Skills** (`[('skill_id', '!=', False)]`)
- **Employees without Skills** (`[('skill_id', '=', False)]`)
- **Archived** (`[('active', '=', False)]`)


*Agrupar por:*
- Employee
- Department
- Skill Type
- Skill



