# Módulo: Ecuadorian Website

## Información General
- **Nombre técnico:** l10n_ec_website_sale
- **Versión:** 1.0
- **Categoría:** Accounting/Localizations/Website
- **Dependencias:** website_sale, l10n_ec




## Descripción
Make ecommerce work for Ecuador.



## Modelos

### website


- Hereda de:

  - website




- No agrega campos



### sale.order


- Hereda de:

  - sale.order




- No agrega campos



### payment.method


- Hereda de:

  - payment.method




- Campos:

  - **l10n_ec_sri_payment_id** (Many2one) → l10n_ec.sri.payment


  - **fiscal_country_codes** (Char)







