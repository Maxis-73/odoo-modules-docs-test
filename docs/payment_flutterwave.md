# Módulo: Payment Provider: Flutterwave

## Información General
- **Nombre técnico:** payment_flutterwave
- **Versión:** 1.0
- **Categoría:** Accounting/Payment Providers
- **Dependencias:** payment


## Propósito
A Nigerian payment provider covering several African countries.



## Descripción
 



## Modelos

### payment.token


- Hereda de:

  - payment.token




#### Campos
- **flutterwave_customer_email** (Char)





### payment.transaction


- Hereda de:

  - payment.transaction




- No agrega campos




### payment.provider


- Hereda de:

  - payment.provider




#### Campos
- **code** (Selection)
- **flutterwave_public_key** (Char)
- **flutterwave_secret_key** (Char)
- **flutterwave_webhook_secret** (Char)







