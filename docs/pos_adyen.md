# Módulo: POS Adyen

## Información General
- **Nombre técnico:** pos_adyen
- **Versión:** 1.0
- **Categoría:** Sales/Point of Sale
- **Dependencias:** point_of_sale


## Propósito
Integrate your POS with an Adyen payment terminal





## Modelos

### pos.config


- Hereda de:

  - pos.config




- Campos:

  - **adyen_ask_customer_for_tip** (Boolean) → Ask Customers For Tip





### pos.payment.method


- Hereda de:

  - pos.payment.method




- Campos:

  - **adyen_api_key** (Char)


  - **adyen_terminal_identifier** (Char)


  - **adyen_test_mode** (Boolean)


  - **adyen_latest_response** (Char)


  - **adyen_event_url** (Char)





### res.config.settings


- Hereda de:

  - res.config.settings




- Campos:

  - **pos_adyen_ask_customer_for_tip** (Boolean)







