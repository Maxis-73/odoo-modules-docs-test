# Módulo: WMS Landed Costs

## Información General
- **Nombre técnico:** stock_landed_costs
- **Versión:** 1.1
- **Categoría:** Inventory/Inventory
- **Dependencias:** stock_account, purchase_stock


## Propósito
Landed Costs



## Descripción

Landed Costs Management
=======================
This module allows you to easily add extra costs on pickings and decide the split of these costs among their stock moves in order to take them into account in your stock valuation.
    



## Modelos

### stock.landed.cost


- Hereda de:


  - mail.thread

  - mail.activity.mixin





#### Campos
- **name** (Char) → Name
- **date** (Date) → Date
- **target_model** (Selection)
- **picking_ids** (Many2many) → stock.picking
- **cost_lines** (One2many) → stock.landed.cost.lines
- **valuation_adjustment_lines** (One2many) → stock.valuation.adjustment.lines
- **description** (Text) → Item Description
- **amount_total** (Monetary) → Total
- **state** (Selection)
- **account_move_id** (Many2one) → account.move
- **account_journal_id** (Many2one) → account.journal
- **company_id** (Many2one) → res.company
- **stock_valuation_layer_ids** (One2many) → stock.valuation.layer
- **vendor_bill_id** (Many2one) → account.move
- **currency_id** (Many2one) → res.currency





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | stock.landed.cost.form | `stock_landed_costs.view_stock_landed_cost_form` | - |
| list | stock.landed.cost.list | `stock_landed_costs.view_stock_landed_cost_tree` | - |
| list | stock.landed.cost.list | `stock_landed_costs.view_stock_landed_cost_tree2` | - |
| kanban | stock.landed.cost.kanban | `stock_landed_costs.stock_landed_cost_view_kanban` | - |
| search | stock.landed.cost.search | `stock_landed_costs.view_stock_landed_cost_search` | - |



**Botones (stock_landed_costs.view_stock_landed_cost_form):**
- **Validate** (object)
- **Cancel** (object)
- **action_view_stock_valuation_layers** (object) - Grupos: `account.group_account_invoice`
- **Compute** (object)


**Filtros de búsqueda (stock_landed_costs.view_stock_landed_cost_search):**

- **Draft** (`[('state', '=', 'draft')]`)
- **Done** (`[('state', '=', 'done')]`)
- **Date**
- **Late Activities** (`[('my_activity_date_deadline', '<', context_today().strftime('%Y-%m-%d'))]`)
- **Today Activities** (`[('my_activity_date_deadline', '=', context_today().strftime('%Y-%m-%d'))]`)
- **Future Activities** (`[('my_activity_date_deadline', '>', context_today().strftime('%Y-%m-%d'))]`)


*Agrupar por:*
- Status
- Date



### stock.landed.cost.lines


- Hereda de: Base



#### Campos
- **name** (Char) → Description
- **cost_id** (Many2one) → stock.landed.cost
- **product_id** (Many2one) → product.product
- **price_unit** (Monetary) → Cost
- **split_method** (Selection)
- **account_id** (Many2one) → account.account
- **currency_id** (Many2one) → res.currency





### stock.valuation.adjustment.lines


- Hereda de: Base



#### Campos
- **name** (Char) → Description
- **cost_id** (Many2one) → stock.landed.cost
- **cost_line_id** (Many2one) → stock.landed.cost.lines
- **move_id** (Many2one) → stock.move
- **product_id** (Many2one) → product.product
- **quantity** (Float) → Quantity
- **weight** (Float) → Weight
- **volume** (Float) → Volume
- **former_cost** (Monetary) → Original Value
- **additional_landed_cost** (Monetary) → Additional Landed Cost
- **final_cost** (Monetary) → New Value
- **currency_id** (Many2one) → res.currency





### stock.move


- Hereda de:

  - stock.move




- No agrega campos




### account.move


- Hereda de:

  - account.move




#### Campos
- **landed_costs_ids** (One2many) → stock.landed.cost
- **landed_costs_visible** (Boolean)





### account.move.line


- Hereda de:

  - account.move.line




#### Campos
- **product_type** (Selection)
- **is_landed_costs_line** (Boolean)





### stock.valuation.layer


- Hereda de:

  - stock.valuation.layer




#### Campos
- **stock_landed_cost_id** (Many2one) → stock.landed.cost





### purchase.order.line


- Hereda de:

  - purchase.order.line




- No agrega campos




### product.template


- Hereda de:

  - product.template




#### Campos
- **landed_cost_ok** (Boolean) → Is a Landed Cost
- **split_method_landed_cost** (Selection)





### res.config.settings


- Hereda de:

  - res.config.settings




#### Campos
- **lc_journal_id** (Many2one) → account.journal





### res.company


- Hereda de:

  - res.company




#### Campos
- **lc_journal_id** (Many2one) → account.journal










