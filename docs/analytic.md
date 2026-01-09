# Módulo: Analytic Accounting

## Información General
- **Nombre técnico:** analytic
- **Versión:** 1.2
- **Categoría:** Accounting/Accounting
- **Dependencias:** base, mail, uom




## Descripción

Module for defining analytic accounting object.

In Odoo, analytic accounts are linked to general accounts but are treated
totally independently. So, you can enter various different analytic operations
that have no counterpart in the general financial accounts.
    



## Modelos

### analytic.mixin


- Hereda de: Base



- Campos:

  - **analytic_distribution** (Json) → Analytic Distribution


  - **analytic_precision** (Integer)


  - **distribution_analytic_account_ids** (Many2many) → account.analytic.account





### account.analytic.plan


- Hereda de: Base



- Campos:

  - **name** (Char)


  - **description** (Text)


  - **parent_id** (Many2one) → account.analytic.plan


  - **parent_path** (Char)


  - **root_id** (Many2one) → account.analytic.plan


  - **children_ids** (One2many) → account.analytic.plan


  - **children_count** (Integer) → Children Plans Count


  - **complete_name** (Char) → Complete Name


  - **account_ids** (One2many) → account.analytic.account


  - **account_count** (Integer) → Analytic Accounts Count


  - **all_account_count** (Integer) → All Analytic Accounts Count


  - **color** (Integer) → Color


  - **sequence** (Integer)


  - **default_applicability** (Selection)


  - **applicability_ids** (One2many) → account.analytic.applicability





### account.analytic.applicability


- Hereda de: Base



- Campos:

  - **analytic_plan_id** (Many2one) → account.analytic.plan


  - **business_domain** (Selection)


  - **applicability** (Selection)


  - **company_id** (Many2one) → res.company





### account.analytic.distribution.model


- Hereda de:

  - analytic.mixin




- Campos:

  - **sequence** (Integer)


  - **partner_id** (Many2one) → res.partner


  - **partner_category_id** (Many2one) → res.partner.category


  - **company_id** (Many2one) → res.company





### account.analytic.account


- Hereda de:


  - mail.thread





- Campos:

  - **name** (Char)


  - **code** (Char)


  - **active** (Boolean) → Active


  - **plan_id** (Many2one) → account.analytic.plan


  - **root_plan_id** (Many2one) → account.analytic.plan


  - **color** (Integer) → Color Index


  - **line_ids** (One2many) → account.analytic.line


  - **company_id** (Many2one) → res.company


  - **partner_id** (Many2one) → res.partner


  - **balance** (Monetary)


  - **debit** (Monetary)


  - **credit** (Monetary)


  - **currency_id** (Many2one)





### res.config.settings


- Hereda de:

  - res.config.settings




- Campos:

  - **group_analytic_accounting** (Boolean)





### analytic.plan.fields.mixin


- Hereda de: Base



- Campos:

  - **account_id** (Many2one) → account.analytic.account


  - **auto_account_id** (Many2one) → account.analytic.account





### account.analytic.line


- Hereda de:

  - analytic.plan.fields.mixin




- Campos:

  - **name** (Char) → Description


  - **date** (Date) → Date


  - **amount** (Monetary) → Amount


  - **unit_amount** (Float) → Quantity


  - **product_uom_id** (Many2one) → uom.uom


  - **product_uom_category_id** (Many2one)


  - **partner_id** (Many2one) → res.partner


  - **user_id** (Many2one) → res.users


  - **company_id** (Many2one) → res.company


  - **currency_id** (Many2one)


  - **category** (Selection)


  - **analytic_distribution** (Json) → Analytic Distribution


  - **analytic_precision** (Integer)





### ir.config_parameter


- Hereda de:

  - ir.config_parameter




- No agrega campos






## Vistas


### account.analytic.account

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | analytic.analytic.account.form | `analytic.view_account_analytic_account_form` | - |
| list | account.analytic.account.list | `analytic.view_account_analytic_account_list` | - |
| list | account.analytic.account.list.select | `analytic.view_account_analytic_account_list_select` | analytic.view_account_analytic_account_list |
| kanban | account.analytic.account.kanban | `analytic.view_account_analytic_account_kanban` | - |
| search | account.analytic.account.search | `analytic.view_account_analytic_account_search` | - |



#### Botones (analytic.view_account_analytic_account_form)
- **%(account_analytic_line_action)d** (action)


#### Filtros de búsqueda (analytic.view_account_analytic_account_search)

**Filtros:**
- **Archived** (`[('active', '=', False)]`)


**Agrupar por:**
- Associated Partner


### account.analytic.distribution.model

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | account.analytic.distribution.model.list | `analytic.account_analytic_distribution_model_tree_view` | - |
| form | account.analytic.distribution.model.form | `analytic.account_analytic_distribution_model_form_view` | - |



### account.analytic.line

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | account.analytic.line.list | `analytic.view_account_analytic_line_tree` | - |
| search | account.analytic.line.select | `analytic.view_account_analytic_line_filter` | - |
| form | account.analytic.line.form | `analytic.view_account_analytic_line_form` | - |
| graph | account.analytic.line.graph | `analytic.view_account_analytic_line_graph` | - |
| pivot | account.analytic.line.pivot | `analytic.view_account_analytic_line_pivot` | - |
| kanban | account.analytic.line.kanban | `analytic.view_account_analytic_line_kanban` | - |



#### Filtros de búsqueda (analytic.view_account_analytic_line_filter)

**Filtros:**
- **Date**


**Agrupar por:**
- Date


### account.analytic.plan

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | account.analytic.plan.form | `analytic.account_analytic_plan_form_view` | - |
| list | account.analytic.plan.list | `analytic.account_analytic_plan_tree_view` | - |



#### Botones (analytic.account_analytic_plan_form_view)
- **action_view_children_plans** (object)
- **action_view_analytical_accounts** (object)

