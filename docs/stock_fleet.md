# Módulo: Stock Transport

## Información General
- **Nombre técnico:** stock_fleet
- **Versión:** 1.0
- **Categoría:** N/A
- **Dependencias:** stock_picking_batch, fleet


## Propósito
Stock Transport: Dispatch Management System



## Descripción
Transport Management: organize packs in your fleet, or carriers.



## Modelos

### stock.picking.batch


- Hereda de:

  - stock.picking.batch




#### Campos
- **vehicle_id** (Many2one) → fleet.vehicle
- **vehicle_category_id** (Many2one) → fleet.vehicle.model.category
- **dock_id** (Many2one) → stock.location
- **vehicle_weight_capacity** (Float)
- **weight_uom_name** (Char)
- **vehicle_volume_capacity** (Float)
- **volume_uom_name** (Char)
- **driver_id** (Many2one) → res.partner
- **used_weight_percentage** (Float)
- **used_volume_percentage** (Float)
- **end_date** (Datetime) → End Date





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| pivot | stock.picking.batch.pivot | `stock_fleet.stock_picking_batch_pivot` | - |
| graph | stock.picking.batch.graph | `stock_fleet.stock_picking_batch_graph` | - |




### fleet.vehicle.model.category


- Hereda de:

  - fleet.vehicle.model.category




#### Campos
- **weight_capacity** (Float)
- **weight_capacity_uom_name** (Char)
- **volume_capacity** (Float)
- **volume_capacity_uom_name** (Char)





### stock.location


- Hereda de:

  - stock.location




#### Campos
- **is_a_dock** (Boolean) → Is a Dock Location





### stock.picking


- Hereda de:

  - stock.picking




#### Campos
- **zip** (Char)










