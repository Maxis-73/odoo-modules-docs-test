# Módulo: Margins by Products

## Información General
- **Nombre técnico:** product_margin
- **Versión:** N/A
- **Categoría:** Sales/Sales
- **Dependencias:** account




## Descripción

Adds a reporting menu in products that computes sales, purchases, margins and other interesting indicators based on invoices.

The wizard to launch the report has several options to help you get the data you need.




## Modelos

### product.product


- Hereda de:

  - product.product




- Campos:

  - **date_from** (Date)


  - **date_to** (Date)


  - **invoice_state** (Selection)


  - **sale_avg_price** (Float)


  - **purchase_avg_price** (Float)


  - **sale_num_invoiced** (Float)


  - **purchase_num_invoiced** (Float)


  - **sales_gap** (Float)


  - **purchase_gap** (Float)


  - **turnover** (Float)


  - **total_cost** (Float)


  - **sale_expected** (Float)


  - **normal_cost** (Float)


  - **total_margin** (Float)


  - **expected_margin** (Float)


  - **total_margin_rate** (Float)


  - **expected_margin_rate** (Float)








## Vistas


### product.product

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| graph | product.margin.graph | `product_margin.view_product_margin_graph` | - |
| form | product.margin.form.inherit | `product_margin.view_product_margin_form` | - |
| list | product.margin.list | `product_margin.view_product_margin_tree` | - |



### product.margin

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | product.margin.form | `product_margin.product_margin_form_view` | - |



#### Botones (product_margin.product_margin_form_view)
- **Open Margins** (object)

