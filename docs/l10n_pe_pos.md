# Módulo: Peruvian - Point of Sale with Pe Doc

## Información General
- **Nombre técnico:** l10n_pe_pos
- **Versión:** 1.0
- **Categoría:** Accounting/Localizations/Point of Sale
- **Dependencias:** l10n_pe, point_of_sale




## Descripción

This module brings the technical requirement for the Peruvian regulation.
Install this if you are using the Point of Sale app in Peru.
    



## Modelos

### pos.config


- Hereda de:

  - pos.config




- No agrega campos



### res.city


- Hereda de:


  - res.city

  - pos.load.mixin





- No agrega campos



### l10n_latam.identification.type


- Hereda de:


  - l10n_latam.identification.type

  - pos.load.mixin





- No agrega campos



### l10n_pe.res.city.district


- Hereda de:


  - l10n_pe.res.city.district

  - pos.load.mixin





- Campos:

  - **country_id** (Many2one)


  - **state_id** (Many2one)





### pos.session


- Hereda de:

  - pos.session




- No agrega campos



### res.partner


- Hereda de:

  - res.partner




- No agrega campos





