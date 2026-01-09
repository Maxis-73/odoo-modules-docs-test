# Módulo: Coupons, Promotions, Gift Card and Loyalty for eCommerce

## Información General
- **Nombre técnico:** website_sale_loyalty
- **Versión:** 1.0
- **Categoría:** Website/Website
- **Dependencias:** website_sale, website_links, sale_loyalty


## Propósito
Use coupon, promotion, gift cards and loyalty programs in your eCommerce store



## Descripción

Create coupon, promotion codes, gift cards and loyalty programs to boost your sales (free products, discounts, etc.). Shoppers can use them in the eCommerce checkout.

Coupon & promotion programs can be edited in the Catalog menu of the Website app.
    



## Modelos

### loyalty.card


- Hereda de:

  - loyalty.card




- No agrega campos




### sale.order


- Hereda de:

  - sale.order




#### Campos
- **disabled_auto_rewards** (Many2many) → loyalty.reward





### loyalty.program


- Hereda de:


  - loyalty.program

  - website.multi.mixin





#### Campos
- **ecommerce_ok** (Boolean) → Available on Website





### sale.order.line


- Hereda de:

  - sale.order.line




- No agrega campos




### loyalty.rule


- Hereda de:

  - loyalty.rule




#### Campos
- **website_id** (Many2one)










## Vistas Adicionales


### coupon.share

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | coupon.share.form | `website_sale_loyalty.coupon_share_view_form` | - |



**Botones (website_sale_loyalty.coupon_share_view_form):**
- **Generate Short Link** (object)



