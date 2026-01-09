# Módulo: Employee Contracts

## Información General
- **Nombre técnico:** hr_contract
- **Versión:** 1.0
- **Categoría:** Human Resources/Contracts
- **Dependencias:** hr




## Descripción

Add all information on the employee form to manage contracts.

    * Contract
    * Place of Birth,
    * Medical Examination Date
    * Company Vehicle

You can assign several contracts per employee.
    



## Modelos

### hr.contract


- Hereda de:


  - mail.thread

  - mail.activity.mixin





- Campos:

  - **name** (Char) → Contract Reference


  - **active** (Boolean)


  - **structure_type_id** (Many2one) → hr.payroll.structure.type


  - **employee_id** (Many2one) → hr.employee


  - **active_employee** (Boolean)


  - **department_id** (Many2one) → hr.department


  - **job_id** (Many2one) → hr.job


  - **date_start** (Date) → Start Date


  - **date_end** (Date) → End Date


  - **trial_date_end** (Date) → End of Trial Period


  - **resource_calendar_id** (Many2one) → resource.calendar


  - **wage** (Monetary) → Wage


  - **contract_wage** (Monetary) → Contract Wage


  - **notes** (Html) → Notes


  - **state** (Selection)


  - **company_id** (Many2one) → res.company


  - **company_country_id** (Many2one) → res.country


  - **country_code** (Char)


  - **contract_type_id** (Many2one) → hr.contract.type


  - **contracts_count** (Integer)


  - **kanban_state** (Selection)


  - **currency_id** (Many2one)


  - **permit_no** (Char) → Work Permit No


  - **visa_no** (Char) → Visa No


  - **hr_responsible_id** (Many2one) → res.users


  - **calendar_mismatch** (Boolean)


  - **first_contract_date** (Date)





### hr.employee.public


- Hereda de:

  - hr.employee.public




- Campos:

  - **first_contract_date** (Date)





### hr.employee.base


- Hereda de:

  - hr.employee.base




- No agrega campos



### hr.employee


- Hereda de:

  - hr.employee




- Campos:

  - **legal_name** (Char)


  - **vehicle** (Char)


  - **contract_ids** (One2many) → hr.contract


  - **contract_id** (Many2one) → hr.contract


  - **calendar_mismatch** (Boolean)


  - **contracts_count** (Integer)


  - **contract_warning** (Boolean)


  - **first_contract_date** (Date)





### ['res.users']


- Hereda de:


  - res.users





- Campos:

  - **vehicle** (Char)


  - **bank_account_id** (Many2one)





### res.config.settings


- Hereda de:

  - res.config.settings




- Campos:

  - **contract_expiration_notice_period** (Integer)


  - **work_permit_expiration_notice_period** (Integer)





### resource.calendar.leaves


- Hereda de:

  - resource.calendar.leaves




- No agrega campos



### resource.calendar


- Hereda de:

  - resource.calendar




- Campos:

  - **contracts_count** (Integer) → # Contracts using it





### ir.ui.menu


- Hereda de:

  - ir.ui.menu




- No agrega campos



### res.company


- Hereda de:

  - res.company




- Campos:

  - **contract_expiration_notice_period** (Integer) → Contract Expiry Notice Period


  - **work_permit_expiration_notice_period** (Integer) → Work Permit Expiry Notice Period





### resource.resource


- Hereda de:

  - resource.resource




- No agrega campos



### hr.payroll.structure.type


- Hereda de: Base



- Campos:

  - **name** (Char) → Salary Structure Type


  - **default_resource_calendar_id** (Many2one) → resource.calendar


  - **country_id** (Many2one) → res.country


  - **country_code** (Char)








## Vistas


### hr.contract

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| search | hr.contract.search | `hr_contract.hr_contract_view_search` | - |
| form | hr.contract.form | `hr_contract.hr_contract_view_form` | - |
| list | hr.contract.list | `hr_contract.hr_contract_view_tree` | - |
| kanban | hr.contract.kanban | `hr_contract.hr_contract_view_kanban` | - |
| activity | hr.contract.activity | `hr_contract.hr_contract_view_activity` | - |



#### Filtros de búsqueda (hr_contract.hr_contract_view_search)

**Filtros:**
- **Running Contracts** (`[('state', '=', 'open')]`)
- **Contracts to review** (`[('state', 'in', ['draft', 'close'])]`)
- **Start Date**
- **End Date**
- **Archived** (`[('active', '=', False)]`)
- **Late Activities** (`[('my_activity_date_deadline', '<', context_today().strftime('%Y-%m-%d'))]`)
- **Today Activities** (`[('my_activity_date_deadline', '=', context_today().strftime('%Y-%m-%d'))]`)
- **Future Activities** (`[('my_activity_date_deadline', '>', context_today().strftime('%Y-%m-%d'))]`)


**Agrupar por:**
- Status
- Employee
- Start Date
- Job Position
- Department
- Working Schedule
- Salary Structure Type


#### Botones (hr_contract.hr_contract_view_form)
- **action_open_contract_list** (object) - Grupos: `hr_contract.group_hr_contract_employee_manager`


### hr.contract.history

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| search | hr.contract.history.search | `hr_contract.hr_contract_history_view_search` | - |
| form | hr.contract.history.form | `hr_contract.hr_contract_history_view_form` | - |
| list | hr.contract.history.list | `hr_contract.hr_contract_history_view_list` | - |
| kanban | hr.contract.history.view.kanban | `hr_contract.hr_contract_history_view_kanban` | - |



#### Filtros de búsqueda (hr_contract.hr_contract_history_view_search)

**Filtros:**
- **Running Contracts** (`[('state', '=', 'open')]`)
- **Contracts to Review** (`['|', ('state', 'in', ['draft', 'close', 'cancel']), ('is_under_contract', '!=', True)]`)
- **No Contracts** (`[('contract_id', '=', False)]`)
- **Currently Under Contract** (`[('is_under_contract', '=', True)]`)
- **Active Employees** (`[('active_employee', '=', True)]`)


**Agrupar por:**
- Job Position
- Status
- Reference Working Time
- Salary Structure Type


#### Botones (hr_contract.hr_contract_history_view_form)
- **Create** (object) - Grupos: `hr_contract.group_hr_contract_manager`
- **action_open_contract_form** (object)

