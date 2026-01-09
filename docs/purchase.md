# Módulo: Purchase

## Información General
- **Nombre técnico:** purchase
- **Versión:** 1.2
- **Categoría:** Inventory/Purchase
- **Dependencias:** account


## Propósito
Purchase orders, tenders and agreements





## Modelos

### purchase.order


- Hereda de:


  - portal.mixin

  - product.catalog.mixin

  - mail.thread

  - mail.activity.mixin





- Campos:

  - **name** (Char) → Order Reference


  - **priority** (Selection)


  - **origin** (Char) → Source Document


  - **partner_ref** (Char) → Vendor Reference


  - **date_order** (Datetime) → Order Deadline


  - **date_approve** (Datetime) → Confirmation Date


  - **partner_id** (Many2one) → res.partner


  - **dest_address_id** (Many2one) → res.partner


  - **currency_id** (Many2one) → res.currency


  - **state** (Selection)


  - **order_line** (One2many) → purchase.order.line


  - **notes** (Html) → Terms and Conditions


  - **partner_bill_count** (Integer)


  - **invoice_count** (Integer)


  - **invoice_ids** (Many2many) → account.move


  - **invoice_status** (Selection)


  - **date_planned** (Datetime)


  - **date_calendar_start** (Datetime)


  - **amount_untaxed** (Monetary)


  - **tax_totals** (Binary)


  - **amount_tax** (Monetary)


  - **amount_total** (Monetary)


  - **amount_total_cc** (Monetary)


  - **fiscal_position_id** (Many2one) → account.fiscal.position


  - **tax_country_id** (Many2one) → res.country


  - **tax_calculation_rounding_method** (Selection)


  - **payment_term_id** (Many2one) → account.payment.term


  - **incoterm_id** (Many2one) → account.incoterms


  - **product_id** (Many2one) → product.product


  - **user_id** (Many2one) → res.users


  - **company_id** (Many2one) → res.company


  - **company_currency_id** (Many2one)


  - **country_code** (Char)


  - **company_price_include** (Selection)


  - **currency_rate** (Float)


  - **mail_reminder_confirmed** (Boolean) → Reminder Confirmed


  - **mail_reception_confirmed** (Boolean) → Reception Confirmed


  - **mail_reception_declined** (Boolean) → Reception Declined


  - **receipt_reminder_email** (Boolean) → Receipt Reminder Email


  - **reminder_date_before_receipt** (Integer) → Days Before Receipt





### account.analytic.applicability


- Hereda de:

  - account.analytic.applicability




- Campos:

  - **business_domain** (Selection)





### ir.actions.report


- Hereda de:

  - ir.actions.report




- No agrega campos



### account.move


- Hereda de:

  - account.move




- Campos:

  - **purchase_vendor_bill_id** (Many2one) → purchase.bill.union


  - **purchase_id** (Many2one) → purchase.order


  - **purchase_order_count** (Integer)


  - **purchase_order_name** (Char)


  - **is_purchase_matched** (Boolean)





### account.move.line


- Hereda de:

  - account.move.line




- Campos:

  - **is_downpayment** (Boolean)


  - **purchase_line_id** (Many2one) → purchase.order.line


  - **purchase_order_id** (Many2one) → purchase.order





### product.template


- Hereda de:

  - product.template




- Campos:

  - **purchased_product_qty** (Float)


  - **purchase_method** (Selection)


  - **purchase_line_warn** (Selection)


  - **purchase_line_warn_msg** (Text) → Message for Purchase Order Line





### product.product


- Hereda de:

  - product.product




- Campos:

  - **purchased_product_qty** (Float)


  - **is_in_purchase_order** (Boolean)





### product.supplierinfo


- Hereda de:

  - product.supplierinfo




- No agrega campos



### product.packaging


- Hereda de:

  - product.packaging




- Campos:

  - **purchase** (Boolean) → Purchase





### account.analytic.account


- Hereda de:

  - account.analytic.account




- Campos:

  - **purchase_order_count** (Integer) → Purchase Order Count





### account.tax


- Hereda de:

  - account.tax




- No agrega campos



### res.config.settings


- Hereda de:

  - res.config.settings




- Campos:

  - **lock_confirmed_po** (Boolean) → Lock Confirmed Orders


  - **po_lock** (Selection)


  - **po_order_approval** (Boolean) → Purchase Order Approval


  - **po_double_validation** (Selection)


  - **po_double_validation_amount** (Monetary)


  - **company_currency_id** (Many2one) → res.currency


  - **default_purchase_method** (Selection)


  - **group_warning_purchase** (Boolean) → Purchase Warnings


  - **module_account_3way_match** (Boolean) → 3-way matching: purchases, receptions and bills


  - **module_purchase_requisition** (Boolean) → Purchase Agreements


  - **module_purchase_product_matrix** (Boolean) → Purchase Grid Entry


  - **po_lead** (Float)


  - **use_po_lead** (Boolean)


  - **group_send_reminder** (Boolean) → Receipt Reminder





### res.company


- Hereda de:

  - res.company




- Campos:

  - **po_lead** (Float)


  - **po_lock** (Selection)


  - **po_double_validation** (Selection)


  - **po_double_validation_amount** (Monetary)





### purchase.order.line


- Hereda de:

  - analytic.mixin




- Campos:

  - **name** (Text)


  - **sequence** (Integer)


  - **product_qty** (Float)


  - **product_uom_qty** (Float)


  - **date_planned** (Datetime)


  - **discount** (Float)


  - **taxes_id** (Many2many) → account.tax


  - **product_uom** (Many2one) → uom.uom


  - **product_uom_category_id** (Many2one)


  - **product_id** (Many2one) → product.product


  - **product_type** (Selection)


  - **price_unit** (Float)


  - **price_unit_discounted** (Float) → Unit Price (Discounted)


  - **price_subtotal** (Monetary)


  - **price_total** (Monetary)


  - **price_tax** (Float)


  - **order_id** (Many2one) → purchase.order


  - **company_id** (Many2one) → res.company


  - **state** (Selection)


  - **invoice_lines** (One2many) → account.move.line


  - **qty_invoiced** (Float)


  - **qty_received_method** (Selection)


  - **qty_received** (Float) → Received Qty


  - **qty_received_manual** (Float) → Manual Received Qty


  - **qty_to_invoice** (Float)


  - **partner_id** (Many2one) → res.partner


  - **currency_id** (Many2one)


  - **date_order** (Datetime)


  - **date_approve** (Datetime)


  - **product_packaging_id** (Many2one) → product.packaging


  - **product_packaging_qty** (Float) → Packaging Quantity


  - **tax_calculation_rounding_method** (Selection)


  - **display_type** (Selection)


  - **is_downpayment** (Boolean)


  - **product_template_attribute_value_ids** (Many2many)


  - **product_no_variant_attribute_value_ids** (Many2many) → product.template.attribute.value





### purchase.bill.line.match


- Hereda de: Base



- Campos:

  - **pol_id** (Many2one) → purchase.order.line


  - **aml_id** (Many2one) → account.move.line


  - **company_id** (Many2one) → res.company


  - **partner_id** (Many2one) → res.partner


  - **product_id** (Many2one) → product.product


  - **line_qty** (Float)


  - **line_uom_id** (Many2one) → uom.uom


  - **qty_invoiced** (Float)


  - **purchase_order_id** (Many2one) → purchase.order


  - **account_move_id** (Many2one) → account.move


  - **line_amount_untaxed** (Monetary)


  - **currency_id** (Many2one) → res.currency


  - **state** (Char)


  - **product_uom_id** (Many2one) → uom.uom


  - **product_uom_qty** (Float)


  - **product_uom_price** (Float)


  - **billed_amount_untaxed** (Monetary)


  - **purchase_amount_untaxed** (Monetary)


  - **reference** (Char)





### res.partner


- Hereda de:

  - res.partner




- Campos:

  - **property_purchase_currency_id** (Many2one) → res.currency


  - **purchase_order_count** (Integer)


  - **purchase_warn** (Selection)


  - **purchase_warn_msg** (Text) → Message for Purchase Order


  - **receipt_reminder_email** (Boolean) → Receipt Reminder


  - **reminder_date_before_receipt** (Integer) → Days Before Receipt


  - **buyer_id** (Many2one) → res.users








## Vistas


### purchase.bill.line.match

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | purchase.bill.line.match.list | `purchase.purchase_bill_line_match_tree` | - |



### purchase.order

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| calendar | purchase.order.calendar | `purchase.purchase_order_calendar` | - |
| pivot | purchase.order.pivot | `purchase.purchase_order_pivot` | - |
| graph | purchase.order.graph | `purchase.purchase_order_graph` | - |
| form | purchase.order.form | `purchase.purchase_order_form` | - |
| search | request.quotation.select | `purchase.view_purchase_order_filter` | - |
| search | purchase.order.select | `purchase.purchase_order_view_search` | - |
| kanban | purchase.order.kanban | `purchase.view_purchase_order_kanban` | - |
| list | purchase.order.list | `purchase.purchase_order_tree` | - |
| list | purchase.order.inherit.purchase.order.list | `purchase.purchase_order_kpis_tree` | - |
| list | purchase.order.view.list | `purchase.purchase_order_view_tree` | - |
| activity | purchase.order.activity | `purchase.purchase_order_view_activity` | - |



#### Botones (purchase.purchase_order_form)
- **Send by Email** (object)
- **Print RFQ** (object) - Grupos: `base.group_user`
- **Confirm Order** (object)
- **Approve Order** (object) - Grupos: `purchase.group_purchase_manager`
- **Create Bill** (object)
- **Re-Send by Email** (object)
- **Print RFQ** (object) - Grupos: `base.group_user`
- **Confirm Order** (object)
- **Send PO by Email** (object)
- **Confirm Receipt Date** (object) - Grupos: `base.group_no_one`
- **Create Bill** (object)
- **Set to Draft** (object)
- **Cancel** (object)
- **Lock** (object)
- **Unlock** (object) - Grupos: `purchase.group_purchase_manager`
- **action_bill_matching** (object) - Grupos: `account.group_account_invoice`
- **action_view_invoice** (object)
- **Catalog** (object)
- **action_purchase_history** (object)


#### Filtros de búsqueda (purchase.view_purchase_order_filter)

**Filtros:**
- **My Purchases** (`[('user_id', '=', uid)]`)
- **Starred** (`[('priority', '=', '1')]`)
- **RFQs** (`[('state', 'in', ('draft', 'sent', 'to approve'))]`)
- **Not Acknowledged** (`[('mail_reception_confirmed', '=', False), ('mail_reception_declined', '=', False), ('state', 'in', ('draft', 'sent'))]`)
- **Purchase Orders** (`[('state', 'in', ('purchase', 'done'))]`)
- **To Approve** (`[('state', '=', 'to approve')]`)
- **Order Date**
- **Draft RFQs** (`[('state', '=', 'draft')]`)
- **Waiting RFQs** (`[('state', '=', 'sent'), ('date_order', '>=', datetime.datetime.now())]`)
- **Late RFQs** (`[('state', 'in', ['draft', 'sent', 'to approve']),('date_order', '<', datetime.datetime.now())]`)
- **Late Activities** (`[('my_activity_date_deadline', '<', context_today().strftime('%Y-%m-%d'))]`)
- **Today Activities** (`[('my_activity_date_deadline', '=', context_today().strftime('%Y-%m-%d'))]`)
- **Future Activities** (`[('my_activity_date_deadline', '>', context_today().strftime('%Y-%m-%d'))]`)
- **Warnings** (`[('activity_exception_decoration', '!=', False)]`)


**Agrupar por:**
- Vendor
- Buyer
- Order Date


#### Filtros de búsqueda (purchase.purchase_order_view_search)

**Filtros:**
- **My Orders** (`[('user_id', '=', uid)]`)
- **Starred** (`[('priority', '=', '1')]`)
- **Waiting Bills** (`[('invoice_status', '=', 'to invoice')]`)
- **Bills Received** (`[('invoice_status', '=', 'invoiced')]`)
- **Order Date**
- **Late Activities** (`[('my_activity_date_deadline', '<', context_today().strftime('%Y-%m-%d'))]`)
- **Today Activities** (`[('my_activity_date_deadline', '=', context_today().strftime('%Y-%m-%d'))]`)
- **Future Activities** (`[('my_activity_date_deadline', '>', context_today().strftime('%Y-%m-%d'))]`)
- **Warnings** (`[('activity_exception_decoration', '!=', False)]`)


**Agrupar por:**
- Vendor
- Buyer
- Order Date


### purchase.order.line

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | purchase.order.line.list | `purchase.purchase_order_line_tree` | - |
| form | purchase.order.line.form2 | `purchase.purchase_order_line_form2` | - |
| search | purchase.order.line.search | `purchase.purchase_order_line_search` | - |
| list | purchase.history.list | `purchase.purchase_history_tree` | - |
| pivot | purchase.history.pivot | `purchase.purchase_history_pivot` | - |
| graph | purchase.history.graph | `purchase.purchase_history_graph` | - |



#### Filtros de búsqueda (purchase.purchase_order_line_search)

**Filtros:**
- **Hide cancelled lines** (`[('state', '!=', 'cancel')]`)
- **Status** (`[('state', '=', 'purchase')]`)
- **filter_date_order**
- **Order Date: Last 365 Days** (`[                             ('date_order', '>', ((context_today() - relativedelta(years=1)).strftime('%Y-%m-%d')))                         ]`)


**Agrupar por:**
- Vendor
- Product
- Order Reference
- Order Date


### bill.to.po.wizard

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | bill.to.po.wizard.form | `purchase.bill_to_po_wizard_form` | - |



#### Botones (purchase.bill_to_po_wizard_form)
- **Add Products** (object)
- **Add Down Payment** (object)


### purchase.report

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| pivot | product.month.pivot | `purchase.view_purchase_order_pivot` | - |
| graph | product.month.graph | `purchase.view_purchase_order_graph` | - |
| list | purchase.report.view.list | `purchase.purchase_report_view_tree` | - |
| search | report.purchase.order.search | `purchase.view_purchase_order_search` | - |



#### Filtros de búsqueda (purchase.view_purchase_order_search)

**Filtros:**
- **Requests for Quotation** (`[('state','in',('draft','sent'))]`)
- **Purchase Orders** (`[('state','!=','draft'), ('state','!=','sent'), ('state','!=','cancel')]`)
- **Confirmation Date Last Year** (`[('date_approve', '>=', ((context_today()-relativedelta(years=1)).strftime('%Y-%m-%d')))]`)
- **filter_date_order**
- **filter_date_approve**


**Agrupar por:**
- Vendor
- Vendor Country
- Buyer
- Product
- Product Category
- Status
- Company
- Order Date
- Confirmation Date


### purchase.bill.union

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| search | purchase.bill.union.select | `purchase.view_purchase_bill_union_filter` | - |
| list | purchase.bill.union.list | `purchase.view_purchase_bill_union_tree` | - |



#### Filtros de búsqueda (purchase.view_purchase_bill_union_filter)

**Filtros:**
- **Purchase Orders** (`[('purchase_order_id', '!=', False)]`)
- **Vendor Bills** (`[('vendor_bill_id', '!=', False)]`)

