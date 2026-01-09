# Módulo: Accounting/Fleet bridge

## Información General
- **Nombre técnico:** account_fleet
- **Versión:** 1.0
- **Categoría:** Accounting/Accounting
- **Dependencias:** fleet, account


## Propósito
Manage accounting with fleets





## Modelos

### fleet.vehicle


- Hereda de:

  - fleet.vehicle




- Campos:

  - **bill_count** (Integer)


  - **account_move_ids** (One2many) → account.move





### fleet.vehicle.log.services


- Hereda de:

  - fleet.vehicle.log.services




- Campos:

  - **account_move_line_id** (Many2one) → account.move.line


  - **account_move_state** (Selection)


  - **amount** (Monetary)


  - **vehicle_id** (Many2one) → fleet.vehicle





### account.move


- Hereda de:

  - account.move




- No agrega campos



### account.move.line


- Hereda de:

  - account.move.line




- Campos:

  - **vehicle_id** (Many2one) → fleet.vehicle


  - **need_vehicle** (Boolean)


  - **vehicle_log_service_ids** (One2many) → fleet.vehicle.log.services







