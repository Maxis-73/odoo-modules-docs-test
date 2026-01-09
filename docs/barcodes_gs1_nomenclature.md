# Módulo: Barcode - GS1 Nomenclature

## Información General
- **Nombre técnico:** barcodes_gs1_nomenclature
- **Versión:** 1.0
- **Categoría:** Hidden
- **Dependencias:** barcodes, uom


## Propósito
Parse barcodes according to the GS1-128 specifications





## Modelos

### barcode.nomenclature


- Hereda de:

  - barcode.nomenclature




#### Campos
- **is_gs1_nomenclature** (Boolean)
- **gs1_separator_fnc1** (Char)





### barcode.rule


- Hereda de:

  - barcode.rule




#### Campos
- **encoding** (Selection)
- **type** (Selection)
- **is_gs1_nomenclature** (Boolean)
- **gs1_content_type** (Selection)
- **gs1_decimal_usage** (Boolean) → Decimal
- **associated_uom_id** (Many2one) → uom.uom





### ir.http


- Hereda de:

  - ir.http




- No agrega campos






