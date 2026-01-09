# Módulo: Products Expiration Date

## Información General
- **Nombre técnico:** product_expiry
- **Versión:** N/A
- **Categoría:** Inventory/Inventory
- **Dependencias:** stock




## Descripción

Track different dates on products and production lots.
======================================================

Following dates can be tracked:
-------------------------------
    - end of life
    - best before date
    - removal date
    - alert date

Also implements the removal strategy First Expiry First Out (FEFO) widely used, for example, in food industries.




## Modelos

### stock.lot


- Hereda de:

  - stock.lot




#### Campos
- **use_expiration_date** (Boolean)
- **expiration_date** (Datetime)
- **use_date** (Datetime)
- **removal_date** (Datetime)
- **alert_date** (Datetime)
- **product_expiry_alert** (Boolean)
- **product_expiry_reminded** (Boolean)





### procurement.group


- Hereda de:

  - procurement.group




- No agrega campos




### product.product


- Hereda de:

  - product.product




- No agrega campos




### product.template


- Hereda de:

  - product.template




#### Campos
- **use_expiration_date** (Boolean)
- **expiration_time** (Integer)
- **use_time** (Integer)
- **removal_time** (Integer)
- **alert_time** (Integer)





### stock.move


- Hereda de:

  - stock.move




#### Campos
- **use_expiration_date** (Boolean)





### stock.quant


- Hereda de:

  - stock.quant




#### Campos
- **expiration_date** (Datetime)
- **removal_date** (Datetime)
- **use_expiration_date** (Boolean)





### stock.picking


- Hereda de:

  - stock.picking




- No agrega campos




### res.config.settings


- Hereda de:

  - res.config.settings




#### Campos
- **group_expiry_date_on_delivery_slip** (Boolean) → Display Expiration Dates on Delivery Slips





### stock.move.line


- Hereda de:

  - stock.move.line




#### Campos
- **expiration_date** (Datetime)
- **is_expired** (Boolean)
- **use_expiration_date** (Boolean)










## Vistas Adicionales


### expiry.picking.confirmation

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | Confirm | `product_expiry.confirm_expiry_view` | - |



**Botones (product_expiry.confirm_expiry_view):**
- **Confirm** (object)
- **Proceed except for expired one** (object)



