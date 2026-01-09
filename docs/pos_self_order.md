# Módulo: POS Self Order

## Información General
- **Nombre técnico:** pos_self_order
- **Versión:** 1.0
- **Categoría:** Sales/Point Of Sale
- **Dependencias:** pos_restaurant, http_routing


## Propósito
Addon for the POS App that allows customers to view the menu on their smartphone.





## Modelos

### restaurant.table


- Hereda de:

  - restaurant.table




- Campos:

  - **identifier** (Char) → Security Token





### restaurant.floor


- Hereda de:

  - restaurant.floor




- No agrega campos



### pos.config


- Hereda de:

  - pos.config




- Campos:

  - **status** (Selection)


  - **self_ordering_url** (Char)


  - **self_ordering_takeaway** (Boolean) → Self Takeaway


  - **self_ordering_mode** (Selection)


  - **self_ordering_service_mode** (Selection)


  - **self_ordering_default_language_id** (Many2one) → res.lang


  - **self_ordering_available_language_ids** (Many2many) → res.lang


  - **self_ordering_image_home_ids** (Many2many) → ir.attachment


  - **self_ordering_default_user_id** (Many2one) → res.users


  - **self_ordering_pay_after** (Selection)


  - **self_ordering_image_brand** (Image)


  - **self_ordering_image_brand_name** (Char)


  - **has_paper** (Boolean) → Has paper





### pos.category


- Hereda de:

  - pos.category




- Campos:

  - **hour_until** (Float)


  - **hour_after** (Float)





### product.template


- Hereda de:

  - product.template




- Campos:

  - **self_order_available** (Boolean)





### product.product


- Hereda de:

  - product.product




- No agrega campos



### pos.payment.method


- Hereda de:

  - pos.payment.method




- No agrega campos



### pos.order.line


- Hereda de:

  - pos.order.line




- Campos:

  - **combo_id** (Many2one) → product.combo





### pos.order


- Hereda de:

  - pos.order




- Campos:

  - **table_stand_number** (Char)





### ir.binary


- Hereda de:

  - ir.binary




- No agrega campos



### account.fiscal.position


- Hereda de:

  - account.fiscal.position




- No agrega campos



### res.config.settings


- Hereda de:

  - res.config.settings




- Campos:

  - **pos_self_ordering_takeaway** (Boolean)


  - **pos_self_ordering_service_mode** (Selection)


  - **pos_self_ordering_mode** (Selection)


  - **pos_self_ordering_default_language_id** (Many2one)


  - **pos_self_ordering_available_language_ids** (Many2many)


  - **pos_self_ordering_image_home_ids** (Many2many)


  - **pos_self_ordering_image_brand** (Image)


  - **pos_self_ordering_image_brand_name** (Char)


  - **pos_self_ordering_pay_after** (Selection)


  - **pos_self_ordering_default_user_id** (Many2one)





### pos.load.mixin


- Hereda de:

  - pos.load.mixin




- No agrega campos



### pos_self_order.custom_link


- Hereda de:

  - pos.load.mixin




- Campos:

  - **name** (Char)


  - **url** (Char)


  - **pos_config_ids** (Many2many) → pos.config


  - **style** (Selection)


  - **link_html** (Html) → Preview


  - **sequence** (Integer) → Sequence





### ir.http


- Hereda de:

  - ir.http




- No agrega campos



### pos.session


- Hereda de:

  - pos.session




- No agrega campos






## Vistas


### pos_self_order.custom_link

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | custom.link.list | `pos_self_order.custom_link_tree` | - |


