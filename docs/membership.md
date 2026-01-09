# Módulo: Members

## Información General
- **Nombre técnico:** membership
- **Versión:** 1.0
- **Categoría:** Sales/Sales
- **Dependencias:** account




## Descripción

This module allows you to manage all operations for managing memberships.
=========================================================================

It supports different kind of members:
--------------------------------------
    * Free member
    * Associated member (e.g.: a group subscribes to a membership for all subsidiaries)
    * Paid members
    * Special member prices

It is integrated with sales and accounting to allow you to automatically
invoice and send propositions for membership renewal.
    



## Modelos

### membership.membership_line


- Hereda de: Base



#### Campos
- **partner** (Many2one) → res.partner
- **membership_id** (Many2one) → product.product
- **date_from** (Date)
- **date_to** (Date)
- **date_cancel** (Date)
- **date** (Date)
- **member_price** (Float)
- **account_invoice_line** (Many2one) → account.move.line
- **account_invoice_id** (Many2one) → account.move
- **company_id** (Many2one) → res.company
- **state** (Selection)





### account.move


- Hereda de:

  - account.move




- No agrega campos




### account.move.line


- Hereda de:

  - account.move.line




- No agrega campos




### res.partner


- Hereda de:

  - res.partner




#### Campos
- **associate_member** (Many2one) → res.partner
- **member_lines** (One2many) → membership.membership_line
- **free_member** (Boolean)
- **membership_amount** (Float)
- **membership_state** (Selection)
- **membership_start** (Date)
- **membership_stop** (Date)
- **membership_cancel** (Date)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | Members | `membership.membership_members_tree` | - |
| search | res.partner.select | `membership.view_res_partner_member_filter` | - |
| form | res.partner.form.inherit | `membership.view_partner_form` | base.view_partner_form |



**Filtros de búsqueda (membership.view_res_partner_member_filter):**

- **Customers** (`[('customer_rank' ,'>', 0)]`)
- **Vendors** (`[('supplier_rank', '>', 0)]`)
- **Members** (`[('membership_state', 'in', ['invoiced', 'paid', 'free'])]`)
- **Start Date**
- **End Date**


*Agrupar por:*
- Salesperson
- Associate Member
- Membership State
- Start Date
- End Date


**Botones (membership.view_partner_form):**
- **Buy Membership** (action)



### product.template


- Hereda de:

  - product.template




#### Campos
- **membership** (Boolean)
- **membership_date_from** (Date)
- **membership_date_to** (Date)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| search | membership.product.search.form | `membership.membership_product_search_form_view` | - |
| list | Membership products | `membership.membership_products_tree` | - |
| kanban | product.template.kanban | `membership.membership_products_kanban` | - |
| form | Membership Products | `membership.membership_products_form` | - |



**Filtros de búsqueda (membership.membership_product_search_form_view):**

- **Inactive** (`[('active','=',False)]`)


*Agrupar por:*
- Category
- Start Date








## Vistas Adicionales


### membership.invoice

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | membership.invoice.view.form | `membership.view_membership_invoice_view` | - |



**Botones (membership.view_membership_invoice_view):**
- **Invoice Membership** (object)


### report.membership

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| search | report.membership.search | `membership.view_report_membership_search` | - |
| pivot | report.membership.pivot | `membership.view_report_membership_pivot` | - |
| graph | report.membership.graph1 | `membership.view_report_membership_graph1` | - |
| list | report.membership.view.list | `membership.report_membership_view_tree` | - |



**Filtros de búsqueda (membership.view_report_membership_search):**

- **Forecast**
- **Revenue Done**
- **filter_start_date**


*Agrupar por:*
- Salesperson
- Associated Partner
- Membership Product
- Current Membership State
- Company
- Month



