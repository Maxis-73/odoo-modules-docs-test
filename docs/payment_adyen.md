# Módulo: Payment Provider: Adyen

## Información General
- **Nombre técnico:** payment_adyen
- **Versión:** 2.0
- **Categoría:** Accounting/Payment Providers
- **Dependencias:** payment


## Propósito
A Dutch payment provider covering Europe and the US.



## Descripción
 



## Modelos

### payment.token


- Hereda de:

  - payment.token




- Campos:

  - **adyen_shopper_reference** (Char)





### payment.transaction


- Hereda de:

  - payment.transaction




- No agrega campos



### payment.provider


- Hereda de:

  - payment.provider




- Campos:

  - **code** (Selection)


  - **adyen_merchant_account** (Char)


  - **adyen_api_key** (Char)


  - **adyen_client_key** (Char)


  - **adyen_hmac_key** (Char)


  - **adyen_api_url_prefix** (Char)







