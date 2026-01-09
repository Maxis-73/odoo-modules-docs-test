# Módulo: Gelato

## Información General
- **Nombre técnico:** sale_gelato
- **Versión:** N/A
- **Categoría:** Sales/Sales
- **Dependencias:** sale_management, delivery


## Propósito
Place orders through Gelato's print-on-demand service





## Modelos

### delivery.carrier


- Hereda de:

  - delivery.carrier




- Campos:

  - **delivery_type** (Selection)


  - **gelato_shipping_service_type** (Selection)





### sale.order


- Hereda de:

  - sale.order




- No agrega campos



### product.document


- Hereda de:

  - product.document




- Campos:

  - **is_gelato** (Boolean)





### product.product


- Hereda de:

  - product.product




- Campos:

  - **gelato_product_uid** (Char)





### sale.order.line


- Hereda de:

  - sale.order.line




- No agrega campos



### product.template


- Hereda de:

  - product.template




- Campos:

  - **gelato_template_ref** (Char)


  - **gelato_product_uid** (Char)


  - **gelato_image_ids** (One2many) → product.document


  - **gelato_missing_images** (Boolean)





### res.company


- Hereda de:

  - res.company




- Campos:

  - **gelato_api_key** (Char)


  - **gelato_webhook_secret** (Char)





### res.partner


- Hereda de:

  - res.partner




- No agrega campos






## Vistas


### product.document

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | Product Document Form | `sale_gelato.product_document_form` | - |


