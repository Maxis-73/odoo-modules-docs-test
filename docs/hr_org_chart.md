# Módulo: HR Org Chart

## Información General
- **Nombre técnico:** hr_org_chart
- **Versión:** 1.0
- **Categoría:** Hidden
- **Dependencias:** hr, web_hierarchy




## Descripción

Org Chart Widget for HR

This module extend the employee form with a organizational chart.
(N+1, N+2, direct subordinates)
        



## Modelos

### hr.employee.base


- Hereda de:

  - hr.employee.base




- Campos:

  - **child_all_count** (Integer) → Indirect Subordinates Count


  - **department_color** (Integer) → Department Color


  - **child_count** (Integer) → Direct Subordinates Count





### ['hr.employee']


- Hereda de:


  - hr.employee





- Campos:

  - **subordinate_ids** (One2many) → hr.employee


  - **is_subordinate** (Boolean)





### ['hr.employee.public']


- Hereda de:


  - hr.employee.public





- Campos:

  - **subordinate_ids** (One2many) → hr.employee.public


  - **is_subordinate** (Boolean)







