# Módulo: Sale Loyalty

## Información General
- **Nombre técnico:** sale_loyalty
- **Versión:** 1.0
- **Categoría:** Sales/Sales
- **Dependencias:** sale, loyalty


## Propósito
Use discounts and loyalty programs in sales orders



## Descripción
Integrate discount and loyalty programs mechanisms in sales orders.



## Modelos

### loyalty.card


- Hereda de:

  - loyalty.card




- Campos:

  - **order_id** (Many2one) → sale.order





### sale.order


- Hereda de:

  - sale.order




- Campos:

  - **applied_coupon_ids** (Many2many) → loyalty.card


  - **code_enabled_rule_ids** (Many2many) → loyalty.rule


  - **coupon_point_ids** (One2many) → sale.order.coupon.points


  - **reward_amount** (Float)


  - **loyalty_data** (Json)





### loyalty.program


- Hereda de:

  - loyalty.program




- Campos:

  - **order_count** (Integer)


  - **sale_ok** (Boolean)





### sale.order.line


- Hereda de:

  - sale.order.line




- Campos:

  - **is_reward_line** (Boolean)


  - **reward_id** (Many2one) → loyalty.reward


  - **coupon_id** (Many2one) → loyalty.card


  - **reward_identifier_code** (Char)


  - **points_cost** (Float)





### loyalty.history


- Hereda de:

  - loyalty.history




- No agrega campos



### sale.order.coupon.points


- Hereda de: Base



- Campos:

  - **order_id** (Many2one) → sale.order


  - **coupon_id** (Many2one) → loyalty.card


  - **points** (Float)





### loyalty.reward


- Hereda de:

  - loyalty.reward




- No agrega campos






## Vistas


### sale.loyalty.reward.wizard

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | sale.loyalty.reward.wizard.view.form | `sale_loyalty.sale_loyalty_reward_wizard_view_form` | - |



#### Botones (sale_loyalty.sale_loyalty_reward_wizard_view_form)
- **Apply** (object)
- **Coupons & Loyalty** (action) - Grupos: `sales_team.group_sale_manager`


### sale.loyalty.coupon.wizard

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | sale.loyalty.coupon.wizard.view.form | `sale_loyalty.sale_loyalty_coupon_wizard_view_form` | - |



#### Botones (sale_loyalty.sale_loyalty_coupon_wizard_view_form)
- **Apply** (object)

