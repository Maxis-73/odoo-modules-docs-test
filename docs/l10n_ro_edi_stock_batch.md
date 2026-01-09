# Módulo: Romania - E-Transport Batch Pickings

## Información General
- **Nombre técnico:** l10n_ro_edi_stock_batch
- **Versión:** 1.0
- **Categoría:** Accounting/Localizations/EDI
- **Dependencias:** l10n_ro_edi_stock, stock_picking_batch




## Descripción

E-Transport implementation for Batch Pickings in Romania
    



## Modelos

### stock.picking.batch


- Hereda de:

  - stock.picking.batch




- Campos:

  - **l10n_ro_edi_stock_document_ids** (One2many) → l10n_ro_edi.document


  - **l10n_ro_edi_stock_document_uit** (Char)


  - **l10n_ro_edi_stock_state** (Selection)


  - **l10n_ro_edi_stock_operation_type** (Selection)


  - **l10n_ro_edi_stock_available_operation_scopes** (Char)


  - **l10n_ro_edi_stock_operation_scope** (Selection)


  - **l10n_ro_edi_stock_vehicle_number** (Char)


  - **l10n_ro_edi_stock_trailer_1_number** (Char)


  - **l10n_ro_edi_stock_trailer_2_number** (Char)


  - **l10n_ro_edi_stock_available_start_loc_types** (Char)


  - **l10n_ro_edi_stock_start_loc_type** (Selection)


  - **l10n_ro_edi_stock_available_end_loc_types** (Char)


  - **l10n_ro_edi_stock_end_loc_type** (Selection)


  - **l10n_ro_edi_stock_start_bcp** (Selection)


  - **l10n_ro_edi_stock_start_customs_office** (Selection)


  - **l10n_ro_edi_stock_end_bcp** (Selection)


  - **l10n_ro_edi_stock_end_customs_office** (Selection)


  - **l10n_ro_edi_stock_remarks** (Text)


  - **l10n_ro_edi_stock_enable** (Boolean)


  - **l10n_ro_edi_stock_enable_send** (Boolean)


  - **l10n_ro_edi_stock_enable_fetch** (Boolean)


  - **l10n_ro_edi_stock_enable_amend** (Boolean)


  - **l10n_ro_edi_stock_fields_readonly** (Boolean)





### l10n_ro_edi.document


- Hereda de:

  - l10n_ro_edi.document




- Campos:

  - **batch_id** (Many2one) → stock.picking.batch





### stock.picking


- Hereda de:

  - stock.picking




- No agrega campos






## Vistas


### stock.picking.batch

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | stock.picking.batch.form.inherit.l10n_ro_edi_stock | `l10n_ro_edi_stock_batch.l10n_ro_edi_stock_view_batch_form` | stock_picking_batch.stock_picking_batch_form |


