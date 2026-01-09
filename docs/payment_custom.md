# Módulo: Payment Provider: Custom Payment Modes

## Información General
- **Nombre técnico:** payment_custom
- **Versión:** 2.0
- **Categoría:** Accounting/Payment Providers
- **Dependencias:** payment


## Propósito
A payment provider for custom flows like wire transfers.



## Descripción
 



## Modelos

### payment.transaction


- Hereda de:

  - payment.transaction




- No agrega campos



### payment.provider


- Hereda de:

  - payment.provider




- Campos:

  - **code** (Selection)


  - **custom_mode** (Selection)


  - **qr_code** (Boolean)







