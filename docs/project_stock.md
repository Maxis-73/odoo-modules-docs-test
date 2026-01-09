# Módulo: Project Stock

## Información General
- **Nombre técnico:** project_stock
- **Versión:** 1.0
- **Categoría:** Services/Project
- **Dependencias:** stock, project


## Propósito
Link Stock pickings to Project





## Modelos

### project.project


- Hereda de:

  - project.project




- No agrega campos



### stock.picking


- Hereda de:

  - stock.picking




- Campos:

  - **project_id** (Many2one) → project.project







