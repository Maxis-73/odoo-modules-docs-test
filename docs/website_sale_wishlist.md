# Módulo: Shopper's Wishlist

## Información General
- **Nombre técnico:** website_sale_wishlist
- **Versión:** 1.0
- **Categoría:** Website/Website
- **Dependencias:** website_sale


## Propósito
Allow shoppers to enlist products



## Descripción

Allow shoppers of your eCommerce store to create personalized collections of products they want to buy and save them for future reference.
    



## Modelos

### product.wishlist


- Hereda de: Base



#### Campos
- **partner_id** (Many2one) → res.partner
- **product_id** (Many2one) → product.product
- **currency_id** (Many2one) → res.currency
- **pricelist_id** (Many2one) → product.pricelist
- **price** (Monetary)
- **website_id** (Many2one) → website
- **active** (Boolean)





### res.partner


- Hereda de:

  - res.partner




#### Campos
- **wishlist_ids** (One2many) → product.wishlist





### product.template


- Hereda de:

  - product.template




- No agrega campos




### product.product


- Hereda de:

  - product.product




- No agrega campos




### res.users


- Hereda de:

  - res.users




- No agrega campos






