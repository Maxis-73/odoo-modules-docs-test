# Módulo: Base import

## Información General
- **Nombre técnico:** base_import
- **Versión:** 2.0
- **Categoría:** Hidden/Tools
- **Dependencias:** web




## Descripción

New extensible file import for Odoo

Re-implement Odoo's file import system:

* Server side, the previous system forces most of the logic into the
  client which duplicates the effort (between clients), makes the
  import system much harder to use without a client (direct RPC or
  other forms of automation) and makes knowledge about the
  import/export system much harder to gather as it is spread over
  3+ different projects.

* In a more extensible manner, so users and partners can build their
  own front-end to import from other file formats (e.g. OpenDocument
  files) which may be simpler to handle in their work flow or from
  their data production sources.

* In a module, so that administrators and users of Odoo who do not
  need or want an online import can avoid it being available to users.




## Modelos

### base


- Hereda de:

  - base




- No agrega campos



### base_import.mapping


- Hereda de: Base



- Campos:

  - **res_model** (Char)


  - **column_name** (Char)


  - **field_name** (Char)





### res.users


- Hereda de:

  - res.users




- No agrega campos



### base_import.import


- Hereda de: Base



- Campos:

  - **res_model** (Char) → Model


  - **file** (Binary) → File


  - **file_name** (Char) → File Name


  - **file_type** (Char) → File Type







