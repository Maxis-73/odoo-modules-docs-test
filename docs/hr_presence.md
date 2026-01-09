# Módulo: Employee Presence Control

## Información General
- **Nombre técnico:** hr_presence
- **Versión:** 1.0
- **Categoría:** Human Resources
- **Dependencias:** hr, hr_holidays, sms




## Descripción

Control Employees Presence
==========================

Based on:
    * The IP Address
    * The User's Session
    * The Sent Emails

Allows to contact directly the employee in case of unjustified absence.
    



## Modelos

### hr.employee.base


- Hereda de:

  - hr.employee.base




#### Campos
- **email_sent** (Boolean)
- **ip_connected** (Boolean)
- **manually_set_present** (Boolean)
- **manually_set_presence** (Boolean)
- **hr_presence_state_display** (Selection)





### res.users.log


- Hereda de:

  - res.users.log




#### Campos
- **create_uid** (Integer)
- **ip** (Char)





### res.config.settings


- Hereda de:

  - res.config.settings




- No agrega campos




### res.company


- Hereda de:

  - res.company




#### Campos
- **hr_presence_last_compute_date** (Datetime)





### hr.employee.base


- Hereda de:

  - hr.employee.base




- No agrega campos




### ir.websocket


- Hereda de:

  - ir.websocket




- No agrega campos






