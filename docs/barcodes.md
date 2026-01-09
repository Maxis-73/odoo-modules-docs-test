# Módulo: Barcode

## Información General
- **Nombre técnico:** barcodes
- **Versión:** 2.0
- **Categoría:** Hidden
- **Dependencias:** web


## Propósito
Scan and Parse Barcodes





## Modelos

### barcode.nomenclature


- Hereda de: Base



- Campos:

  - **name** (Char)


  - **rule_ids** (One2many) → barcode.rule


  - **upc_ean_conv** (Selection)





### barcodes.barcode_events_mixin


- Hereda de: Base



- Campos:

  - **_barcode_scanned** (Char) → Barcode Scanned





### barcode.rule


- Hereda de: Base



- Campos:

  - **name** (Char)


  - **barcode_nomenclature_id** (Many2one) → barcode.nomenclature


  - **sequence** (Integer)


  - **encoding** (Selection)


  - **type** (Selection)


  - **pattern** (Char)


  - **alias** (Char)





### res.company


- Hereda de:

  - res.company




- Campos:

  - **nomenclature_id** (Many2one) → barcode.nomenclature





### ir.http


- Hereda de:

  - ir.http




- No agrega campos






## Vistas


### barcode.nomenclature

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | Barcode Nomenclatures | `barcodes.view_barcode_nomenclature_form` | - |
| list | Barcode Nomenclatures | `barcodes.view_barcode_nomenclature_tree` | - |



### barcode.rule

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | Barcode Rule | `barcodes.view_barcode_rule_form` | - |


