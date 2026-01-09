# Módulo: Project Purchase

## Información General
- **Nombre técnico:** project_purchase
- **Versión:** 1.0
- **Categoría:** Services/Project
- **Dependencias:** purchase, project_account


## Propósito
Monitor purchase in project





## Modelos

### purchase.order


- Hereda de:

  - purchase.order




- Campos:

  - **project_id** (Many2one) → project.project





### project.project


- Hereda de:

  - project.project




- Campos:

  - **purchase_orders_count** (Integer) → # Purchase Orders





### purchase.order.line


- Hereda de:

  - purchase.order.line




- No agrega campos





