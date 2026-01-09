# Módulo: MRP Subcontracting

## Información General
- **Nombre técnico:** mrp_subcontracting
- **Versión:** 0.1
- **Categoría:** Manufacturing/Manufacturing
- **Dependencias:** mrp


## Propósito
Subcontract Productions





## Modelos

### mrp.bom


- Hereda de:

  - mrp.bom




#### Campos
- **type** (Selection)
- **subcontractor_ids** (Many2many) → res.partner





### stock.warehouse


- Hereda de:

  - stock.warehouse




#### Campos
- **subcontracting_to_resupply** (Boolean) → Resupply Subcontractors
- **subcontracting_mto_pull_id** (Many2one) → stock.rule
- **subcontracting_pull_id** (Many2one) → stock.rule
- **subcontracting_route_id** (Many2one) → stock.route
- **subcontracting_type_id** (Many2one) → stock.picking.type
- **subcontracting_resupply_type_id** (Many2one) → stock.picking.type





### mrp.production


- Hereda de:

  - mrp.production




#### Campos
- **move_line_raw_ids** (One2many) → stock.move.line
- **subcontracting_has_been_recorded** (Boolean) → Has been recorded?
- **subcontractor_id** (Many2one) → res.partner
- **bom_product_ids** (Many2many) → product.product
- **incoming_picking** (Many2one)





### stock.move


- Hereda de:

  - stock.move




#### Campos
- **is_subcontract** (Boolean) → The move is a subcontract receipt
- **show_subcontracting_details_visible** (Boolean)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | mrp.subcontracting.move.form.view | `mrp_subcontracting.mrp_subcontracting_move_form_view` | - |
| list | mrp.subcontracting.move.list.view | `mrp_subcontracting.mrp_subcontracting_move_tree_view` | - |




### stock.quant


- Hereda de:

  - stock.quant




#### Campos
- **is_subcontract** (Boolean)





### stock.location


- Hereda de:

  - stock.location




#### Campos
- **is_subcontracting_location** (Boolean) → Is a Subcontracting Location?
- **subcontractor_ids** (One2many) → res.partner





### stock.rule


- Hereda de:

  - stock.rule




- No agrega campos




### stock.picking


- Hereda de:

  - stock.picking




#### Campos
- **move_line_ids_without_package** (One2many)
- **display_action_record_components** (Selection)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | subcontracting.portal.production.view.form | `mrp_subcontracting.subcontracting_portal_production_form_view` | - |



**Botones (mrp_subcontracting.subcontracting_portal_production_form_view):**
- **action_show_details** (object)
- **Register components for subcontracted product** (object)



### product.supplierinfo


- Hereda de:

  - product.supplierinfo




#### Campos
- **is_subcontractor** (Boolean) → Subcontracted





### product.product


- Hereda de:

  - product.product




- No agrega campos




### stock.move.line


- Hereda de:

  - stock.move.line




- No agrega campos




#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | mrp.subcontracting.stock.move.line.list.view | `mrp_subcontracting.mrp_subcontracting_stock_move_line_tree_view` | - |




### res.company


- Hereda de:

  - res.company




#### Campos
- **subcontracting_location_id** (Many2one) → stock.location





### mrp.production


- Hereda de:

  - mrp.production




- No agrega campos




### res.partner


- Hereda de:

  - res.partner




#### Campos
- **property_stock_subcontractor** (Many2one) → stock.location
- **is_subcontractor** (Boolean)
- **bom_ids** (Many2many) → mrp.bom
- **production_ids** (Many2many) → mrp.production
- **picking_ids** (Many2many) → stock.picking





### stock.replenish.mixin


- Hereda de:

  - stock.replenish.mixin




- No agrega campos









