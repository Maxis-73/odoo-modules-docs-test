# Módulo: Stock - SMS

## Información General
- **Nombre técnico:** stock_sms
- **Versión:** 1.0
- **Categoría:** Hidden
- **Dependencias:** stock, sms


## Propósito
Send text messages when final stock move



## Descripción
Send text messages when final stock move



## Modelos

### stock.picking


- Hereda de:

  - stock.picking




- No agrega campos




### res.config.settings


- Hereda de:

  - res.config.settings




#### Campos
- **stock_move_sms_validation** (Boolean)
- **stock_sms_confirmation_template_id** (Many2one)





### res.company


- Hereda de:

  - res.company




#### Campos
- **stock_move_sms_validation** (Boolean) → SMS Confirmation
- **stock_sms_confirmation_template_id** (Many2one) → sms.template
- **has_received_warning_stock_sms** (Boolean)










## Vistas Adicionales


### confirm.stock.sms

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | stock_confirm_sms | `stock_sms.view_confirm_stock_sms` | - |



**Botones (stock_sms.view_confirm_stock_sms):**
- **Confirm** (object)
- **Disable SMS** (object)



