# Módulo: Point of Sale - Coupons & Loyalty

## Información General
- **Nombre técnico:** pos_loyalty
- **Versión:** 2.0
- **Categoría:** Sales/Point Of Sale
- **Dependencias:** loyalty, point_of_sale


## Propósito
Use Coupons, Gift Cards and Loyalty programs in Point of Sale





## Modelos

### loyalty.card


- Hereda de:


  - loyalty.card

  - pos.load.mixin





- Campos:

  - **source_pos_order_id** (Many2one) → pos.order





### pos.config


- Hereda de:

  - pos.config




- No agrega campos



### loyalty.program


- Hereda de:


  - loyalty.program

  - pos.load.mixin





- Campos:

  - **pos_config_ids** (Many2many) → pos.config


  - **pos_order_count** (Integer) → PoS Order Count


  - **pos_ok** (Boolean) → Point of Sale


  - **pos_report_print_id** (Many2one) → ir.actions.report





### product.product


- Hereda de:

  - product.product




- No agrega campos



### pos.order.line


- Hereda de:

  - pos.order.line




- Campos:

  - **is_reward_line** (Boolean)


  - **reward_id** (Many2one) → loyalty.reward


  - **coupon_id** (Many2one) → loyalty.card


  - **reward_identifier_code** (Char)


  - **points_cost** (Float)





### loyalty.mail


- Hereda de:

  - loyalty.mail




- Campos:

  - **pos_report_print_id** (Many2one) → ir.actions.report





### pos.order


- Hereda de:

  - pos.order




- No agrega campos



### barcode.rule


- Hereda de:

  - barcode.rule




- Campos:

  - **type** (Selection)





### loyalty.rule


- Hereda de:


  - loyalty.rule

  - pos.load.mixin





- Campos:

  - **valid_product_ids** (Many2many) → product.product


  - **any_product** (Boolean)


  - **promo_barcode** (Char) → Barcode





### loyalty.reward


- Hereda de:


  - loyalty.reward

  - pos.load.mixin





- No agrega campos



### pos.session


- Hereda de:

  - pos.session




- No agrega campos



### res.partner


- Hereda de:

  - res.partner




- Campos:

  - **loyalty_card_count** (Integer)







