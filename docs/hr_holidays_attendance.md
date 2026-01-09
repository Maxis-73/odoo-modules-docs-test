# Módulo: HR Attendance Holidays

## Información General
- **Nombre técnico:** hr_holidays_attendance
- **Versión:** 1.0
- **Categoría:** Human Resources
- **Dependencias:** hr_attendance, hr_holidays


## Propósito
Attendance Holidays



## Descripción

Convert employee's extra hours to leave allocations.
    



## Modelos

### hr.leave.accrual.level


- Hereda de:

  - hr.leave.accrual.level




- Campos:

  - **frequency_hourly_source** (Selection)





### hr.leave.allocation


- Hereda de:

  - hr.leave.allocation




- Campos:

  - **overtime_deductible** (Boolean)


  - **overtime_id** (Many2one) → hr.attendance.overtime


  - **employee_overtime** (Float)





### hr.attendance


- Hereda de:

  - hr.attendance




- No agrega campos



### hr.leave.type


- Hereda de:

  - hr.leave.type




- Campos:

  - **overtime_deductible** (Boolean) → Deduct Extra Hours





### hr.leave


- Hereda de:

  - hr.leave




- Campos:

  - **overtime_id** (Many2one) → hr.attendance.overtime


  - **employee_overtime** (Float)


  - **overtime_deductible** (Boolean)





### res.users


- Hereda de:

  - res.users




- Campos:

  - **request_overtime** (Boolean)







