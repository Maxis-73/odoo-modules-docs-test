# Módulo: Extended Addresses

## Información General
- **Nombre técnico:** base_address_extended
- **Versión:** 1.1
- **Categoría:** Hidden
- **Dependencias:** base, contacts


## Propósito
Add extra fields on addresses



## Descripción

Extended Addresses Management

This module provides the ability to choose a city from a list (in specific countries).

It is primarily used for EDIs that might need a special city code.
        



## Modelos

### res.country


- Hereda de:

  - res.country




- Campos:

  - **enforce_cities** (Boolean)





### res.city


- Hereda de: Base



- Campos:

  - **name** (Char) → Name


  - **zipcode** (Char) → Zip


  - **country_id** (Many2one) → res.country


  - **state_id** (Many2one) → res.country.state





### ['res.partner']


- Hereda de:


  - res.partner





- Campos:

  - **street_name** (Char) → Street Name


  - **street_number** (Char) → House


  - **street_number2** (Char) → Door


  - **city_id** (Many2one) → res.city


  - **country_enforce_cities** (Boolean)








## Vistas


### res.partner

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | partner.form.address.extended | `base_address_extended.address_street_extended_form` | - |



### res.city

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | res.city.list | `base_address_extended.view_city_tree` | - |
| search | - | `base_address_extended.view_city_filter` | - |


