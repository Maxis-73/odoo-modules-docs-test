# Módulo: Maintenance - HR

## Información General
- **Nombre técnico:** hr_maintenance
- **Versión:** 1.0
- **Categoría:** Human Resources
- **Dependencias:** hr, maintenance


## Propósito
Equipment, Assets, Internal Hardware, Allocation Tracking



## Descripción

Bridge between HR and Maintenance.



## Modelos

### res.users


- Hereda de:

  - res.users




- Campos:

  - **equipment_ids** (One2many) → maintenance.equipment


  - **equipment_count** (Integer)





### hr.employee


- Hereda de:

  - hr.employee




- Campos:

  - **equipment_ids** (One2many) → maintenance.equipment


  - **equipment_count** (Integer) → Equipment Count





### maintenance.equipment


- Hereda de:

  - maintenance.equipment




- Campos:

  - **employee_id** (Many2one) → hr.employee


  - **department_id** (Many2one) → hr.department


  - **equipment_assign_to** (Selection)


  - **owner_user_id** (Many2one)


  - **assign_date** (Date)





### maintenance.request


- Hereda de:

  - maintenance.request




- Campos:

  - **employee_id** (Many2one) → hr.employee


  - **owner_user_id** (Many2one)


  - **equipment_id** (Many2one)







