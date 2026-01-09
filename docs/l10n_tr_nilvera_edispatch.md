# Módulo: Türkiye - e-Irsaliye (e-Dispatch)

## Información General
- **Nombre técnico:** l10n_tr_nilvera_edispatch
- **Versión:** 1.0
- **Categoría:** Accounting/Localizations
- **Dependencias:** l10n_tr_nilvera, stock




## Descripción
Allows the users to create the UBL 1.2.1 e-Dispatch file



## Modelos

### stock.picking


- Hereda de:

  - stock.picking




- Campos:

  - **l10n_tr_nilvera_dispatch_type** (Selection)


  - **l10n_tr_nilvera_carrier_id** (Many2one) → res.partner


  - **l10n_tr_nilvera_buyer_id** (Many2one) → res.partner


  - **l10n_tr_nilvera_seller_supplier_id** (Many2one) → res.partner


  - **l10n_tr_nilvera_buyer_originator_id** (Many2one) → res.partner


  - **l10n_tr_nilvera_delivery_printed_number** (Char)


  - **l10n_tr_nilvera_delivery_date** (Date)


  - **l10n_tr_vehicle_plate** (Many2one) → l10n_tr.nilvera.trailer.plate


  - **l10n_tr_nilvera_trailer_plate_ids** (Many2many) → l10n_tr.nilvera.trailer.plate


  - **l10n_tr_nilvera_driver_ids** (Many2many) → res.partner


  - **l10n_tr_nilvera_delivery_notes** (Char)


  - **l10n_tr_nilvera_dispatch_state** (Selection)


  - **l10n_tr_nilvera_edispatch_warnings** (Json)





### stock.picking.type


- Hereda de:

  - stock.picking.type




- No agrega campos



### l10n_tr.nilvera.trailer.plate


- Hereda de: Base



- Campos:

  - **name** (Char)


  - **plate_number_type** (Selection)





### res.partner


- Hereda de:

  - res.partner




- Campos:

  - **l10n_tr_nilvera_edispatch_customs_zip** (Char)








## Vistas


### stock.picking

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | stock.picking.view.list.inherit | `l10n_tr_nilvera_edispatch.vpicktree_inherit_l10n_tr_nilvera_edispatch` | stock.vpicktree |



### l10n_tr.nilvera.trailer.plate

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | l10n_tr.nilvera.trailer.plate.tree | `l10n_tr_nilvera_edispatch.l10n_tr_nilvera_trailer_plate_view_tree` | - |
| form | l10n_tr.nilvera.trailer.plate.form | `l10n_tr_nilvera_edispatch.l10n_tr_nilvera_trailer_plate_view_form` | - |


