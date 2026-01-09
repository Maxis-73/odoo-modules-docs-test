# Módulo: Spreadsheet Test

## Información General
- **Nombre técnico:** test_spreadsheet
- **Versión:** 1.0
- **Categoría:** Hidden
- **Dependencias:** spreadsheet


## Propósito
Spreadsheet Test, mainly to test the mixin behavior



## Descripción
This module contains tests related to spreadsheet.
    The modules exposes some mixin that are only implemented in other functional modules.
    When trying to test a global behavior of the mixin, it makes no sense to test it in
    each module implementing the mixin but rather test a dummy implementation of the later,
    hence the need for this test module.
    



## Modelos

### spreadsheet.test


- Hereda de:


  - spreadsheet.mixin





- No agrega campos






