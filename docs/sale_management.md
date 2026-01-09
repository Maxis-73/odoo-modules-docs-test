# Módulo: Sales

## Información General
- **Nombre técnico:** sale_management
- **Versión:** 1.0
- **Categoría:** Sales/Sales
- **Dependencias:** sale, digest


## Propósito
From quotations to invoices



## Descripción

Manage sales quotations and orders

This application allows you to manage your sales goals in an effective and efficient manner by keeping track of all sales orders and history.

It handles the full sales workflow:

* **Quotation** -> **Sales order** -> **Invoice**

Preferences (only with Warehouse Management installed)
------------------------------------------------------

If you also installed the Warehouse Management, you can deal with the following preferences:

* Shipping: Choice of delivery at once or partial delivery
* Invoicing: choose how invoices will be paid
* Incoterms: International Commercial terms


With this module you can personnalize the sales order and invoice report with
categories, subtotals or page-breaks.

The Dashboard for the Sales Manager will include
------------------------------------------------
* My Quotations
* Monthly Turnover (Graph)
    



## Modelos

### sale.order.template.option


- Hereda de: Base



- Campos:

  - **sale_order_template_id** (Many2one) → sale.order.template


  - **company_id** (Many2one)


  - **product_id** (Many2one) → product.product


  - **name** (Text)


  - **uom_id** (Many2one) → uom.uom


  - **product_uom_category_id** (Many2one)


  - **quantity** (Float)





### sale.order


- Hereda de:

  - sale.order




- Campos:

  - **sale_order_template_id** (Many2one) → sale.order.template


  - **sale_order_option_ids** (One2many) → sale.order.option





### sale.order.line


- Hereda de:

  - sale.order.line




- Campos:

  - **sale_order_option_ids** (One2many) → sale.order.option





### digest.digest


- Hereda de:

  - digest.digest




- Campos:

  - **kpi_all_sale_total** (Boolean) → All Sales


  - **kpi_all_sale_total_value** (Monetary)





### res.config.settings


- Hereda de:

  - res.config.settings




- Campos:

  - **group_sale_order_template** (Boolean) → Quotation Templates


  - **company_so_template_id** (Many2one)





### sale.order.option


- Hereda de: Base



- Campos:

  - **order_id** (Many2one) → sale.order


  - **product_id** (Many2one) → product.product


  - **line_id** (Many2one) → sale.order.line


  - **sequence** (Integer)


  - **name** (Text)


  - **quantity** (Float)


  - **uom_id** (Many2one) → uom.uom


  - **product_uom_category_id** (Many2one)


  - **price_unit** (Float)


  - **discount** (Float)


  - **is_present** (Boolean)





### res.company


- Hereda de:

  - res.company




- Campos:

  - **sale_order_template_id** (Many2one) → sale.order.template





### sale.order.template.line


- Hereda de: Base



- Campos:

  - **sale_order_template_id** (Many2one) → sale.order.template


  - **sequence** (Integer)


  - **company_id** (Many2one)


  - **product_id** (Many2one) → product.product


  - **name** (Text)


  - **product_uom_id** (Many2one) → uom.uom


  - **product_uom_category_id** (Many2one)


  - **product_uom_qty** (Float)


  - **display_type** (Selection)





### sale.order.template


- Hereda de: Base



- Campos:

  - **active** (Boolean)


  - **company_id** (Many2one) → res.company


  - **name** (Char)


  - **note** (Html)


  - **sequence** (Integer)


  - **mail_template_id** (Many2one) → mail.template


  - **number_of_days** (Integer)


  - **require_signature** (Boolean)


  - **require_payment** (Boolean)


  - **prepayment_percent** (Float)


  - **sale_order_template_line_ids** (One2many) → sale.order.template.line


  - **sale_order_template_option_ids** (One2many) → sale.order.template.option


  - **journal_id** (Many2one) → account.journal








## Vistas


### sale.order

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | sale.order.form.inherit.sale_management | `sale_management.sale_order_form_quote` | sale.view_order_form |



#### Botones (sale_management.sale_order_form_quote)
- **button_add_to_order** (object)
- **button_add_to_order** (object)


### sale.order.template

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| search | sale.order.template.search | `sale_management.sale_order_template_view_search` | - |
| form | sale.order.template.form | `sale_management.sale_order_template_view_form` | - |
| list | sale.order.template.list | `sale_management.sale_order_template_view_tree` | - |



#### Filtros de búsqueda (sale_management.sale_order_template_view_search)

**Filtros:**
- **Archived** (`[('active','=', False)]`)


**Agrupar por:**
- Company

