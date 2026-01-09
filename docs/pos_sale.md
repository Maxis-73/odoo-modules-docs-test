# Módulo: POS - Sales

## Información General
- **Nombre técnico:** pos_sale
- **Versión:** 1.1
- **Categoría:** Hidden
- **Dependencias:** point_of_sale, sale_management


## Propósito
Link module between Point of Sale and Sales



## Descripción


This module adds a custom Sales Team for the Point of Sale. This enables you to view and manage your point of sale sales with more ease.




## Modelos

### sale.order


- Hereda de:


  - sale.order

  - pos.load.mixin





#### Campos
- **pos_order_line_ids** (One2many) → pos.order.line
- **pos_order_count** (Integer)
- **amount_unpaid** (Monetary)





### sale.order.line


- Hereda de:


  - sale.order.line

  - pos.load.mixin





#### Campos
- **pos_order_line_ids** (One2many) → pos.order.line





### pos.config


- Hereda de:

  - pos.config




#### Campos
- **crm_team_id** (Many2one) → crm.team
- **down_payment_product_id** (Many2one) → product.product





### product.product


- Hereda de:

  - product.product




- No agrega campos




### pos.order


- Hereda de:

  - pos.order




#### Campos
- **currency_rate** (Float)
- **crm_team_id** (Many2one) → crm.team
- **sale_order_count** (Integer)





### pos.order.line


- Hereda de:

  - pos.order.line




#### Campos
- **sale_order_origin_id** (Many2one) → sale.order
- **sale_order_line_id** (Many2one) → sale.order.line
- **down_payment_details** (Text)
- **qty_delivered** (Float)





### stock.picking


- Hereda de:

  - stock.picking




- No agrega campos




### res.config.settings


- Hereda de:

  - res.config.settings




#### Campos
- **pos_crm_team_id** (Many2one)
- **pos_down_payment_product_id** (Many2one)





### crm.team


- Hereda de:

  - crm.team




#### Campos
- **pos_config_ids** (One2many) → pos.config
- **pos_sessions_open_count** (Integer)
- **pos_order_amount_total** (Float)





### pos.session


- Hereda de:

  - pos.session




#### Campos
- **crm_team_id** (Many2one) → crm.team







