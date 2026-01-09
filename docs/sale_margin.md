# Módulo: Margins in Sales Orders

## Información General
- **Nombre técnico:** sale_margin
- **Versión:** 1.0
- **Categoría:** Sales/Sales
- **Dependencias:** sale_management




## Descripción

This module adds the 'Margin' on sales order.
=============================================

This gives the profitability by calculating the difference between the Unit
Price and Cost Price.
    



## Modelos

### sale.order


- Hereda de:

  - sale.order




#### Campos
- **margin** (Monetary) → Margin
- **margin_percent** (Float) → Margin (%)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| pivot | sale.order.margin.view.pivot | `sale_margin.sale_margin_sale_order_pivot` | sale.view_sale_order_pivot |
| graph | sale.order.margin.view.graph | `sale_margin.sale_margin_sale_order_graph` | sale.view_sale_order_graph |




### sale.order.line


- Hereda de:

  - sale.order.line




#### Campos
- **margin** (Float) → Margin
- **margin_percent** (Float) → Margin (%)
- **purchase_price** (Float)










