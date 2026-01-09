# Módulo: Phone Numbers Validation

## Información General
- **Nombre técnico:** phone_validation
- **Versión:** 2.1
- **Categoría:** Hidden
- **Dependencias:** base, mail


## Propósito
Validate and format phone numbers



## Descripción

Phone Numbers Validation
========================

This module adds the feature of validation and formatting phone numbers
according to a destination country.

It also adds phone blacklist management through a specific model storing
blacklisted phone numbers.

It adds mail.thread.phone mixin that handles sanitation and blacklist of
records numbers. 



## Modelos

### mail.thread.phone


- Hereda de:


  - mail.thread





#### Campos
- **phone_sanitized** (Char)
- **phone_sanitized_blacklisted** (Boolean)
- **phone_blacklisted** (Boolean)
- **mobile_blacklisted** (Boolean)
- **phone_mobile_search** (Char) → Phone/Mobile





### res.users


- Hereda de:

  - res.users




- No agrega campos




### phone.blacklist


- Hereda de:


  - mail.thread





#### Campos
- **number** (Char)
- **active** (Boolean)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | phone.blacklist.view.list | `phone_validation.phone_blacklist_view_tree` | - |
| form | phone.blacklist.view.form | `phone_validation.phone_blacklist_view_form` | - |
| search | phone.blacklist.view.search | `phone_validation.phone_blacklist_view_search` | - |



**Botones (phone_validation.phone_blacklist_view_form):**
- **Unblacklist** (object)
- **Blacklist** (object)


**Filtros de búsqueda (phone_validation.phone_blacklist_view_search):**

- **Archived** (`[('active','=',False)]`)



### res.partner


- Hereda de:


  - res.partner





- No agrega campos




### base


- Hereda de:

  - base




- No agrega campos









## Vistas Adicionales


### phone.blacklist.remove

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | phone.blacklist.remove.form | `phone_validation.phone_blacklist_remove_view_form` | - |



**Botones (phone_validation.phone_blacklist_remove_view_form):**
- **Remove phone from blacklist** (object)



