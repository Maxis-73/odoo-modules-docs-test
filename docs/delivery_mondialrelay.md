# Módulo: delivery_mondialrelay

## Información General
- **Nombre técnico:** delivery_mondialrelay
- **Versión:** 0.1
- **Categoría:** Inventory/Delivery
- **Dependencias:** stock_delivery


## Propósito
 Let's choose a Point Relais® as shipping address 



## Descripción

This module allow your customer to choose a Point Relais® and use it as shipping address.
This module doesn't implement the WebService. It is only the integration of the widget.

Delivery price pre-configured is an example, you need to adapt the pricing's rules.
    



## Modelos

### delivery.carrier


- Hereda de:

  - delivery.carrier




- Campos:

  - **is_mondialrelay** (Boolean)


  - **mondialrelay_brand** (Char)


  - **mondialrelay_packagetype** (Char)





### sale.order


- Hereda de:

  - sale.order




- No agrega campos



### res.partner


- Hereda de:

  - res.partner




- Campos:

  - **is_mondialrelay** (Boolean)








## Vistas


### choose.delivery.carrier

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | choose.delivery.carrier.form | `delivery_mondialrelay.choose_delivery_carrier_view_form` | delivery.choose_delivery_carrier_view_form |


