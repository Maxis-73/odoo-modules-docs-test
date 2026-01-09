# Módulo: Expenses

## Información General
- **Nombre técnico:** hr_expense
- **Versión:** 2.0
- **Categoría:** Human Resources/Expenses
- **Dependencias:** account, web_tour, hr


## Propósito
Submit, validate and reinvoice employee expenses



## Descripción

Manage expenses by Employees

This application allows you to manage your employees' daily expenses. It gives you access to your employees’ fee notes and give you the right to complete and validate or refuse the notes. After validation it creates an invoice for the employee.
Employee can encode their own expenses and the validation flow puts it automatically in the accounting after validation by managers.


The whole flow is implemented as:
---------------------------------
* Draft expense
* Submitted by the employee to his manager
* Approved by his manager
* Validation by the accountant and accounting entries creation

This module also uses analytic accounting and is compatible with the invoice on timesheet module so that you are able to automatically re-invoice your customers' expenses if your work by project.
    



## Modelos

### hr.department


- Hereda de:

  - hr.department




- Campos:

  - **expense_sheets_to_approve_count** (Integer)





### account.analytic.applicability


- Hereda de:

  - account.analytic.applicability




- Campos:

  - **business_domain** (Selection)





### account.analytic.account


- Hereda de:

  - account.analytic.account




- No agrega campos



### product.product


- Hereda de:

  - product.product




- Campos:

  - **standard_price_update_warning** (Char)





### account.payment


- Hereda de:

  - account.payment




- Campos:

  - **expense_sheet_id** (Many2one)





### product.template


- Hereda de:

  - product.template




- Campos:

  - **can_be_expensed** (Boolean)





### hr.expense.sheet


- Hereda de:


  - mail.thread.main.attachment

  - mail.activity.mixin





- Campos:

  - **name** (Char)


  - **expense_line_ids** (One2many) → hr.expense


  - **nb_expense** (Integer)


  - **state** (Selection)


  - **approval_state** (Selection)


  - **approval_date** (Datetime)


  - **company_id** (Many2one) → res.company


  - **employee_id** (Many2one) → hr.employee


  - **department_id** (Many2one) → hr.department


  - **user_id** (Many2one) → res.users


  - **product_ids** (Many2many) → product.product


  - **total_amount** (Monetary)


  - **untaxed_amount** (Monetary)


  - **total_tax_amount** (Monetary)


  - **amount_residual** (Monetary)


  - **currency_id** (Many2one) → res.currency


  - **company_currency_id** (Many2one) → res.currency


  - **is_multiple_currency** (Boolean)


  - **payment_state** (Selection)


  - **payment_mode** (Selection)


  - **employee_journal_id** (Many2one) → account.journal


  - **selectable_payment_method_line_ids** (Many2many) → account.payment.method.line


  - **payment_method_line_id** (Many2one) → account.payment.method.line


  - **attachment_ids** (One2many) → ir.attachment


  - **message_main_attachment_id** (Many2one)


  - **accounting_date** (Date)


  - **account_move_ids** (One2many) → account.move


  - **nb_account_move** (Integer)


  - **journal_id** (Many2one) → account.journal


  - **can_reset** (Boolean)


  - **can_approve** (Boolean)


  - **cannot_approve_reason** (Char)


  - **is_editable** (Boolean)





### hr.expense


- Hereda de:


  - mail.thread.main.attachment

  - mail.activity.mixin

  - analytic.mixin





- Campos:

  - **name** (Char)


  - **date** (Date)


  - **employee_id** (Many2one) → hr.employee


  - **company_id** (Many2one) → res.company


  - **product_id** (Many2one) → product.product


  - **product_description** (Html)


  - **product_uom_id** (Many2one) → uom.uom


  - **product_uom_category_id** (Many2one) → uom.category


  - **product_has_cost** (Boolean)


  - **product_has_tax** (Boolean)


  - **quantity** (Float)


  - **description** (Text)


  - **message_main_attachment_checksum** (Char)


  - **nb_attachment** (Integer)


  - **attachment_ids** (One2many) → ir.attachment


  - **state** (Selection)


  - **sheet_id** (Many2one) → hr.expense.sheet


  - **approved_by** (Many2one) → res.users


  - **approved_on** (Datetime)


  - **duplicate_expense_ids** (Many2many) → hr.expense


  - **same_receipt_expense_ids** (Many2many) → hr.expense


  - **tax_amount_currency** (Monetary)


  - **tax_amount** (Monetary)


  - **total_amount_currency** (Monetary)


  - **untaxed_amount_currency** (Monetary)


  - **total_amount** (Monetary)


  - **price_unit** (Float)


  - **currency_id** (Many2one) → res.currency


  - **company_currency_id** (Many2one) → res.currency


  - **is_multiple_currency** (Boolean)


  - **currency_rate** (Float)


  - **label_currency_rate** (Char)


  - **payment_mode** (Selection)


  - **vendor_id** (Many2one) → res.partner


  - **account_id** (Many2one) → account.account


  - **tax_ids** (Many2many) → account.tax


  - **accounting_date** (Date)


  - **is_editable** (Boolean)





### ir.actions.report


- Hereda de:

  - ir.actions.report




- No agrega campos



### hr.employee.base


- Hereda de:

  - hr.employee.base




- Campos:

  - **filter_for_expense** (Boolean)





### hr.employee


- Hereda de:

  - hr.employee




- Campos:

  - **expense_manager_id** (Many2one) → res.users





### hr.employee.public


- Hereda de:

  - hr.employee.public




- Campos:

  - **expense_manager_id** (Many2one) → res.users





### ['res.users']


- Hereda de:


  - res.users





- Campos:

  - **expense_manager_id** (Many2one)





### account.move


- Hereda de:

  - account.move




- Campos:

  - **expense_sheet_id** (Many2one) → hr.expense.sheet


  - **show_commercial_partner_warning** (Boolean)





### ir.attachment


- Hereda de:

  - ir.attachment




- No agrega campos



### account.tax


- Hereda de:

  - account.tax




- No agrega campos



### res.config.settings


- Hereda de:

  - res.config.settings




- Campos:

  - **hr_expense_alias_prefix** (Char) → Default Alias Name for Expenses


  - **hr_expense_alias_domain_id** (Many2one) → mail.alias.domain


  - **hr_expense_use_mailgateway** (Boolean)


  - **module_hr_payroll_expense** (Boolean)


  - **module_hr_expense_extract** (Boolean)


  - **expense_journal_id** (Many2one) → account.journal


  - **expense_outstanding_account_id** (Many2one) → account.account


  - **company_expense_allowed_payment_method_line_ids** (Many2many) → account.payment.method.line





### account.move.line


- Hereda de:

  - account.move.line




- Campos:

  - **expense_id** (Many2one) → hr.expense





### res.company


- Hereda de:

  - res.company




- Campos:

  - **expense_journal_id** (Many2one) → account.journal


  - **expense_outstanding_account_id** (Many2one) → account.account


  - **company_expense_allowed_payment_method_line_ids** (Many2many) → account.payment.method.line








## Vistas


### hr.expense

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | hr.expense.list | `hr_expense.hr_expense_view_expenses_analysis_tree` | - |
| form | hr.expense.view.form | `hr_expense.hr_expense_view_form` | - |
| kanban | hr.expense.kanban | `hr_expense.hr_expense_view_expenses_analysis_kanban` | - |
| pivot | hr.expense.pivot | `hr_expense.hr_expense_view_pivot` | - |
| graph | hr.expense.graph | `hr_expense.hr_expense_view_graph` | - |
| search | hr.expense.view.search | `hr_expense.hr_expense_view_search` | - |
| activity | hr.expense.activity | `hr_expense.hr_expense_view_activity` | - |



#### Botones (hr_expense.hr_expense_view_form)
- **Create Report** (object)
- **View Report** (object)
- **Create Report** (object)
- **View Report** (object)
- **Split Expense** (object)


#### Filtros de búsqueda (hr_expense.hr_expense_view_search)

**Filtros:**
- **My Expenses** (`[('employee_id.user_id', '=', uid)]`)
- **My Team** (`[('employee_id.parent_id.user_id', '=', uid)]`)
- **To Report** (`[('sheet_id', '=', False)]`)
- **Refused** (`[('state', '=', 'refused')]`)
- **To Submit** (`[('state', 'in', ('draft', 'reported')), ('employee_id.user_id', '=', uid)]`)
- **Under Validation** (`[('state', '=', 'submitted'), ('employee_id.user_id', '=', uid)]`)
- **To be Reimbursed** (`[('state', '=', 'approved'), ('payment_mode', '=', 'own_account'), ('employee_id.user_id', '=', uid)]`)
- **Expense Date**
- **Former Employees** (`[('employee_id.active', '=', False)]`)
- **Late Activities** (`[('my_activity_date_deadline', '<', context_today().strftime('%Y-%m-%d'))]`)
- **Today Activities** (`[('my_activity_date_deadline', '=', context_today().strftime('%Y-%m-%d'))]`)
- **Future Activities** (`[('my_activity_date_deadline', '>', context_today().strftime('%Y-%m-%d'))]`)


**Agrupar por:**
- Employee
- Category
- Status
- Expense Date
- Company


### product.product

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | product.product.expense.form | `hr_expense.product_product_expense_form_view` | - |
| list | product.product.expense.list | `hr_expense.product_product_expense_tree_view` | - |
| list | product.product.expense.categories.list.view | `hr_expense.product_product_expense_categories_tree_view` | - |



### hr.expense.sheet

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | hr.expense.sheet.list | `hr_expense.view_hr_expense_sheet_tree` | - |
| form | hr.expense.sheet.form | `hr_expense.view_hr_expense_sheet_form` | - |
| kanban | hr.expense.sheet.kanban | `hr_expense.view_hr_expense_sheet_kanban` | - |
| pivot | hr.expense.sheet.pivot | `hr_expense.view_hr_expense_sheet_pivot` | - |
| graph | hr.expense.sheet.graph | `hr_expense.view_hr_expense_sheet_graph` | - |
| search | hr.expense.sheet.view.search | `hr_expense.hr_expense_sheet_view_search` | - |
| activity | hr.expense.sheet.activity | `hr_expense.hr_expense_sheet_view_activity` | - |



#### Botones (hr_expense.view_hr_expense_sheet_form)
- **Submit to Manager** (object)
- **Approve** (object)
- **Post Journal Entries** (object) - Grupos: `account.group_account_invoice`
- **Pay** (object) - Grupos: `account.group_account_invoice`
- **Refuse** (object) - Grupos: `hr_expense.group_hr_expense_team_approver`
- **Reset to Draft** (object) - Grupos: `account.group_account_invoice`
- **Reset to Draft** (object) - Grupos: `!account.group_account_invoice`
- **action_open_account_moves** (object) - Grupos: `account.group_account_invoice`
- **action_open_expense_view** (object)
- **action_get_attachment_view** (object)


#### Filtros de búsqueda (hr_expense.hr_expense_sheet_view_search)

**Filtros:**
- **My Reports** (`[('employee_id.user_id', '=', uid)]`)
- **My Team** (`[('employee_id.parent_id.user_id', '=', uid)]`)
- **Not Refused** (`[('employee_id.user_id', '=', uid), ('state', '!=', 'cancel')]`)
- **Date**
- **Former Employees** (`[('employee_id.active', '=', False)]`)
- **Late Activities** (`[('my_activity_date_deadline', '<', context_today().strftime('%Y-%m-%d'))]`)
- **Today Activities** (`[('my_activity_date_deadline', '=', context_today().strftime('%Y-%m-%d'))]`)
- **Future Activities** (`[('my_activity_date_deadline', '>', context_today().strftime('%Y-%m-%d'))                             ]`)


**Agrupar por:**
- Employee
- Department
- Company
- Date
- Status


### hr.expense.approve.duplicate

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | - | `hr_expense.hr_expense_approve_duplicate_view_form` | - |



#### Botones (hr_expense.hr_expense_approve_duplicate_view_form)
- **Refuse** (object)
- **Approve** (object)


### hr.expense.refuse.wizard

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | hr.expense.refuse.wizard.form | `hr_expense.hr_expense_refuse_wizard_view_form` | - |



#### Botones (hr_expense.hr_expense_refuse_wizard_view_form)
- **Refuse** (object)


### hr.expense.split.wizard

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | Expense split | `hr_expense.hr_expense_split` | - |



#### Botones (hr_expense.hr_expense_split)
- **Split Expense** (object)
- **Split Expense** (object)

