# Módulo: POS - SMS

## Información General
- **Nombre técnico:** pos_sms
- **Versión:** N/A
- **Categoría:** Send sms to customer for order confirmation
- **Dependencias:** point_of_sale, sms




## Descripción
This module integrates the Point of Sale with SMS



## Modelos

### pos.config


- Hereda de:

  - pos.config




- Campos:

  - **sms_receipt_template_id** (Many2one) → sms.template





### pos.order


- Hereda de:

  - pos.order




- No agrega campos



### res.config.settings


- Hereda de:

  - res.config.settings




- Campos:

  - **pos_sms_receipt_template_id** (Many2one) → sms.template







