# Módulo: Product Images

## Información General
- **Nombre técnico:** product_images
- **Versión:** 1.0
- **Categoría:** Technical
- **Dependencias:** product




## Descripción

Automatically set product images based on the barcode
=====================================================

This module integrates with the Google Custom Search API to set images on products based on the
barcode.
    



## Modelos

### product.product


- Hereda de:

  - product.product




#### Campos
- **image_fetch_pending** (Boolean)





### res.config.settings


- Hereda de:

  - res.config.settings




#### Campos
- **google_custom_search_key** (Char)
- **google_pse_id** (Char)





### ir.cron.trigger


- Hereda de:

  - ir.cron.trigger




- No agrega campos









## Vistas Adicionales


### product.fetch.image.wizard

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | product.fetch.image.wizard.view | `product_images.product_fetch_image_wizard_view_form` | - |



**Botones (product_images.product_fetch_image_wizard_view_form):**
- **Get Pictures** (object)



