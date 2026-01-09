# Módulo: POS Self-Order / Online Payment

## Información General
- **Nombre técnico:** pos_online_payment_self_order
- **Versión:** 1.0
- **Categoría:** Sales/Point of Sale
- **Dependencias:** pos_online_payment, pos_self_order


## Propósito
Support online payment in self-order





## Modelos

### pos.config


- Hereda de:

  - pos.config




#### Campos
- **self_order_online_payment_method_id** (Many2one) → pos.payment.method





### pos.payment.method


- Hereda de:

  - pos.payment.method




- No agrega campos




### pos.order


- Hereda de:

  - pos.order




#### Campos
- **use_self_order_online_payment** (Boolean)





### res.config.settings


- Hereda de:

  - res.config.settings




#### Campos
- **pos_self_order_online_payment_method_id** (Many2one)







