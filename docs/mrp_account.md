# Módulo: Accounting - MRP

## Información General
- **Nombre técnico:** mrp_account
- **Versión:** 1.0
- **Categoría:** Manufacturing/Manufacturing
- **Dependencias:** mrp, stock_account


## Propósito
Analytic accounting in Manufacturing



## Descripción

Analytic Accounting in MRP
==========================

* Cost structure report

Also, allows to compute the cost of the product based on its BoM, using the costs of its components and work center operations.
It adds a button on the product itself but also an action in the list view of the products.
If the automated inventory valuation is active, the necessary accounting entries will be created.





## Modelos

### mrp.production


- Hereda de:

  - mrp.production




#### Campos
- **extra_cost** (Float)
- **show_valuation** (Boolean)





### stock.move


- Hereda de:

  - stock.move




- No agrega campos




### mrp.workorder


- Hereda de:

  - mrp.workorder




#### Campos
- **mo_analytic_account_line_ids** (Many2many) → account.analytic.line
- **wc_analytic_account_line_ids** (Many2many) → account.analytic.line





### account.move


- Hereda de:

  - account.move




#### Campos
- **wip_production_ids** (Many2many) → mrp.production
- **wip_production_count** (Integer) → Manufacturing Orders Count





### account.move.line


- Hereda de:

  - account.move.line




- No agrega campos




### mrp.routing.workcenter


- Hereda de:

  - mrp.routing.workcenter




- No agrega campos




### mrp.workcenter


- Hereda de:


  - mrp.workcenter

  - analytic.mixin





#### Campos
- **costs_hour_account_ids** (Many2many) → account.analytic.account
- **expense_account_id** (Many2one) → account.account





### mrp.workcenter.productivity


- Hereda de:

  - mrp.workcenter.productivity




#### Campos
- **account_move_line_id** (Many2one) → account.move.line





### product.template


- Hereda de:

  - product.template




- No agrega campos




### product.product


- Hereda de:

  - product.product




- No agrega campos




### product.category


- Hereda de:

  - product.category




#### Campos
- **property_stock_account_production_cost_id** (Many2one) → account.account





### account.analytic.account


- Hereda de:

  - account.analytic.account




#### Campos
- **production_ids** (Many2many) → mrp.production
- **production_count** (Integer) → Manufacturing Orders Count
- **bom_ids** (Many2many) → mrp.bom
- **bom_count** (Integer) → BoM Count
- **workcenter_ids** (Many2many) → mrp.workcenter
- **workorder_count** (Integer) → Work Order Count





### account.analytic.line


- Hereda de:

  - account.analytic.line




#### Campos
- **category** (Selection)





### account.analytic.applicability


- Hereda de:

  - account.analytic.applicability




#### Campos
- **business_domain** (Selection)










## Vistas Adicionales


### mrp.account.wip.accounting

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | Post WIP Accounting Entry | `mrp_account.view_wip_accounting_form` | - |



**Botones (mrp_account.view_wip_accounting_form):**
- **Post WIP** (object)



