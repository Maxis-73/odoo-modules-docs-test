# Módulo: Base import module

## Información General
- **Nombre técnico:** base_import_module
- **Versión:** N/A
- **Categoría:** Hidden/Tools
- **Dependencias:** web




## Descripción

Import a custom data module
===========================

This module allows authorized users to import a custom data module (.xml files and static assests)
for customization purpose.




## Modelos

### ir.module.module


- Hereda de:

  - ir.module.module




#### Campos
- **imported** (Boolean)
- **module_type** (Selection)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | Apps List Data Modules | `base_import_module.module_tree_apps_inherit` | base.module_tree |




### ir.ui.view


- Hereda de:

  - ir.ui.view




- No agrega campos




### base.import.module


- Hereda de: Base



#### Campos
- **module_file** (Binary)
- **state** (Selection)
- **import_message** (Text)
- **force** (Boolean)
- **with_demo** (Boolean)
- **modules_dependencies** (Text)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | base.import.module.form | `base_import_module.view_base_module_import` | - |



**Botones (base_import_module.view_base_module_import):**
- **Install** (object)








