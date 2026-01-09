# Módulo: Spain - Veri*Factu for Point of Sale

## Información General
- **Nombre técnico:** l10n_es_edi_verifactu_pos
- **Versión:** 1.0
- **Categoría:** Accounting/Localizations/Point of Sale
- **Dependencias:** l10n_es_edi_verifactu, point_of_sale


## Propósito
Add Veri*Factu support to Point of Sale





## Modelos

### l10n_es_edi_verifactu.document


- Hereda de:

  - l10n_es_edi_verifactu.document




- Campos:

  - **pos_order_id** (Many2one) → pos.order





### pos.config


- Hereda de:

  - pos.config




- Campos:

  - **l10n_es_edi_verifactu_required** (Boolean)





### pos.order


- Hereda de:

  - pos.order




- Campos:

  - **l10n_es_edi_verifactu_required** (Boolean)


  - **l10n_es_edi_verifactu_document_ids** (One2many) → l10n_es_edi_verifactu.document


  - **l10n_es_edi_verifactu_state** (Selection)


  - **l10n_es_edi_verifactu_warning_level** (Char)


  - **l10n_es_edi_verifactu_warning** (Html)


  - **l10n_es_edi_verifactu_qr_code** (Char)


  - **l10n_es_edi_verifactu_show_cancel_button** (Boolean)


  - **l10n_es_edi_verifactu_refund_reason** (Selection)





### account.move


- Hereda de:

  - account.move




- No agrega campos



### res.company


- Hereda de:

  - res.company




- No agrega campos



### pos.session


- Hereda de:

  - pos.session




- No agrega campos






## Vistas


### pos.order

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | pos.order.form.inherit.l10n_es_edi_verifactu_pos | `l10n_es_edi_verifactu_pos.view_pos_order_form_inherit_l10n_es_pos_verifactu` | point_of_sale.view_pos_pos_form |


