# Módulo: Product Comparison

## Información General
- **Nombre técnico:** website_sale_comparison
- **Versión:** 1.0
- **Categoría:** Website/Website
- **Dependencias:** website_sale


## Propósito
Allow shoppers to compare products based on their attributes



## Descripción

This module adds a comparison tool to your eCommerce shop, so that your shoppers can easily compare products based on their attributes. It will considerably accelerate their purchasing decision.

To configure product attributes, activate *Attributes & Variants* in the Website settings. This will add a dedicated section in the product form. In the configuration, this module adds a category field to product attributes in order to structure the shopper's comparison table.

Finally, the module comes with an option to display an attribute summary table in product web pages (available in Customize menu).
    



## Modelos

### product.attribute.category


- Hereda de: Base



- Campos:

  - **name** (Char) → Category Name


  - **sequence** (Integer) → Sequence


  - **attribute_ids** (One2many) → product.attribute





### product.product


- Hereda de:

  - product.product




- No agrega campos



### product.template.attribute.line


- Hereda de:

  - product.template.attribute.line




- No agrega campos



### product.attribute


- Hereda de:

  - product.attribute




- Campos:

  - **category_id** (Many2one) → product.attribute.category








## Vistas


### product.attribute.category

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | product.attribute.category.list | `website_sale_comparison.product_attribute_category_tree_view` | - |


