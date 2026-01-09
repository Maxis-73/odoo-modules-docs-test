# Módulo: WMS Accounting

## Información General
- **Nombre técnico:** stock_account
- **Versión:** 1.1
- **Categoría:** Hidden
- **Dependencias:** stock, account


## Propósito
Inventory, Logistic, Valuation, Accounting



## Descripción

WMS Accounting module
This module makes the link between the 'stock' and 'account' modules and allows you to create accounting entries to value your stock movements

Key Features
------------
* Stock Valuation (periodical or automatic)
* Invoice from Picking

Dashboard / Reports for Warehouse Management includes:
------------------------------------------------------
* Stock Inventory Value at given date (support dates in the past)
    



## Modelos

### stock.move


- Hereda de:

  - stock.move




- Campos:

  - **to_refund** (Boolean)


  - **account_move_ids** (One2many) → account.move


  - **stock_valuation_layer_ids** (One2many) → stock.valuation.layer


  - **analytic_account_line_ids** (Many2many) → account.analytic.line





### stock.quant


- Hereda de:

  - stock.quant




- Campos:

  - **value** (Monetary) → Value


  - **currency_id** (Many2one) → res.currency


  - **accounting_date** (Date) → Accounting Date


  - **cost_method** (Selection)





### account.move


- Hereda de:

  - account.move




- Campos:

  - **stock_move_id** (Many2one) → stock.move


  - **stock_valuation_layer_ids** (One2many) → stock.valuation.layer





### account.move.line


- Hereda de:

  - account.move.line




- Campos:

  - **stock_valuation_layer_ids** (One2many) → stock.valuation.layer


  - **cogs_origin_id** (Many2one) → account.move.line





### stock.valuation.layer


- Hereda de: Base



- Campos:

  - **company_id** (Many2one) → res.company


  - **product_id** (Many2one) → product.product


  - **categ_id** (Many2one) → product.category


  - **product_tmpl_id** (Many2one) → product.template


  - **quantity** (Float) → Quantity


  - **uom_id** (Many2one)


  - **currency_id** (Many2one) → res.currency


  - **unit_cost** (Float) → Unit Value


  - **value** (Monetary) → Total Value


  - **remaining_qty** (Float)


  - **remaining_value** (Monetary) → Remaining Value


  - **description** (Char) → Description


  - **stock_valuation_layer_id** (Many2one) → stock.valuation.layer


  - **stock_valuation_layer_ids** (One2many) → stock.valuation.layer


  - **stock_move_id** (Many2one) → stock.move


  - **account_move_id** (Many2one) → account.move


  - **account_move_line_id** (Many2one) → account.move.line


  - **reference** (Char)


  - **price_diff_value** (Float) → Invoice value correction with invoice currency


  - **warehouse_id** (Many2one) → stock.warehouse


  - **lot_id** (Many2one) → stock.lot





### stock.location


- Hereda de:

  - stock.location




- Campos:

  - **valuation_in_account_id** (Many2one) → account.account


  - **valuation_out_account_id** (Many2one) → account.account





### account.chart.template


- Hereda de:

  - account.chart.template




- No agrega campos



### stock.picking


- Hereda de:

  - stock.picking




- Campos:

  - **country_code** (Char)





### product.template


- Hereda de:

  - product.template




- Campos:

  - **cost_method** (Selection)


  - **valuation** (Selection)


  - **lot_valuated** (Boolean) → Valuation by Lot/Serial number





### product.product


- Hereda de:

  - product.product




- Campos:

  - **value_svl** (Float)


  - **quantity_svl** (Float)


  - **avg_cost** (Monetary)


  - **total_value** (Monetary)


  - **company_currency_id** (Many2one) → res.currency


  - **stock_valuation_layer_ids** (One2many) → stock.valuation.layer


  - **valuation** (Selection)


  - **cost_method** (Selection)





### product.category


- Hereda de:

  - product.category




- Campos:

  - **property_valuation** (Selection)


  - **property_cost_method** (Selection)


  - **property_stock_journal** (Many2one) → account.journal


  - **property_stock_account_input_categ_id** (Many2one) → account.account


  - **property_stock_account_output_categ_id** (Many2one) → account.account


  - **property_stock_valuation_account_id** (Many2one) → account.account





### account.analytic.plan


- Hereda de:

  - account.analytic.plan




- No agrega campos



### account.analytic.account


- Hereda de:

  - account.analytic.account




- No agrega campos



### res.config.settings


- Hereda de:

  - res.config.settings




- Campos:

  - **module_stock_landed_costs** (Boolean) → Landed Costs


  - **group_lot_on_invoice** (Boolean) → Display Lots & Serial Numbers on Invoices


  - **group_stock_accounting_automatic** (Boolean) → Automatic Stock Accounting





### stock.move.line


- Hereda de:

  - stock.move.line




- No agrega campos



### res.company


- Hereda de:

  - res.company




- Campos:

  - **account_production_wip_account_id** (Many2one) → account.account


  - **account_production_wip_overhead_account_id** (Many2one) → account.account





### account.chart.template


- Hereda de:

  - account.chart.template




- No agrega campos



### stock.lot


- Hereda de:

  - stock.lot




- Campos:

  - **value_svl** (Float)


  - **quantity_svl** (Float)


  - **avg_cost** (Monetary)


  - **total_value** (Monetary)


  - **company_currency_id** (Many2one) → res.currency


  - **stock_valuation_layer_ids** (One2many) → stock.valuation.layer


  - **standard_price** (Float) → Cost








## Vistas


### stock.valuation.layer

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | stock.valuation.layer.form | `stock_account.stock_valuation_layer_form` | - |
| list | stock.valuation.layer.list | `stock_account.stock_valuation_layer_tree` | - |
| pivot | stock.valuation.layer.pivot | `stock_account.stock_valuation_layer_pivot` | - |
| graph | inventory.aging.graph | `stock_account.stock_valuation_layer_graph` | - |
| search | Inventory Valuation | `stock_account.view_inventory_valuation_search` | - |



#### Filtros de búsqueda (stock_account.view_inventory_valuation_search)

**Filtros:**
- **Incoming** (`[('stock_move_id.location_id.usage', 'not in', ('internal', 'transit')), ('stock_move_id.location_dest_id.usage', 'in', ('internal', 'transit'))]`)
- **Outgoing** (`[('stock_move_id.location_id.usage', 'in', ('internal', 'transit')), ('stock_move_id.location_dest_id.usage', 'not in', ('internal', 'transit'))]`)
- **Has Remaining Qty** (`[('remaining_qty', '>', 0)]`)


**Agrupar por:**
- Product
- Lot/Serial Number
- Product Category
- Date
- Company


### stock.valuation.layer.revaluation

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | stock.valuation.layer.revaluation.form | `stock_account.stock_valuation_layer_revaluation_form_view` | - |



#### Botones (stock_account.stock_valuation_layer_revaluation_form_view)
- **Revalue** (object)

