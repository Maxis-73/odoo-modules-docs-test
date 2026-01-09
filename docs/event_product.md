# Módulo: Events Product

## Información General
- **Nombre técnico:** event_product
- **Versión:** 1.0
- **Categoría:** Marketing/Events
- **Dependencias:** event, product, account






## Modelos

### product.product


- Hereda de:

  - product.product




- Campos:

  - **event_ticket_ids** (One2many) → event.event.ticket





### product.template


- Hereda de:

  - product.template




- Campos:

  - **service_tracking** (Selection)





### event.type.ticket


- Hereda de:

  - event.type.ticket




- Campos:

  - **description** (Text)


  - **product_id** (Many2one) → product.product


  - **currency_id** (Many2one)


  - **price** (Float)


  - **price_reduce** (Float)





### event.event.ticket


- Hereda de:

  - event.event.ticket




- Campos:

  - **price_reduce_taxinc** (Float)


  - **price_incl** (Float)





### event.event


- Hereda de:

  - event.event




- Campos:

  - **currency_id** (Many2one) → res.currency







