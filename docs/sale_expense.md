# Módulo: Sales Expense

## Información General
- **Nombre técnico:** sale_expense
- **Versión:** 1.0
- **Categoría:** Sales/Sales
- **Dependencias:** sale_management, hr_expense


## Propósito
Quotation, Sales Orders, Delivery & Invoicing Control



## Descripción

Reinvoice Employee Expense

Create some products for which you can re-invoice the costs.
This module allow to reinvoice employee expense, by setting the SO directly on the expense.




## Modelos

### sale.order


- Hereda de:

  - sale.order




- Campos:

  - **expense_ids** (One2many) → hr.expense


  - **expense_count** (Integer) → # of Expenses





### product.template


- Hereda de:

  - product.template




- Campos:

  - **expense_policy_tooltip** (Char)





### hr.expense.split


- Hereda de:

  - hr.expense.split




- Campos:

  - **sale_order_id** (Many2one) → sale.order


  - **can_be_reinvoiced** (Boolean) → Can be reinvoiced





### hr.expense.sheet


- Hereda de:

  - hr.expense.sheet




- Campos:

  - **sale_order_count** (Integer)





### hr.expense


- Hereda de:

  - hr.expense




- Campos:

  - **sale_order_id** (Many2one) → sale.order


  - **can_be_reinvoiced** (Boolean) → Can be reinvoiced





### account.move.line


- Hereda de:

  - account.move.line




- No agrega campos



### account.move


- Hereda de:

  - account.move




- No agrega campos





