# Módulo: MRP Project

## Información General
- **Nombre técnico:** project_mrp
- **Versión:** 1.0
- **Categoría:** Services/Project
- **Dependencias:** mrp, project


## Propósito
Monitor MRP using project





## Modelos

### mrp.bom


- Hereda de:

  - mrp.bom




#### Campos
- **project_id** (Many2one) → project.project





### mrp.production


- Hereda de:

  - mrp.production




#### Campos
- **project_id** (Many2one) → project.project





### project.project


- Hereda de:

  - project.project




#### Campos
- **bom_count** (Integer)
- **production_count** (Integer)





### stock.rule


- Hereda de:

  - stock.rule




- No agrega campos




### stock.move


- Hereda de:

  - stock.move




- No agrega campos






