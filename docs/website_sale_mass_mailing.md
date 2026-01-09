# Módulo: Checkout Newsletter

## Información General
- **Nombre técnico:** website_sale_mass_mailing
- **Versión:** 1.0
- **Categoría:** Website/Website
- **Dependencias:** website_sale, website_mass_mailing


## Propósito
Let new customers sign up for a newsletter during checkout



## Descripción

        Allows anonymous shoppers of your eCommerce to sign up for a newsletter during the checkout
        process.
    



## Modelos

### website


- Hereda de:

  - website




#### Campos
- **newsletter_id** (Many2one) → mailing.list





### res.config.settings


- Hereda de:

  - res.config.settings




#### Campos
- **is_newsletter_enabled** (Boolean)
- **newsletter_id** (Many2one)







