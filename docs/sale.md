# Módulo: Sales

## Información General
- **Nombre técnico:** sale
- **Versión:** 1.2
- **Categoría:** Sales/Sales
- **Dependencias:** sales_team, account_payment, utm


## Propósito
Sales internal machinery



## Descripción

This module contains all the common features of Sales Management and eCommerce.
    



## Modelos

### sale.order


- Hereda de:


  - portal.mixin

  - product.catalog.mixin

  - mail.thread

  - mail.activity.mixin

  - utm.mixin





- Campos:

  - **name** (Char)


  - **company_id** (Many2one) → res.company


  - **partner_id** (Many2one) → res.partner


  - **state** (Selection)


  - **locked** (Boolean)


  - **has_archived_products** (Boolean)


  - **client_order_ref** (Char)


  - **create_date** (Datetime)


  - **commitment_date** (Datetime)


  - **date_order** (Datetime)


  - **origin** (Char)


  - **reference** (Char)


  - **require_signature** (Boolean)


  - **require_payment** (Boolean)


  - **prepayment_percent** (Float)


  - **signature** (Image)


  - **signed_by** (Char)


  - **signed_on** (Datetime)


  - **validity_date** (Date)


  - **journal_id** (Many2one) → account.journal


  - **note** (Html)


  - **partner_invoice_id** (Many2one) → res.partner


  - **partner_shipping_id** (Many2one) → res.partner


  - **fiscal_position_id** (Many2one) → account.fiscal.position


  - **payment_term_id** (Many2one) → account.payment.term


  - **pricelist_id** (Many2one) → product.pricelist


  - **currency_id** (Many2one) → res.currency


  - **currency_rate** (Float)


  - **user_id** (Many2one) → res.users


  - **team_id** (Many2one) → crm.team


  - **order_line** (One2many) → sale.order.line


  - **amount_untaxed** (Monetary)


  - **amount_tax** (Monetary)


  - **amount_total** (Monetary)


  - **amount_to_invoice** (Monetary)


  - **amount_invoiced** (Monetary)


  - **invoice_count** (Integer)


  - **invoice_ids** (Many2many) → account.move


  - **invoice_status** (Selection)


  - **transaction_ids** (Many2many) → payment.transaction


  - **authorized_transaction_ids** (Many2many) → payment.transaction


  - **amount_paid** (Float)


  - **campaign_id** (Many2one)


  - **medium_id** (Many2one)


  - **source_id** (Many2one)


  - **tag_ids** (Many2many) → crm.tag


  - **amount_undiscounted** (Float)


  - **country_code** (Char)


  - **company_price_include** (Selection)


  - **duplicated_order_ids** (Many2many) → sale.order


  - **expected_date** (Datetime)


  - **is_expired** (Boolean)


  - **partner_credit_warning** (Text)


  - **tax_calculation_rounding_method** (Selection)


  - **tax_country_id** (Many2one) → res.country


  - **tax_totals** (Binary)


  - **terms_type** (Selection)


  - **type_name** (Char)


  - **show_update_fpos** (Boolean)


  - **has_active_pricelist** (Boolean)


  - **show_update_pricelist** (Boolean)





### account.analytic.line


- Hereda de:

  - account.analytic.line




- Campos:

  - **so_line** (Many2one) → sale.order.line





### account.analytic.applicability


- Hereda de:

  - account.analytic.applicability




- Campos:

  - **business_domain** (Selection)





### product.document


- Hereda de:

  - product.document




- Campos:

  - **attached_on_sale** (Selection)





### payment.transaction


- Hereda de:

  - payment.transaction




- Campos:

  - **sale_order_ids** (Many2many) → sale.order


  - **sale_order_ids_nbr** (Integer)





### product.product


- Hereda de:

  - product.product




- Campos:

  - **sales_count** (Float)


  - **product_catalog_product_is_in_sale_order** (Boolean)





### product.attribute.custom.value


- Hereda de:

  - product.attribute.custom.value




- Campos:

  - **sale_order_line_id** (Many2one) → sale.order.line





### product.packaging


- Hereda de:

  - product.packaging




- Campos:

  - **sales** (Boolean) → Sales





### utm.campaign


- Hereda de:

  - utm.campaign




- Campos:

  - **quotation_count** (Integer) → Quotation Count


  - **invoiced_amount** (Integer)


  - **company_id** (Many2one) → res.company


  - **currency_id** (Many2one) → res.currency





### mail.scheduled.message


- Hereda de:

  - mail.scheduled.message




- No agrega campos



### sale.order.line


- Hereda de:

  - analytic.mixin




- Campos:

  - **order_id** (Many2one) → sale.order


  - **sequence** (Integer)


  - **company_id** (Many2one)


  - **currency_id** (Many2one)


  - **order_partner_id** (Many2one)


  - **salesman_id** (Many2one)


  - **state** (Selection)


  - **tax_country_id** (Many2one)


  - **display_type** (Selection)


  - **is_configurable_product** (Boolean)


  - **is_downpayment** (Boolean)


  - **is_expense** (Boolean)


  - **product_id** (Many2one) → product.product


  - **product_template_id** (Many2one) → product.template


  - **product_uom_category_id** (Many2one)


  - **product_template_attribute_value_ids** (Many2many)


  - **product_custom_attribute_value_ids** (One2many) → product.attribute.custom.value


  - **product_no_variant_attribute_value_ids** (Many2many) → product.template.attribute.value


  - **is_product_archived** (Boolean)


  - **name** (Text)


  - **translated_product_name** (Text)


  - **product_uom_qty** (Float)


  - **product_uom** (Many2one) → uom.uom


  - **linked_line_id** (Many2one) → sale.order.line


  - **linked_line_ids** (One2many) → sale.order.line


  - **virtual_id** (Char)


  - **linked_virtual_id** (Char)


  - **selected_combo_items** (Char)


  - **combo_item_id** (Many2one) → product.combo.item


  - **tax_id** (Many2many) → account.tax


  - **pricelist_item_id** (Many2one) → product.pricelist.item


  - **price_unit** (Float)


  - **technical_price_unit** (Float)


  - **discount** (Float)


  - **price_subtotal** (Monetary)


  - **price_tax** (Float)


  - **price_total** (Monetary)


  - **price_reduce_taxexcl** (Monetary)


  - **price_reduce_taxinc** (Monetary)


  - **product_packaging_id** (Many2one) → product.packaging


  - **product_packaging_qty** (Float)


  - **customer_lead** (Float)


  - **qty_delivered_method** (Selection)


  - **qty_delivered** (Float)


  - **qty_invoiced** (Float)


  - **qty_invoiced_posted** (Float)


  - **qty_to_invoice** (Float)


  - **analytic_line_ids** (One2many) → account.analytic.line


  - **invoice_lines** (Many2many) → account.move.line


  - **invoice_status** (Selection)


  - **untaxed_amount_invoiced** (Monetary)


  - **amount_invoiced** (Monetary)


  - **untaxed_amount_to_invoice** (Monetary)


  - **amount_to_invoice** (Monetary)


  - **product_type** (Selection)


  - **service_tracking** (Selection)


  - **product_updatable** (Boolean)


  - **product_uom_readonly** (Boolean)


  - **tax_calculation_rounding_method** (Selection)


  - **company_price_include** (Selection)





### product.template


- Hereda de:

  - product.template




- Campos:

  - **service_type** (Selection)


  - **sale_line_warn** (Selection)


  - **sale_line_warn_msg** (Text)


  - **expense_policy** (Selection)


  - **visible_expense_policy** (Boolean)


  - **sales_count** (Float)


  - **invoice_policy** (Selection)


  - **optional_product_ids** (Many2many) → product.template





### product.category


- Hereda de:

  - product.category




- Campos:

  - **property_account_downpayment_categ_id** (Many2one) → account.account





### account.move


- Hereda de:


  - account.move

  - utm.mixin





- Campos:

  - **team_id** (Many2one) → crm.team


  - **campaign_id** (Many2one)


  - **medium_id** (Many2one)


  - **source_id** (Many2one)


  - **sale_order_count** (Integer)





### payment.provider


- Hereda de:

  - payment.provider




- Campos:

  - **so_reference_type** (Selection)





### account.move.line


- Hereda de:

  - account.move.line




- Campos:

  - **is_downpayment** (Boolean)


  - **sale_line_ids** (Many2many) → sale.order.line





### ir.config_parameter


- Hereda de:

  - ir.config_parameter




- No agrega campos



### crm.team


- Hereda de:

  - crm.team




- Campos:

  - **invoiced** (Float)


  - **invoiced_target** (Float)


  - **quotations_count** (Integer)


  - **quotations_amount** (Float)


  - **sales_to_invoice_count** (Integer)


  - **sale_order_count** (Integer)





### res.company


- Hereda de:

  - res.company




- Campos:

  - **portal_confirmation_sign** (Boolean)


  - **portal_confirmation_pay** (Boolean)


  - **prepayment_percent** (Float)


  - **quotation_validity_days** (Integer)


  - **sale_discount_product_id** (Many2one) → product.product


  - **sale_onboarding_payment_method** (Selection)





### account.chart.template


- Hereda de:

  - account.chart.template




- No agrega campos



### res.partner


- Hereda de:

  - res.partner




- Campos:

  - **sale_order_count** (Integer)


  - **sale_order_ids** (One2many) → sale.order


  - **sale_warn** (Selection)


  - **sale_warn_msg** (Text) → Message for Sales Order








## Vistas


### sale.order

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| activity | sale.order.activity | `sale.sale_order_view_activity` | - |
| calendar | sale.order.calendar | `sale.view_sale_order_calendar` | - |
| graph | sale.order.graph | `sale.view_sale_order_graph` | - |
| pivot | sale.order.pivot | `sale.view_sale_order_pivot` | - |
| kanban | sale.order.kanban | `sale.view_sale_order_kanban` | - |
| kanban | sale.order.kanban.upload (orders) | `sale.sale_order_kanban_upload` | view_sale_order_kanban |
| list | sale.order.list | `sale.sale_order_tree` | - |
| list | sale.order.list (orders) | `sale.view_order_tree` | sale_order_tree |
| list | sale.order.tree.upload (orders) | `sale.sale_order_list_upload` | view_order_tree |
| list | sale.order.list (quotes) | `sale.view_quotation_tree` | sale_order_tree |
| form | sale.order.form | `sale.view_order_form` | - |
| search | sale.order.list.select | `sale.view_sales_order_filter` | - |



#### Botones (sale.view_order_form)
- **Capture Transaction** (object)
- **Void Transaction** (object)
- **Create Invoice** (action)
- **Create Invoice** (action)
- **Send by Email** (object)
- **Send PRO-FORMA Invoice** (object) - Grupos: `sale.group_proforma_sales`
- **Confirm** (object)
- **Confirm** (object)
- **Send PRO-FORMA Invoice** (object) - Grupos: `sale.group_proforma_sales`
- **Send by Email** (object)
- **Unlock** (object) - Grupos: `sales_team.group_sale_manager`
- **Preview** (object)
- **Cancel** (object)
- **Set to Quotation** (object)
- **Lock** (object) - Grupos: `sales_team.group_sale_manager`
- **action_view_invoice** (object)
- ** Update Prices** (object)
- **Catalog** (object)
- **Catalog** (object)
- **Discount** (object) - Grupos: `sale.group_discount_per_so_line`
- ** Update Taxes** (object)


#### Filtros de búsqueda (sale.view_sales_order_filter)

**Filtros:**
- **My Orders** (`[('user_id', '=', uid)]`)
- **Late Activities** (`[('my_activity_date_deadline', '<', context_today().strftime('%Y-%m-%d'))]`)
- **Today Activities** (`[('my_activity_date_deadline', '=', context_today().strftime('%Y-%m-%d'))]`)
- **Future Activities** (`[('my_activity_date_deadline', '>', context_today().strftime('%Y-%m-%d'))]`)


**Agrupar por:**
- Salesperson
- Customer
- Order Date


### product.document

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| search | product.document.search.sale | `sale.product_document_search` | product.product_document_search |



#### Filtros de búsqueda (sale.product_document_search)

**Filtros:**
- **Quotation** (`[('attached_on_sale', '=', 'quotation')]`)
- **Sales Order** (`[('attached_on_sale', '=', 'sale_order')]`)


### sale.order.line

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | sale.order.line.list | `sale.view_order_line_tree` | - |
| form | sale.order.line.form.readonly | `sale.sale_order_line_view_form_readonly` | - |
| search | sale.order.line.select | `sale.view_sales_order_line_filter` | - |
| kanban | sale.order.line.kanban | `sale.sale_order_line_view_kanban` | - |



#### Filtros de búsqueda (sale.view_sales_order_line_filter)

**Filtros:**
- **To Invoice** (`[('qty_to_invoice', '!=', 0)]`)
- **My Sales Order Lines** (`[('salesman_id','=',uid)]`)


**Agrupar por:**
- Product
- Order
- Salesperson


### sale.advance.payment.inv

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | Invoice Orders | `sale.view_sale_advance_payment_inv` | - |



#### Botones (sale.view_sale_advance_payment_inv)
- **Create Draft** (object)


### sale.order.discount

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | sale.order.line.wizard.form | `sale.sale_order_line_wizard_form` | - |



#### Botones (sale.sale_order_line_wizard_form)
- **Apply** (object)


### sale.order.cancel

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | sale.order.cancel.form | `sale.sale_order_cancel_view_form` | - |



#### Botones (sale.sale_order_cancel_view_form)
- **Send and cancel** (object)
- **Cancel** (object)


### sale.mass.cancel.orders

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | sale.mass.cancel.orders.form | `sale.mass_cancel_orders_view_form` | - |



#### Botones (sale.mass_cancel_orders_view_form)
- **Cancel** (object)


### sale.report

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| pivot | sale.report.pivot | `sale.view_order_product_pivot` | - |
| graph | sale.report.graph | `sale.view_order_product_graph` | - |
| graph | sale.report.graph.pie | `sale.sale_report_graph_pie` | view_order_product_graph |
| graph | sale.report.graph.bar | `sale.sale_report_graph_bar` | view_order_product_graph |
| list | sale.report.view.list | `sale.sale_report_view_tree` | - |
| search | sale.report.search | `sale.view_order_product_search` | - |



#### Filtros de búsqueda (sale.view_order_product_search)

**Filtros:**
- **Date**
- **Quotations** (`[('state','in', ('draft', 'sent'))]`)
- **Sales Orders** (`[('state','not in',('draft', 'cancel', 'sent'))]`)
- **filter_date**
- **Order Date: Last 365 Days** (`[('date', '>=', (datetime.datetime.combine(context_today() + relativedelta(days=-365), datetime.time(0,0,0))).strftime('%Y-%m-%d %H:%M:%S'))]`)
- **To Invoice** (`[('line_invoice_status', '=', 'to invoice')]`)
- **Fully Invoiced** (`[('line_invoice_status', '=', 'invoiced')]`)


**Agrupar por:**
- Salesperson
- Sales Team
- Customer
- Customer Country
- Customer Industry
- Product
- Product Variant
- Product Category
- Status
- Company
- Order Date
- Order Date

