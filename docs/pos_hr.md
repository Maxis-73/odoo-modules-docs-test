# Módulo: POS - HR

## Información General
- **Nombre técnico:** pos_hr
- **Versión:** N/A
- **Categoría:** Hidden
- **Dependencias:** point_of_sale, hr


## Propósito
Link module between Point of Sale and HR



## Descripción

This module allows Employees (and not users) to log in to the Point of Sale application using a barcode, a PIN number or both.
The actual till still requires one user but an unlimited number of employees can log on to that till and process sales.
    



## Modelos

### account.bank.statement.line


- Hereda de:

  - account.bank.statement.line




#### Campos
- **employee_id** (Many2one) → hr.employee





### pos.config


- Hereda de:

  - pos.config




#### Campos
- **basic_employee_ids** (Many2many) → hr.employee
- **advanced_employee_ids** (Many2many) → hr.employee





### report.pos_hr.single_employee_sales_report


- Hereda de:

  - report.point_of_sale.report_saledetails




- No agrega campos




### product.product


- Hereda de:

  - product.product




- No agrega campos




### pos.order


- Hereda de:

  - pos.order




#### Campos
- **employee_id** (Many2one) → hr.employee
- **cashier** (Char)





### pos.payment


- Hereda de:

  - pos.payment




#### Campos
- **employee_id** (Many2one) → hr.employee





### hr.employee


- Hereda de:

  - hr.employee




- No agrega campos




### report.pos_hr.multi_employee_sales_report


- Hereda de: Base



- No agrega campos




### res.config.settings


- Hereda de:

  - res.config.settings




#### Campos
- **pos_basic_employee_ids** (Many2many)
- **pos_advanced_employee_ids** (Many2many)





### pos.session


- Hereda de:

  - pos.session




#### Campos
- **employee_id** (Many2one) → hr.employee







