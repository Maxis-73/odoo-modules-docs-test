# Módulo: Purchase Agreements

## Información General
- **Nombre técnico:** purchase_requisition
- **Versión:** 0.1
- **Categoría:** Inventory/Purchase
- **Dependencias:** purchase




## Descripción

This module allows you to manage your Purchase Agreements.

Manage calls for tenders and blanket orders. Calls for tenders are used to get
competing offers from different vendors and select the best ones. Blanket orders
are agreements you have with vendors to benefit from a predetermined pricing.




## Modelos

### purchase.order.group


- Hereda de: Base



- Campos:

  - **order_ids** (One2many) → purchase.order





### purchase.order


- Hereda de:

  - purchase.order




- Campos:

  - **requisition_id** (Many2one) → purchase.requisition


  - **requisition_type** (Selection)


  - **purchase_group_id** (Many2one) → purchase.order.group


  - **alternative_po_ids** (One2many) → purchase.order


  - **has_alternatives** (Boolean) → Has Alternatives





### purchase.order.line


- Hereda de:

  - purchase.order.line




- Campos:

  - **price_total_cc** (Monetary)


  - **company_currency_id** (Many2one)





### product.supplierinfo


- Hereda de:

  - product.supplierinfo




- Campos:

  - **purchase_requisition_id** (Many2one) → purchase.requisition


  - **purchase_requisition_line_id** (Many2one) → purchase.requisition.line





### product.product


- Hereda de:

  - product.product




- No agrega campos



### res.config.settings


- Hereda de:

  - res.config.settings




- Campos:

  - **group_purchase_alternatives** (Boolean) → Purchase Alternatives





### purchase.requisition


- Hereda de:


  - mail.thread

  - mail.activity.mixin





- Campos:

  - **name** (Char)


  - **active** (Boolean) → Active


  - **reference** (Char)


  - **order_count** (Integer)


  - **vendor_id** (Many2one) → res.partner


  - **requisition_type** (Selection)


  - **date_start** (Date)


  - **date_end** (Date)


  - **user_id** (Many2one) → res.users


  - **description** (Html)


  - **company_id** (Many2one) → res.company


  - **purchase_ids** (One2many) → purchase.order


  - **line_ids** (One2many) → purchase.requisition.line


  - **product_id** (Many2one) → product.product


  - **state** (Selection)


  - **currency_id** (Many2one) → res.currency





### purchase.requisition.line


- Hereda de:

  - analytic.mixin




- Campos:

  - **product_id** (Many2one) → product.product


  - **product_uom_id** (Many2one) → uom.uom


  - **product_uom_category_id** (Many2one)


  - **product_qty** (Float)


  - **product_description_variants** (Char) → Description


  - **price_unit** (Float)


  - **qty_ordered** (Float)


  - **requisition_id** (Many2one) → purchase.requisition


  - **company_id** (Many2one) → res.company


  - **supplier_info_ids** (One2many) → product.supplierinfo








## Vistas


### purchase.order

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | purchase.order.form.inherit | `purchase_requisition.purchase_order_form_inherit` | purchase.purchase_order_form |



### purchase.order.line

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | purchase.order.line.compare.list | `purchase_requisition.purchase_order_line_compare_tree` | - |



### purchase.requisition

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | purchase.requisition.form | `purchase_requisition.view_purchase_requisition_form` | - |
| list | purchase.requisition.list | `purchase_requisition.view_purchase_requisition_tree` | - |
| kanban | purchase.requisition.kanban | `purchase_requisition.view_purchase_requisition_kanban` | - |
| search | purchase.requisition.list.select | `purchase_requisition.view_purchase_requisition_filter` | - |



#### Botones (purchase_requisition.view_purchase_requisition_form)
- **New Quotation** (action)
- **Confirm** (object)
- **Close** (object)
- **Reset to Draft** (object)
- **Cancel** (object)
- **%(action_purchase_requisition_list)d** (action)


#### Filtros de búsqueda (purchase_requisition.view_purchase_requisition_filter)

**Filtros:**
- **My Agreements** (`[('user_id', '=', uid)]`)
- **Blanket Orders** (`[('requisition_type', '=', 'blanket_order')]`)
- **Purchase Templates** (`[('requisition_type', '=', 'purchase_template')]`)
- **Draft** (`[('state', '=', 'draft')]`)
- **Done** (`[('state', '=', 'done')]`)
- **Archived** (`[('active','=',False)]`)
- **Late Activities** (`[('my_activity_date_deadline', '<', context_today().strftime('%Y-%m-%d'))]`)
- **Today Activities** (`[('my_activity_date_deadline', '=', context_today().strftime('%Y-%m-%d'))]`)
- **Future Activities** (`[('my_activity_date_deadline', '>', context_today().strftime('%Y-%m-%d'))]`)


**Agrupar por:**
- Purchase Representative
- Status
- Ordering Date


### purchase.requisition.create.alternative

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | Create Alternative | `purchase_requisition.purchase_requisition_create_alternative_form` | - |



#### Botones (purchase_requisition.purchase_requisition_create_alternative_form)
- **Create Alternative** (object)


### purchase.requisition.alternative.warning

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | Alternative Warning | `purchase_requisition.purchase_requisition_alternative_warning_form` | - |



#### Botones (purchase_requisition.purchase_requisition_alternative_warning_form)
- **Cancel Alternatives** (object)
- **Keep Alternatives** (object)

