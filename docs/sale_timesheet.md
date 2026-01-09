# Módulo: Sales Timesheet

## Información General
- **Nombre técnico:** sale_timesheet
- **Versión:** N/A
- **Categoría:** Hidden
- **Dependencias:** sale_project, hr_timesheet


## Propósito
Sell based on timesheets



## Descripción

Allows to sell timesheets in your sales order
=============================================

This module set the right product on all timesheet lines
according to the order/contract you work on. This allows to
have real delivered quantities in sales orders.




## Modelos

### sale.order


- Hereda de:

  - sale.order




#### Campos
- **timesheet_count** (Float)
- **timesheet_encode_uom_id** (Many2one) → uom.uom
- **timesheet_total_duration** (Integer) → Timesheet Total Duration
- **show_hours_recorded_button** (Boolean)





### project.sale.line.employee.map


- Hereda de: Base



#### Campos
- **project_id** (Many2one) → project.project
- **employee_id** (Many2one) → hr.employee
- **existing_employee_ids** (Many2many) → hr.employee
- **sale_line_id** (Many2one) → sale.order.line
- **sale_order_id** (Many2one)
- **company_id** (Many2one) → res.company
- **partner_id** (Many2one)
- **price_unit** (Float) → Unit Price
- **currency_id** (Many2one) → res.currency
- **cost** (Monetary)
- **display_cost** (Monetary)
- **cost_currency_id** (Many2one) → res.currency
- **is_cost_changed** (Boolean) → Is Cost Manually Changed





### account.analytic.line


- Hereda de:

  - account.analytic.line




#### Campos
- **timesheet_invoice_type** (Selection)
- **commercial_partner_id** (Many2one) → res.partner
- **timesheet_invoice_id** (Many2one) → account.move
- **so_line** (Many2one)
- **order_id** (Many2one)
- **is_so_line_edited** (Boolean) → Is Sales Order Item Manually Edited
- **allow_billable** (Boolean)
- **sale_order_state** (Selection)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| pivot | account.analytic.line.pivot.billing.rate | `sale_timesheet.view_hr_timesheet_line_pivot_billing_rate` | - |
| graph | account.analytic.line.graph.employee.per.date | `sale_timesheet.view_hr_timesheet_line_graph_employee_per_date` | - |




### product.product


- Hereda de:

  - product.product




- No agrega campos




### sale.order.line


- Hereda de:

  - sale.order.line




#### Campos
- **qty_delivered_method** (Selection)
- **analytic_line_ids** (One2many)
- **remaining_hours_available** (Boolean)
- **remaining_hours** (Float) → Time Remaining on SO
- **has_displayed_warning_upsell** (Boolean) → Has Displayed Warning Upsell
- **timesheet_ids** (One2many) → account.analytic.line





### product.template


- Hereda de:

  - product.template




#### Campos
- **service_type** (Selection)
- **project_id** (Many2one)
- **project_template_id** (Many2one)
- **service_upsell_threshold** (Float) → Threshold
- **service_upsell_threshold_ratio** (Char)





### account.move.reversal


- Hereda de:

  - account.move.reversal




- No agrega campos




### project.project


- Hereda de:

  - project.project




#### Campos
- **pricing_type** (Selection)
- **sale_line_employee_ids** (One2many) → project.sale.line.employee.map
- **timesheet_product_id** (Many2one) → product.product
- **warning_employee_rate** (Boolean)
- **partner_id** (Many2one)
- **allocated_hours** (Float)
- **billing_type** (Selection)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | project.project.form.inherit | `sale_timesheet.project_project_view_form` | hr_timesheet.project_invoice_form |




### hr.employee


- Hereda de:

  - hr.employee




- No agrega campos




### account.move


- Hereda de:

  - account.move




#### Campos
- **timesheet_ids** (One2many) → account.analytic.line
- **timesheet_count** (Integer) → Number of timesheets
- **timesheet_encode_uom_id** (Many2one) → uom.uom
- **timesheet_total_duration** (Integer) → Timesheet Total Duration





### project.update


- Hereda de:

  - project.update




- No agrega campos




### res.config.settings


- Hereda de:

  - res.config.settings




#### Campos
- **invoice_policy** (Boolean)





### account.move.line


- Hereda de:

  - account.move.line




- No agrega campos




### project.task


- Hereda de:

  - project.task




#### Campos
- **sale_order_id** (Many2one)
- **pricing_type** (Selection)
- **is_project_map_empty** (Boolean) → Is Project map empty
- **has_multi_sol** (Boolean)
- **timesheet_product_id** (Many2one)
- **remaining_hours_so** (Float) → Time Remaining on SO
- **remaining_hours_available** (Boolean)










## Vistas Adicionales


### project.create.invoice

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | project.create.invoice.view.form | `sale_timesheet.project_create_invoice_view_form` | - |



**Botones (sale_timesheet.project_create_invoice_view_form):**
- **Create Invoice** (object)


### timesheets.analysis.report

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| pivot | timesheets.analysis.report.pivot | `sale_timesheet.timesheets_analysis_report_pivot_invoice_type` | - |
| graph | timesheets.analysis.report.graph | `sale_timesheet.timesheets_analysis_report_graph_invoice_type` | - |
| search | timesheets.analysis.report.search | `sale_timesheet.hr_timesheet_report_search_sale_timesheet` | sale_timesheet.timesheet_view_search |



**Filtros de búsqueda (sale_timesheet.hr_timesheet_report_search_sale_timesheet):**


*Agrupar por:*
- Sales Order



