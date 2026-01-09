# Módulo: Sale Purchase

## Información General
- **Nombre técnico:** sale_purchase
- **Versión:** 1.0
- **Categoría:** Hidden
- **Dependencias:** sale, purchase


## Propósito
Sale based on service outsourcing.



## Descripción

Allows the outsourcing of services. This module allows one to sell services provided
by external providers and will automatically generate purchase orders directed to the service seller.
    



## Modelos

### sale.order


- Hereda de:

  - sale.order




#### Campos
- **purchase_order_count** (Integer) → Number of Purchase Order Generated





### purchase.order


- Hereda de:

  - purchase.order




#### Campos
- **sale_order_count** (Integer) → Number of Source Sale





### purchase.order.line


- Hereda de:

  - purchase.order.line




#### Campos
- **sale_order_id** (Many2one)
- **sale_line_id** (Many2one) → sale.order.line





### sale.order.line


- Hereda de:

  - sale.order.line




#### Campos
- **purchase_line_ids** (One2many) → purchase.order.line
- **purchase_line_count** (Integer) → Number of generated purchase items





### product.template


- Hereda de:

  - product.template




#### Campos
- **service_to_purchase** (Boolean) → Subcontract Service







