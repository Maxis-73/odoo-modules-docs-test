# Módulo: Events Booths Sales

## Información General
- **Nombre técnico:** event_booth_sale
- **Versión:** 1.2
- **Categoría:** Marketing/Events
- **Dependencias:** event_booth, event_sale


## Propósito
Manage event booths sale



## Descripción

Sell your event booths and track payments on sale orders.
    



## Modelos

### sale.order


- Hereda de:

  - sale.order




#### Campos
- **event_booth_ids** (One2many) → event.booth
- **event_booth_count** (Integer)





### event.booth


- Hereda de:

  - event.booth




#### Campos
- **event_booth_registration_ids** (One2many) → event.booth.registration
- **sale_order_line_registration_ids** (Many2many) → sale.order.line
- **sale_order_line_id** (Many2one) → sale.order.line
- **sale_order_id** (Many2one)
- **is_paid** (Boolean) → Is Paid





### event.booth.registration


- Hereda de: Base



#### Campos
- **sale_order_line_id** (Many2one) → sale.order.line
- **event_booth_id** (Many2one) → event.booth
- **partner_id** (Many2one) → res.partner
- **contact_name** (Char)
- **contact_email** (Char)
- **contact_phone** (Char)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | event.booth.registration.view.form | `event_booth_sale.event_booth_registration_view_form` | - |
| list | event.booth.registration.view.list | `event_booth_sale.event_booth_registration_view_tree` | - |




### product.product


- Hereda de:

  - product.product




- No agrega campos




### event.type.booth


- Hereda de:

  - event.type.booth




#### Campos
- **product_id** (Many2one)
- **price** (Float)
- **currency_id** (Many2one)





### sale.order.line


- Hereda de:

  - sale.order.line




#### Campos
- **event_booth_category_id** (Many2one) → event.booth.category
- **event_booth_pending_ids** (Many2many) → event.booth
- **event_booth_registration_ids** (One2many) → event.booth.registration
- **event_booth_ids** (One2many) → event.booth
- **is_event_booth** (Boolean)





### product.template


- Hereda de:

  - product.template




#### Campos
- **service_tracking** (Selection)





### account.move


- Hereda de:

  - account.move




- No agrega campos




### event.booth.category


- Hereda de:

  - event.booth.category




#### Campos
- **product_id** (Many2one) → product.product
- **price** (Float)
- **price_incl** (Float)
- **currency_id** (Many2one)
- **price_reduce** (Float)
- **price_reduce_taxinc** (Float)
- **image_1920** (Image)










## Vistas Adicionales


### event.booth.configurator

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | event.booth.configurator.view.form | `event_booth_sale.event_booth_configurator_view_form` | - |




