# Módulo: Project Stock Account

## Información General
- **Nombre técnico:** project_stock_account
- **Versión:** 1.0
- **Categoría:** Services/Project
- **Dependencias:** stock_account, project_stock


## Propósito
Handle analytics in Stock pickings with Project





## Modelos

### account.analytic.line


- Hereda de:

  - account.analytic.line




#### Campos
- **category** (Selection)





### stock.move


- Hereda de:

  - stock.move




- No agrega campos




### account.analytic.applicability


- Hereda de:

  - account.analytic.applicability




#### Campos
- **business_domain** (Selection)





### project.project


- Hereda de:

  - project.project




- No agrega campos




### stock.picking.type


- Hereda de:

  - stock.picking.type




#### Campos
- **analytic_costs** (Boolean)







