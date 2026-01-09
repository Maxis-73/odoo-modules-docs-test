# Módulo: Mass mailing on sale orders

## Información General
- **Nombre técnico:** mass_mailing_sale
- **Versión:** 1.0
- **Categoría:** Hidden
- **Dependencias:** sale, mass_mailing


## Propósito
Add sale order UTM info on mass mailing



## Descripción
UTM and mass mailing on sale orders



## Modelos

### utm.campaign


- Hereda de:

  - utm.campaign




- Campos:

  - **ab_testing_winner_selection** (Selection)





### sale.order


- Hereda de:

  - sale.order




- No agrega campos



### mailing.mailing


- Hereda de:

  - mailing.mailing




- Campos:

  - **sale_quotation_count** (Integer) → Quotation Count


  - **sale_invoiced_amount** (Integer) → Invoiced Amount







