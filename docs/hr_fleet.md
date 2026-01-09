# Módulo: Fleet History

## Información General
- **Nombre técnico:** hr_fleet
- **Versión:** 1.0
- **Categoría:** Human Resources
- **Dependencias:** hr, fleet


## Propósito
Get history of driven cars by employees





## Modelos

### fleet.vehicle.log.contract


- Hereda de:

  - fleet.vehicle.log.contract




- Campos:

  - **purchaser_employee_id** (Many2one)





### fleet.vehicle


- Hereda de:

  - fleet.vehicle




- Campos:

  - **mobility_card** (Char)


  - **driver_employee_id** (Many2one) → hr.employee


  - **driver_employee_name** (Char)


  - **future_driver_employee_id** (Many2one) → hr.employee





### fleet.vehicle.log.services


- Hereda de:

  - fleet.vehicle.log.services




- Campos:

  - **purchaser_employee_id** (Many2one) → hr.employee





### fleet.vehicle.assignation.log


- Hereda de:

  - fleet.vehicle.assignation.log




- Campos:

  - **driver_employee_id** (Many2one) → hr.employee


  - **attachment_number** (Integer) → Number of Attachments





### ['res.users']


- Hereda de:


  - res.users





- Campos:

  - **employee_cars_count** (Integer)





### mail.activity.plan.template


- Hereda de:

  - mail.activity.plan.template




- Campos:

  - **responsible_type** (Selection)





### fleet.vehicle.odometer


- Hereda de:

  - fleet.vehicle.odometer




- Campos:

  - **driver_employee_id** (Many2one)





### hr.employee


- Hereda de:

  - hr.employee




- Campos:

  - **employee_cars_count** (Integer)


  - **car_ids** (One2many) → fleet.vehicle


  - **license_plate** (Char)


  - **mobility_card** (Char)





### hr.employee.public


- Hereda de:

  - hr.employee.public




- Campos:

  - **mobility_card** (Char)







