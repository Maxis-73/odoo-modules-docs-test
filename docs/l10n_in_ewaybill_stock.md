# Módulo: Indian - E-waybill Stock

## Información General
- **Nombre técnico:** l10n_in_ewaybill_stock
- **Versión:** 1.0
- **Categoría:** Accounting/Localizations/EDI
- **Dependencias:** l10n_in_stock, l10n_in_edi_ewaybill




## Descripción

Indian E-waybill for Stock

This module enables users to create E-waybill from Inventory App without generating an invoice
    



## Modelos

### stock.move


- Hereda de:

  - stock.move




- Campos:

  - **l10n_in_ewaybill_id** (One2many)


  - **company_currency_id** (Many2one)


  - **ewaybill_price_unit** (Monetary)


  - **ewaybill_tax_ids** (Many2many) → account.tax





### stock.picking


- Hereda de:

  - stock.picking




- Campos:

  - **l10n_in_ewaybill_id** (One2many) → l10n.in.ewaybill





### l10n.in.ewaybill


- Hereda de:


  - portal.mixin

  - mail.thread

  - mail.activity.mixin





- Campos:

  - **name** (Char) → e-Waybill Number


  - **ewaybill_date** (Date) → e-Waybill Date


  - **ewaybill_expiry_date** (Date) → e-Waybill Valid Upto


  - **state** (Selection)


  - **picking_id** (Many2one) → stock.picking


  - **move_ids** (One2many)


  - **picking_type_code** (Selection)


  - **document_date** (Datetime) → Document Date


  - **document_number** (Char) → Document


  - **company_id** (Many2one) → res.company


  - **company_currency_id** (Many2one)


  - **supply_type** (Selection)


  - **partner_bill_from_id** (Many2one) → res.partner


  - **partner_bill_to_id** (Many2one) → res.partner


  - **partner_ship_from_id** (Many2one) → res.partner


  - **partner_ship_to_id** (Many2one) → res.partner


  - **is_bill_to_editable** (Boolean)


  - **is_bill_from_editable** (Boolean)


  - **is_ship_to_editable** (Boolean)


  - **is_ship_from_editable** (Boolean)


  - **fiscal_position_id** (Many2one) → account.fiscal.position


  - **type_id** (Many2one) → l10n.in.ewaybill.type


  - **sub_type_code** (Char)


  - **type_description** (Char)


  - **distance** (Integer) → Distance


  - **mode** (Selection)


  - **vehicle_no** (Char) → Vehicle Number


  - **vehicle_type** (Selection)


  - **transportation_doc_no** (Char)


  - **transportation_doc_date** (Date)


  - **transporter_id** (Many2one) → res.partner


  - **error_message** (Html)


  - **blocking_level** (Selection)


  - **content** (Binary)


  - **cancel_reason** (Selection)


  - **cancel_remarks** (Char) → Cancel remarks








## Vistas


### l10n.in.ewaybill

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | l10n.in.ewaybill.form.view | `l10n_in_ewaybill_stock.l10n_in_ewaybill_form_view` | - |



#### Botones (l10n_in_ewaybill_stock.l10n_in_ewaybill_form_view)
- **Generate e-Waybill** (object)
- **Cancel e-Waybill** (object)
- **Reset to Pending** (object)
- **Use as Challan** (object)
- **Download JSON** (object) - Grupos: `base.group_no_one`
- **Print** (object)


### l10n.in.ewaybill.cancel

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | l10n.in.ewaybill.cancel.form | `l10n_in_ewaybill_stock.view_ewaybill_cancel_form` | - |



#### Botones (l10n_in_ewaybill_stock.view_ewaybill_cancel_form)
- **Cancel Ewaybill** (object)

