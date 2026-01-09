# Módulo: Payment Provider: Authorize.Net

## Información General
- **Nombre técnico:** payment_authorize
- **Versión:** 2.0
- **Categoría:** Accounting/Payment Providers
- **Dependencias:** payment


## Propósito
An payment provider covering the US, Australia, and Canada.



## Descripción
 



## Modelos

### payment.token


- Hereda de:

  - payment.token




- Campos:

  - **authorize_profile** (Char)





### payment.transaction


- Hereda de:

  - payment.transaction




- No agrega campos



### payment.provider


- Hereda de:

  - payment.provider




- Campos:

  - **code** (Selection)


  - **authorize_login** (Char)


  - **authorize_transaction_key** (Char)


  - **authorize_signature_key** (Char)


  - **authorize_client_key** (Char)







