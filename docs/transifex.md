# Módulo: Transifex integration

## Información General
- **Nombre técnico:** transifex
- **Versión:** 1.0
- **Categoría:** Hidden/Tools
- **Dependencias:** base, web


## Propósito
Add a link to edit a translation in Transifex



## Descripción

Transifex integration
This module will add a link to the Transifex project in the translation view.
The purpose of this module is to speed up translations of the main modules.

To work, Odoo uses Transifex configuration files `.tx/config` to detect the
project source. Custom modules will not be translated (as not published on
the main Transifex project).

The language the user tries to translate must be activated on the Transifex
project.
        



## Modelos

### transifex.translation


- Hereda de: Base



- No agrega campos



### transifex.code.translation


- Hereda de: Base



- Campos:

  - **source** (Text)


  - **value** (Text)


  - **module** (Char)


  - **lang** (Selection)


  - **transifex_url** (Char) → Transifex URL





### base


- Hereda de:

  - base




- No agrega campos






## Vistas


### transifex.code.translation

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | transifex.code.translation.list | `transifex.transifex_code_translation_tree_view` | - |
| search | transifex.code.translation.view.search | `transifex.transifex_code_translation_view_search` | - |



#### Filtros de búsqueda (transifex.transifex_code_translation_view_search)

**Filtros:**
- **Not Translated** (`[('value', '=', '')]`)


**Agrupar por:**
- Module

