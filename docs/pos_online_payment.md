# Módulo: Point of Sale online payment

## Información General
- **Nombre técnico:** pos_online_payment
- **Versión:** N/A
- **Categoría:** N/A
- **Dependencias:** point_of_sale, account_payment






## Modelos

### pos.config


- Hereda de:

  - pos.config




- No agrega campos



### payment.transaction


- Hereda de:

  - payment.transaction




- Campos:

  - **pos_order_id** (Many2one) → pos.order





### account.payment


- Hereda de:

  - account.payment




- Campos:

  - **pos_order_id** (Many2one) → pos.order





### pos.payment.method


- Hereda de:

  - pos.payment.method




- Campos:

  - **is_online_payment** (Boolean)


  - **online_payment_provider_ids** (Many2many) → payment.provider


  - **has_an_online_payment_provider** (Boolean)


  - **type** (Selection)





### pos.order


- Hereda de:

  - pos.order




- Campos:

  - **online_payment_method_id** (Many2one) → pos.payment.method


  - **next_online_payment_amount** (Float)





### pos.payment


- Hereda de:

  - pos.payment




- Campos:

  - **online_account_payment_id** (Many2one) → account.payment





### pos.session


- Hereda de:

  - pos.session




- No agrega campos





