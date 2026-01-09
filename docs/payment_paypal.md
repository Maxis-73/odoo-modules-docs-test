# Módulo: Payment Provider: Paypal

## Información General
- **Nombre técnico:** payment_paypal
- **Versión:** 2.0
- **Categoría:** Accounting/Payment Providers
- **Dependencias:** payment


## Propósito
An American payment provider for online payments all over the world.



## Descripción
 



## Modelos

### payment.transaction


- Hereda de:

  - payment.transaction




#### Campos
- **paypal_type** (Char)





### payment.provider


- Hereda de:

  - payment.provider




#### Campos
- **code** (Selection)
- **paypal_email_account** (Char)
- **paypal_client_id** (Char)
- **paypal_client_secret** (Char)
- **paypal_access_token** (Char)
- **paypal_access_token_expiry** (Datetime)
- **paypal_webhook_id** (Char)







