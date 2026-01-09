# Módulo: Sales - Project

## Información General
- **Nombre técnico:** sale_project
- **Versión:** N/A
- **Categoría:** Hidden
- **Dependencias:** sale_management, sale_service, project_account


## Propósito
Task Generation from Sales Orders



## Descripción

Allows to create task from your sales order
=============================================
This module allows to generate a project/task from sales orders.




## Modelos

### sale.order


- Hereda de:

  - sale.order




#### Campos
- **tasks_ids** (Many2many) → project.task
- **tasks_count** (Integer)
- **visible_project** (Boolean) → Display project
- **project_ids** (Many2many) → project.project
- **project_count** (Integer)
- **milestone_count** (Integer)
- **is_product_milestone** (Boolean)
- **show_create_project_button** (Boolean)
- **show_project_button** (Boolean)
- **show_task_button** (Boolean)
- **closed_task_count** (Integer)
- **completed_task_percentage** (Float)
- **project_id** (Many2one) → project.project
- **project_account_id** (Many2one) → account.analytic.account





### product.product


- Hereda de:

  - product.product




- No agrega campos




### sale.order.line


- Hereda de:

  - sale.order.line




#### Campos
- **qty_delivered_method** (Selection)
- **project_id** (Many2one) → project.project
- **task_id** (Many2one) → project.task
- **reached_milestones_ids** (One2many) → project.milestone





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | sale.order.line.list.with.create | `sale_project.view_order_line_tree_with_create` | sale.view_order_line_tree |
| form | sale.order.line.view.form.editable | `sale_project.sale_order_line_view_form_editable` | sale.sale_order_line_view_form_readonly |




### product.template


- Hereda de:

  - product.template




#### Campos
- **service_tracking** (Selection)
- **project_id** (Many2one) → project.project
- **project_template_id** (Many2one) → project.project
- **service_policy** (Selection) → _selection_service_policy
- **service_type** (Selection)





### project.task.recurrence


- Hereda de:

  - project.task.recurrence




- No agrega campos




### project.project


- Hereda de:

  - project.project




#### Campos
- **allow_billable** (Boolean) → Billable
- **sale_line_id** (Many2one) → sale.order.line
- **sale_order_id** (Many2one)
- **has_any_so_to_invoice** (Boolean) → Has SO to Invoice
- **sale_order_line_count** (Integer)
- **sale_order_count** (Integer)
- **has_any_so_with_nothing_to_invoice** (Boolean) → Has a SO with an invoice status of No
- **invoice_count** (Integer)
- **vendor_bill_count** (Integer)
- **partner_id** (Many2one)
- **display_sales_stat_buttons** (Boolean)
- **sale_order_state** (Selection)
- **reinvoiced_sale_order_id** (Many2one) → sale.order





### account.move


- Hereda de:

  - account.move




- No agrega campos




### res.config.settings


- Hereda de:

  - res.config.settings




- No agrega campos




### account.move.line


- Hereda de:

  - account.move.line




- No agrega campos




### sale.order.template.line


- Hereda de:

  - sale.order.template.line




- No agrega campos




### project.milestone


- Hereda de:

  - project.milestone




#### Campos
- **allow_billable** (Boolean)
- **project_partner_id** (Many2one)
- **sale_line_id** (Many2one) → sale.order.line
- **quantity_percentage** (Float) → Quantity (%)
- **sale_line_display_name** (Char) → Sale Line Display Name
- **product_uom** (Many2one)
- **product_uom_qty** (Float) → Quantity





### project.task


- Hereda de:

  - project.task




#### Campos
- **sale_order_id** (Many2one) → sale.order
- **sale_line_id** (Many2one) → sale.order.line
- **project_sale_order_id** (Many2one) → sale.order
- **sale_order_state** (Selection)
- **task_to_invoice** (Boolean) → To invoice
- **allow_billable** (Boolean)
- **partner_id** (Many2one)
- **display_sale_order_button** (Boolean)










