# Módulo: Sales Expense Margin

## Información General
- **Nombre técnico:** sale_expense_margin
- **Versión:** 1.0
- **Categoría:** Sales/Sales
- **Dependencias:** sale_expense, sale_margin




## Descripción
When re-invoicing the expense on the SO, set the cost to the total untaxed amount of the expense.



## Modelos

### sale.order.line


- Hereda de:

  - sale.order.line




#### Campos
- **expense_id** (Many2one) → hr.expense





### account.move.line


- Hereda de:

  - account.move.line




- No agrega campos






