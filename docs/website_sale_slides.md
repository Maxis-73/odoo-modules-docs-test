# Módulo: Sell Courses

## Información General
- **Nombre técnico:** website_sale_slides
- **Versión:** 1.0
- **Categoría:** Hidden
- **Dependencias:** website_slides, website_sale


## Propósito
Sell your courses online



## Descripción
Sell your courses using the e-commerce features of the website.



## Modelos

### sale.order


- Hereda de:

  - sale.order




- No agrega campos



### product.product


- Hereda de:

  - product.product




- Campos:

  - **channel_ids** (One2many) → slide.channel





### product.template


- Hereda de:

  - product.template




- Campos:

  - **service_tracking** (Selection)





### slide.channel


- Hereda de:

  - slide.channel




- Campos:

  - **enroll** (Selection)


  - **product_id** (Many2one) → product.product


  - **product_sale_revenues** (Monetary)


  - **currency_id** (Many2one)








## Vistas


### sale.report

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| graph | sale.report.view.graph.slides | `website_sale_slides.sale_report_view_graph_slides` | - |


