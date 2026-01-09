# Módulo: Delivery - Stock

## Información General
- **Nombre técnico:** stock_delivery
- **Versión:** 1.0
- **Categoría:** Inventory/Delivery
- **Dependencias:** sale_stock, delivery




## Descripción

Allows you to add delivery methods in pickings.
===============================================

When creating invoices from picking, the system is able to add and compute the shipping line.




## Modelos

### delivery.carrier


- Hereda de:

  - delivery.carrier




#### Campos
- **invoice_policy** (Selection)
- **route_ids** (Many2many) → stock.route





### sale.order


- Hereda de:

  - sale.order




- No agrega campos




### sale.order.line


- Hereda de:

  - sale.order.line




- No agrega campos




### product.template


- Hereda de:

  - product.template




#### Campos
- **hs_code** (Char)
- **country_of_origin** (Many2one) → res.country





### stock.route


- Hereda de:

  - stock.route




#### Campos
- **shipping_selectable** (Boolean) → Applicable on Shipping Methods





### stock.move


- Hereda de:

  - stock.move




#### Campos
- **weight** (Float)





### stock.move.line


- Hereda de:

  - stock.move.line




#### Campos
- **sale_price** (Float)
- **destination_country_code** (Char)
- **carrier_id** (Many2one)





### stock.package.type


- Hereda de:

  - stock.package.type




#### Campos
- **shipper_package_code** (Char) → Carrier Code
- **package_carrier_type** (Selection)





### stock.quant.package


- Hereda de:

  - stock.quant.package




#### Campos
- **weight** (Float)
- **weight_uom_name** (Char)
- **weight_is_kg** (Boolean) → Technical field indicating whether weight uom is kg or not (i.e. lb)
- **weight_uom_rounding** (Float) → Technical field indicating weight's number of decimal places





### stock.picking


- Hereda de:

  - stock.picking




#### Campos
- **carrier_price** (Float)
- **delivery_type** (Selection)
- **carrier_id** (Many2one) → delivery.carrier
- **weight** (Float)
- **carrier_tracking_ref** (Char)
- **carrier_tracking_url** (Char)
- **weight_uom_name** (Char)
- **is_return_picking** (Boolean)
- **return_label_ids** (One2many) → ir.attachment
- **destination_country_code** (Char)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | delivery.carrier.warning.url.form | `stock_delivery.delivery_tracking_url_warning_form` | - |









## Vistas Adicionales


### choose.delivery.package

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | choose.delivery.package.form | `stock_delivery.choose_delivery_package_view_form` | - |



**Botones (stock_delivery.choose_delivery_package_view_form):**
- **Save** (object)



