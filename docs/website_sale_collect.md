# Módulo: Click & Collect

## Información General
- **Nombre técnico:** website_sale_collect
- **Versión:** 1.0
- **Categoría:** Website/Website
- **Dependencias:** base_geolocalize, payment_custom, website_sale_stock




## Descripción

Allows customers to check in-store stock, pay on site, and pick up their orders at the shop.




## Modelos

### website


- Hereda de:

  - website




#### Campos
- **in_store_dm_id** (Many2one) → delivery.carrier





### delivery.carrier


- Hereda de:

  - delivery.carrier




#### Campos
- **delivery_type** (Selection)
- **warehouse_ids** (Many2many) → stock.warehouse





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | In-store Delivery Carrier Form | `website_sale_collect.delivery_carrier_form` | delivery.view_delivery_carrier_form |




### sale.order


- Hereda de:

  - sale.order




- No agrega campos




### stock.warehouse


- Hereda de:

  - stock.warehouse




#### Campos
- **opening_hours** (Many2one) → resource.calendar





### payment.transaction


- Hereda de:

  - payment.transaction




- No agrega campos




### product.template


- Hereda de:

  - product.template




- No agrega campos




### payment.provider


- Hereda de:

  - payment.provider




#### Campos
- **custom_mode** (Selection)





### res.config.settings


- Hereda de:

  - res.config.settings




- No agrega campos









