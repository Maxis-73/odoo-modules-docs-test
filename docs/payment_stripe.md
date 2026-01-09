# Módulo: Payment Provider: Stripe

## Información General
- **Nombre técnico:** payment_stripe
- **Versión:** 2.0
- **Categoría:** Accounting/Payment Providers
- **Dependencias:** payment


## Propósito
An Irish-American payment provider covering the US and many others.



## Descripción
 



## Modelos

### payment.token


- Hereda de:

  - payment.token




#### Campos
- **stripe_payment_method** (Char)
- **stripe_mandate** (Char)





### payment.transaction


- Hereda de:

  - payment.transaction




- No agrega campos




### payment.provider


- Hereda de:

  - payment.provider




#### Campos
- **code** (Selection)
- **stripe_publishable_key** (Char)
- **stripe_secret_key** (Char)
- **stripe_webhook_secret** (Char)







