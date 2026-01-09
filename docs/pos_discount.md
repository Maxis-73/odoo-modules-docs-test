# Módulo: Point of Sale Discounts

## Información General
- **Nombre técnico:** pos_discount
- **Versión:** 1.0
- **Categoría:** Sales/Point of Sale
- **Dependencias:** point_of_sale


## Propósito
Simple Discounts in the Point of Sale 



## Descripción


This module allows the cashier to quickly give percentage-based
discount to a customer.





## Modelos

### pos.config


- Hereda de:

  - pos.config




#### Campos
- **iface_discount** (Boolean)
- **discount_pc** (Float)
- **discount_product_id** (Many2one) → product.product





### product.product


- Hereda de:

  - product.product




- No agrega campos




### res.config.settings


- Hereda de:

  - res.config.settings




#### Campos
- **pos_discount_pc** (Float)
- **pos_discount_product_id** (Many2one) → product.product







