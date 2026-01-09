# Módulo: POS - Event

## Información General
- **Nombre técnico:** pos_event
- **Versión:** N/A
- **Categoría:** Technical
- **Dependencias:** point_of_sale, event_product


## Propósito
Link module between Point of Sale and Event





## Modelos

### pos.config


- Hereda de:

  - pos.config




- No agrega campos




### event.question.answer


- Hereda de:


  - event.question.answer

  - pos.load.mixin





- No agrega campos




### pos.order.line


- Hereda de:

  - pos.order.line




#### Campos
- **event_ticket_id** (Many2one) → event.event.ticket
- **event_registration_ids** (One2many) → event.registration





### pos.order


- Hereda de:

  - pos.order




#### Campos
- **attendee_count** (Integer) → Attendee Count





### event.event.ticket


- Hereda de:


  - event.event.ticket

  - pos.load.mixin





- No agrega campos




### event.registration.answer


- Hereda de:


  - event.registration.answer

  - pos.load.mixin





- No agrega campos




### event.event


- Hereda de:


  - event.event

  - pos.load.mixin





#### Campos
- **image_1024** (Image) → PoS Image





### event.registration


- Hereda de:


  - event.registration

  - pos.load.mixin





#### Campos
- **pos_order_id** (Many2one)
- **pos_order_line_id** (Many2one) → pos.order.line





### pos.session


- Hereda de:

  - pos.session




- No agrega campos




### event.question


- Hereda de:


  - event.question

  - pos.load.mixin





- No agrega campos






