# Módulo: Landed Costs On MO

## Información General
- **Nombre técnico:** mrp_landed_costs
- **Versión:** 1.0
- **Categoría:** Manufacturing/Manufacturing
- **Dependencias:** stock_landed_costs, mrp


## Propósito
Landed Costs on Manufacturing Order



## Descripción

This module allows you to easily add extra costs on manufacturing order 
and decide the split of these costs among their stock moves in order to 
take them into account in your stock valuation.
    



## Modelos

### stock.landed.cost


- Hereda de:

  - stock.landed.cost




#### Campos
- **target_model** (Selection)
- **mrp_production_ids** (Many2many) → mrp.production







