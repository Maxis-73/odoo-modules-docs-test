# Módulo: Events Sales

## Información General
- **Nombre técnico:** event_sale
- **Versión:** 1.3
- **Categoría:** Marketing/Events
- **Dependencias:** event_product, sale_management




## Descripción

Creating registration with sales orders.

This module allows you to automate and connect your registration creation with
your main sale flow and therefore, to enable the invoicing feature of registrations.

It defines a new kind of service products that offers you the possibility to
choose an event category associated with it. When you encode a sales order for
that product, you will be able to choose an existing event of that category and
when you confirm your sales order it will automatically create a registration for
this event.




## Modelos

### sale.order


- Hereda de:

  - sale.order




- Campos:

  - **attendee_count** (Integer) → Attendee Count





### sale.order.line


- Hereda de:

  - sale.order.line




- Campos:

  - **event_id** (Many2one) → event.event


  - **event_ticket_id** (Many2one) → event.event.ticket


  - **registration_ids** (One2many) → event.registration





### product.template


- Hereda de:

  - product.template




- No agrega campos



### event.event.ticket


- Hereda de:

  - event.event.ticket




- No agrega campos



### event.event


- Hereda de:

  - event.event




- Campos:

  - **sale_order_lines_ids** (One2many) → sale.order.line


  - **sale_price_subtotal** (Monetary)





### event.registration


- Hereda de:

  - event.registration




- Campos:

  - **sale_order_id** (Many2one) → sale.order


  - **sale_order_line_id** (Many2one) → sale.order.line


  - **sale_status** (Selection)


  - **state** (Selection)


  - **utm_campaign_id** (Many2one)


  - **utm_source_id** (Many2one)


  - **utm_medium_id** (Many2one)








## Vistas


### event.event.configurator

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | event.configurator.view.form | `event_sale.event_configurator_view_form` | - |



### registration.editor

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | registration.editor.form | `event_sale.view_event_registration_editor_form` | - |



#### Botones (event_sale.view_event_registration_editor_form)
- **Create/Update registrations** (object)


### event.sale.report

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| graph | event.sale.report.view.graph | `event_sale.event_sale_report_view_graph` | - |
| form | event.sale.report.view.form | `event_sale.event_sale_report_view_form` | - |
| pivot | event.sale.report.view.pivot | `event_sale.event_sale_report_view_pivot` | - |
| list | event.sale.report.view.list | `event_sale.event_sale_report_view_tree` | - |
| search | event.sale.report.view.search | `event_sale.event_sale_report_view_search` | - |



#### Filtros de búsqueda (event_sale.event_sale_report_view_search)

**Filtros:**
- **Non-free tickets** (`[('event_ticket_price', '!=', 0)]`)
- **Free** (`[('sale_status', '=', 'free')]`)
- **Pending payment** (`[('sale_status', '=', 'to_pay')]`)
- **Sold** (`[('sale_status', '=', 'sold')]`)
- **Registration Date**
- **Upcoming/Running** (`[('event_date_end', '>=', datetime.datetime.combine(context_today(), datetime.time(0,0,0)))]`)
- **Past Events** (`[('event_date_end', '<', datetime.datetime.combine(context_today(), datetime.time(0,0,0)))]`)
- **Event Start Date**
- **Event End Date**


**Agrupar por:**
- Event Type
- Event
- Product
- Ticket
- Registration Status
- Sale Order Status
- Customer

