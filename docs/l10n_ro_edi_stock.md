# Módulo: Romania - E-Transport

## Información General
- **Nombre técnico:** l10n_ro_edi_stock
- **Versión:** 1.0
- **Categoría:** Accounting/Localizations/EDI
- **Dependencias:** stock_delivery, l10n_ro_edi




## Descripción

E-Transport implementation for Romania
    



## Modelos

### delivery.carrier


- Hereda de:

  - delivery.carrier




- Campos:

  - **l10n_ro_edi_stock_partner_id** (Many2one) → res.partner





### l10n_ro_edi.document


- Hereda de:

  - l10n_ro_edi.document




- Campos:

  - **invoice_id** (Many2one)


  - **picking_id** (Many2one) → stock.picking


  - **state** (Selection)


  - **message** (Char)


  - **l10n_ro_edi_stock_uit** (Char)


  - **l10n_ro_edi_stock_load_id** (Char)





### stock.picking


- Hereda de:

  - stock.picking




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








## Vistas


### stock.picking

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | stock.picking.form.inherit.l10n_ro_edi_stock | `l10n_ro_edi_stock.l10n_ro_edi_stock_view_picking_form` | stock.view_picking_form |


