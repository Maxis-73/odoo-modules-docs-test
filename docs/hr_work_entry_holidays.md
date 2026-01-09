# Módulo: Time Off in Payslips

## Información General
- **Nombre técnico:** hr_work_entry_holidays
- **Versión:** 1.0
- **Categoría:** Human Resources/Payroll
- **Dependencias:** hr_holidays, hr_holidays_contract, hr_work_entry_contract


## Propósito
Manage Time Off in Payslips



## Descripción

Manage Time Off in Payslips
============================

This application allows you to integrate time off in payslips.
    



## Modelos

### hr.contract


- Hereda de:

  - hr.contract




- No agrega campos




### hr.leave.type


- Hereda de:

  - hr.leave.type




#### Campos
- **work_entry_type_id** (Many2one) → hr.work.entry.type





### hr.leave


- Hereda de:

  - hr.leave




- No agrega campos




### hr.work.entry


- Hereda de:

  - hr.work.entry




#### Campos
- **leave_id** (Many2one) → hr.leave
- **leave_state** (Selection)





### hr.work.entry.type


- Hereda de:

  - hr.work.entry.type




#### Campos
- **leave_type_ids** (One2many) → hr.leave.type







