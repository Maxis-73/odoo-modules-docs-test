# Módulo: Delivery Costs

## Información General
- **Nombre técnico:** delivery
- **Versión:** 1.0
- **Categoría:** Sales/Delivery
- **Dependencias:** sale




## Descripción

Allows you to add delivery methods in sale orders.
You can define your own carrier for prices.
The system is able to add and compute the shipping line.




## Modelos

### delivery.carrier


- Hereda de: Base



- Campos:

  - **name** (Char) → Delivery Method


  - **active** (Boolean)


  - **sequence** (Integer)


  - **delivery_type** (Selection)


  - **integration_level** (Selection)


  - **prod_environment** (Boolean) → Environment


  - **debug_logging** (Boolean) → Debug logging


  - **company_id** (Many2one) → res.company


  - **product_id** (Many2one) → product.product


  - **tracking_url** (Char)


  - **currency_id** (Many2one)


  - **invoice_policy** (Selection)


  - **country_ids** (Many2many) → res.country


  - **state_ids** (Many2many) → res.country.state


  - **zip_prefix_ids** (Many2many) → delivery.zip.prefix


  - **max_weight** (Float) → Max Weight


  - **weight_uom_name** (Char)


  - **max_volume** (Float) → Max Volume


  - **volume_uom_name** (Char)


  - **must_have_tag_ids** (Many2many) → product.tag


  - **excluded_tag_ids** (Many2many) → product.tag


  - **carrier_description** (Text) → Carrier Description


  - **margin** (Float)


  - **fixed_margin** (Float)


  - **free_over** (Boolean) → Free if order amount is above


  - **amount** (Float)


  - **can_generate_return** (Boolean)


  - **return_label_on_delivery** (Boolean)


  - **get_return_label_from_portal** (Boolean)


  - **supports_shipping_insurance** (Boolean)


  - **shipping_insurance** (Integer) → Insurance Percentage


  - **price_rule_ids** (One2many) → delivery.price.rule


  - **fixed_price** (Float)





### sale.order


- Hereda de:

  - sale.order




- Campos:

  - **pickup_location_data** (Json)


  - **carrier_id** (Many2one) → delivery.carrier


  - **delivery_message** (Char)


  - **delivery_set** (Boolean)


  - **recompute_delivery_price** (Boolean) → Delivery cost should be recomputed


  - **is_all_service** (Boolean) → Service Product


  - **shipping_weight** (Float) → Shipping Weight





### sale.order.line


- Hereda de:

  - sale.order.line




- Campos:

  - **is_delivery** (Boolean)


  - **product_qty** (Float)


  - **recompute_delivery_price** (Boolean)





### product.category


- Hereda de:

  - product.category




- No agrega campos



### delivery.zip.prefix


- Hereda de: Base



- Campos:

  - **name** (Char) → Prefix





### delivery.price.rule


- Hereda de: Base



- Campos:

  - **name** (Char)


  - **sequence** (Integer)


  - **carrier_id** (Many2one) → delivery.carrier


  - **currency_id** (Many2one)


  - **variable** (Selection)


  - **operator** (Selection)


  - **max_value** (Float) → Maximum Value


  - **list_base_price** (Float)


  - **list_price** (Float) → Sale Price


  - **variable_factor** (Selection)





### res.partner


- Hereda de:

  - res.partner




- Campos:

  - **property_delivery_carrier_id** (Many2one) → delivery.carrier








## Vistas


### delivery.price.rule

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | delivery.price.rule.form | `delivery.view_delivery_price_rule_form` | - |
| list | delivery.price.rule.list | `delivery.view_delivery_price_rule_tree` | - |



### delivery.carrier

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | delivery.carrier.list | `delivery.view_delivery_carrier_tree` | - |
| search | delivery.carrier.search | `delivery.view_delivery_carrier_search` | - |
| form | delivery.carrier.form | `delivery.view_delivery_carrier_form` | - |



#### Filtros de búsqueda (delivery.view_delivery_carrier_search)

**Filtros:**
- **Archived** (`[('active', '=', False)]`)


**Agrupar por:**
- Provider


#### Botones (delivery.view_delivery_carrier_form)
- **toggle_prod_environment** (object)
- **toggle_prod_environment** (object)
- **toggle_debug** (object)
- **toggle_debug** (object)
- **Install more Providers** (object)


### choose.delivery.carrier

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | choose.delivery.carrier.form | `delivery.choose_delivery_carrier_view_form` | - |



#### Botones (delivery.choose_delivery_carrier_view_form)
- **update_price** (object)
- **Update** (object)
- **Add** (object)

