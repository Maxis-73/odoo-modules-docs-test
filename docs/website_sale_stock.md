# Módulo: Product Availability

## Información General
- **Nombre técnico:** website_sale_stock
- **Versión:** N/A
- **Categoría:** Website/Website
- **Dependencias:** website_sale, sale_stock, stock_delivery


## Propósito
Manage product inventory & availability



## Descripción

Manage the inventory of your products and display their availability status in your eCommerce store.
In case of stockout, you can decide to block further sales or to keep selling.
A default behavior can be selected in the Website settings.
Then it can be made specific at the product level.
    



## Modelos

### website


- Hereda de:

  - website




#### Campos
- **warehouse_id** (Many2one) → stock.warehouse





### product.combo


- Hereda de:

  - product.combo




- No agrega campos




### sale.order


- Hereda de:

  - sale.order




- No agrega campos




### product.product


- Hereda de:

  - product.product




#### Campos
- **stock_notification_partner_ids** (Many2many) → res.partner





### sale.order.line


- Hereda de:

  - sale.order.line




- No agrega campos




### product.template


- Hereda de:

  - product.template




#### Campos
- **allow_out_of_stock_order** (Boolean)
- **available_threshold** (Float)
- **show_availability** (Boolean)
- **out_of_stock_message** (Html)





### stock.picking


- Hereda de:

  - stock.picking




#### Campos
- **website_id** (Many2one) → website





### res.config.settings


- Hereda de:

  - res.config.settings




#### Campos
- **allow_out_of_stock_order** (Boolean)
- **available_threshold** (Float)
- **show_availability** (Boolean)
- **website_warehouse_id** (Many2one) → stock.warehouse







