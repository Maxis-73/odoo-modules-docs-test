# Módulo: Test - Import & Export

## Información General
- **Nombre técnico:** test_import_export
- **Versión:** 1.0
- **Categoría:** Hidden
- **Dependencias:** web, base_import, website


## Propósito
Base Import & Export Tests: Ensure Flow Robustness



## Descripción
This module contains tests related to base import and export.



## Modelos

### export.one2many.child


- Hereda de: Base



- Campos:

  - **parent_id** (Many2one) → export.one2many


  - **str** (Char)


  - **m2o** (Many2one) → export.integer


  - **value** (Integer)





### export.one2many.multiple


- Hereda de: Base



- Campos:

  - **parent_id** (Many2one) → export.one2many.recursive


  - **const** (Integer)


  - **child1** (One2many) → export.one2many.child.1


  - **child2** (One2many) → export.one2many.child.2





### export.one2many.multiple.child


- Hereda de: Base



- Campos:

  - **parent_id** (Many2one) → export.one2many.multiple


  - **str** (Char)


  - **value** (Integer)





### export.one2many.child.1


- Hereda de:

  - export.one2many.multiple.child




- No agrega campos



### export.one2many.child.2


- Hereda de:

  - export.one2many.multiple.child




- No agrega campos



### export.many2many.other


- Hereda de: Base



- Campos:

  - **str** (Char)


  - **value** (Integer)





### export.selection.withdefault


- Hereda de: Base



- Campos:

  - **const** (Integer)


  - **value** (Selection)





### export.one2many.recursive


- Hereda de: Base



- Campos:

  - **value** (Integer)


  - **child** (One2many) → export.one2many.multiple





### export.unique


- Hereda de: Base



- Campos:

  - **value** (Integer)


  - **value2** (Integer)


  - **value3** (Integer)





### export.inherits.parent


- Hereda de: Base



- Campos:

  - **value_parent** (Integer)





### export.inherits.child


- Hereda de: Base



- Campos:

  - **parent_id** (Many2one) → export.inherits.parent


  - **value** (Integer)





### export.m2o.str


- Hereda de: Base



- Campos:

  - **child_id** (Many2one) → export.m2o.str.child





### export.m2o.str.child


- Hereda de: Base



- Campos:

  - **name** (Char)





### export.with.required.field


- Hereda de: Base



- Campos:

  - **name** (Char)


  - **value** (Integer)





### export.many2one.required.subfield


- Hereda de: Base



- Campos:

  - **name** (Many2one) → export.with.required.field





### export.aggregator


- Hereda de: Base



- Campos:

  - **int_sum** (Integer)


  - **int_max** (Integer)


  - **float_min** (Float)


  - **float_avg** (Float)


  - **float_monetary** (Monetary)


  - **currency_id** (Many2one) → res.currency


  - **date_max** (Date)


  - **bool_and** (Boolean)


  - **bool_or** (Boolean)


  - **many2one** (Many2one) → export.integer


  - **one2many** (One2many) → export.aggregator.one2many


  - **active** (Boolean)


  - **parent_id** (Many2one) → export.aggregator


  - **definition_properties** (PropertiesDefinition) → Definitions


  - **properties** (Properties) → Properties





### export.aggregator.one2many


- Hereda de: Base



- Campos:

  - **name** (Char)


  - **parent_id** (Many2one) → export.aggregator


  - **value** (Integer)


  - **active** (Boolean)





### import.char


- Hereda de: Base



- Campos:

  - **value** (Char)





### import.char.required


- Hereda de: Base



- Campos:

  - **value** (Char)





### import.char.readonly


- Hereda de: Base



- Campos:

  - **value** (Char)





### import.char.noreadonly


- Hereda de: Base



- Campos:

  - **value** (Char)





### import.char.stillreadonly


- Hereda de: Base



- Campos:

  - **value** (Char)





### import.m2o


- Hereda de: Base



- Campos:

  - **value** (Many2one) → import.m2o.related





### import.m2o.related


- Hereda de: Base



- Campos:

  - **value** (Integer)





### import.m2o.required


- Hereda de: Base



- Campos:

  - **value** (Many2one) → import.m2o.required.related





### import.m2o.required.related


- Hereda de: Base



- Campos:

  - **value** (Integer)





### import.o2m


- Hereda de: Base



- Campos:

  - **name** (Char)


  - **value** (One2many) → import.o2m.child





### import.o2m.child


- Hereda de: Base



- Campos:

  - **parent_id** (Many2one) → import.o2m


  - **value** (Integer)





### import.preview


- Hereda de: Base



- Campos:

  - **name** (Char) → Name


  - **somevalue** (Integer)


  - **othervalue** (Integer)





### import.float


- Hereda de: Base



- Campos:

  - **value** (Float)


  - **value2** (Monetary)


  - **currency_id** (Many2one) → res.currency





### import.complex


- Hereda de: Base



- Campos:

  - **f** (Float)


  - **m** (Monetary)


  - **c** (Char)


  - **currency_id** (Many2one) → res.currency


  - **d** (Date)


  - **dt** (Datetime)


  - **parent_id** (Many2one) → import.complex





### import.properties.definition


- Hereda de: Base



- Campos:

  - **properties_definition** (PropertiesDefinition)


  - **record_properties_ids** (One2many) → import.properties


  - **main_properties_record_id** (Many2one) → import.properties





### import.properties


- Hereda de: Base



- Campos:

  - **properties** (Properties)


  - **record_definition_id** (Many2one) → import.properties.definition





### import.properties.inherits


- Hereda de: Base



- Campos:

  - **parent_id** (Many2one) → import.properties





### import.path.properties


- Hereda de: Base



- Campos:

  - **properties_id** (Many2one) → import.properties


  - **another_properties_id** (Many2one) → import.properties


  - **all_properties_ids** (Many2many) → import.properties







