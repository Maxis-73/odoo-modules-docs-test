# Módulo: Sparse Fields

## Información General
- **Nombre técnico:** base_sparse_field
- **Versión:** 1.0
- **Categoría:** Hidden
- **Dependencias:** base


## Propósito
Implementation of sparse fields.



## Descripción

The purpose of this module is to implement "sparse" fields, i.e., fields
that are mostly null. This implementation circumvents the PostgreSQL
limitation on the number of columns in a table. The values of all sparse
fields are stored in a "serialized" field in the form of a JSON mapping.
    



## Modelos

### base


- Hereda de:

  - base




- No agrega campos




### ir.model.fields


- Hereda de:

  - ir.model.fields




#### Campos
- **ttype** (Selection)
- **serialization_field_id** (Many2one) → ir.model.fields





### sparse_fields.test


- Hereda de: Base



#### Campos
- **data** (Serialized)
- **boolean** (Boolean)
- **integer** (Integer)
- **float** (Float)
- **char** (Char)
- **selection** (Selection)
- **partner** (Many2one) → res.partner







