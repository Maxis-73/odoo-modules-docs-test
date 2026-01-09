# Módulo: Purchase Repair

## Información General
- **Nombre técnico:** purchase_repair
- **Versión:** 1.0
- **Categoría:** Repair/Purchase
- **Dependencias:** repair, purchase_stock


## Propósito
Keep track of linked purchase and repair orders





## Modelos

### purchase.order


- Hereda de:

  - purchase.order




- Campos:

  - **repair_count** (Integer)





### repair.order


- Hereda de:

  - repair.order




- Campos:

  - **purchase_count** (Integer)







