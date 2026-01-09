# Módulo: Skills Certification

## Información General
- **Nombre técnico:** hr_skills_survey
- **Versión:** 1.0
- **Categoría:** Hidden
- **Dependencias:** hr_skills, survey


## Propósito
Add certification to resume of your employees



## Descripción

Certification and Skills for HR

This module adds certification to resume for employees.
        



## Modelos

### survey.user_input


- Hereda de:

  - survey.user_input




- No agrega campos



### survey.survey


- Hereda de:

  - survey.survey




- Campos:

  - **certification_validity_months** (Integer) → Validity





### hr.resume.line


- Hereda de:

  - hr.resume.line




- Campos:

  - **display_type** (Selection)


  - **department_id** (Many2one)


  - **survey_id** (Many2one) → survey.survey


  - **expiration_status** (Selection)








## Vistas


### hr.resume.line

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | - | `hr_skills_survey.hr_employee_certification_report_view_list` | - |
| search | - | `hr_skills_survey.hr_resume_line_view_search` | - |



#### Filtros de búsqueda (hr_skills_survey.hr_resume_line_view_search)

**Filtros:**
- **Expiring Soon** (`[('expiration_status', '=', 'expiring')]`)
- **Expired** (`[('expiration_status', '=', 'expired')]`)
- **Valid Until**


**Agrupar por:**
- Employee
- Department
- Certification
- Expiration date

