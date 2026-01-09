# Módulo: Greece - myDATA

## Información General
- **Nombre técnico:** l10n_gr_edi
- **Versión:** 1.0
- **Categoría:** Accounting/Localizations
- **Dependencias:** l10n_gr


## Propósito
Connect to myDATA API implementation for Greece



## Descripción

        myDATA is a platform created by Greece's tax authority,
        The Independent Authority for Public Revenue (IAPR),
        to digitize business tax and accounting information declaration.
    



## Modelos

### account.move.send


- Hereda de:

  - account.move.send




- No agrega campos



### l10n_gr_edi.document


- Hereda de: Base



- Campos:

  - **move_id** (Many2one) → account.move


  - **state** (Selection)


  - **datetime** (Datetime)


  - **attachment_id** (Many2one) → ir.attachment


  - **message** (Char)


  - **mydata_mark** (Char)


  - **mydata_cls_mark** (Char)


  - **mydata_url** (Char)





### product.template


- Hereda de:

  - product.template




- Campos:

  - **l10n_gr_edi_preferred_classification_ids** (One2many) → l10n_gr_edi.preferred_classification





### l10n_gr_edi.preferred_classification


- Hereda de: Base



- Campos:

  - **product_template_id** (Many2one) → product.template


  - **fiscal_position_id** (Many2one) → account.fiscal.position


  - **priority** (Integer)


  - **l10n_gr_edi_inv_type** (Selection)


  - **l10n_gr_edi_cls_category** (Selection)


  - **l10n_gr_edi_cls_type** (Selection)


  - **l10n_gr_edi_available_inv_type** (Char)


  - **l10n_gr_edi_available_cls_category** (Char)


  - **l10n_gr_edi_available_cls_type** (Char)





### account.move


- Hereda de:

  - account.move




- Campos:

  - **l10n_gr_edi_mark** (Char)


  - **l10n_gr_edi_cls_mark** (Char)


  - **l10n_gr_edi_document_ids** (One2many) → l10n_gr_edi.document


  - **l10n_gr_edi_state** (Selection)


  - **l10n_gr_edi_available_inv_type** (Char)


  - **l10n_gr_edi_correlation_id** (Many2one) → account.move


  - **l10n_gr_edi_inv_type** (Selection)


  - **l10n_gr_edi_payment_method** (Selection)


  - **l10n_gr_edi_alerts** (Json)


  - **l10n_gr_edi_need_correlated** (Boolean)


  - **l10n_gr_edi_need_payment_method** (Boolean)


  - **l10n_gr_edi_enable_view_mydata** (Boolean)


  - **l10n_gr_edi_enable_send_invoices** (Boolean)


  - **l10n_gr_edi_enable_send_expense_classification** (Boolean)


  - **l10n_gr_edi_attachment_id** (Many2one) → ir.attachment





### account.fiscal.position


- Hereda de:

  - account.fiscal.position




- Campos:

  - **l10n_gr_edi_preferred_classification_ids** (One2many) → l10n_gr_edi.preferred_classification





### account.tax


- Hereda de:

  - account.tax




- Campos:

  - **l10n_gr_edi_default_tax_exemption_category** (Selection)





### res.config.settings


- Hereda de:

  - res.config.settings




- Campos:

  - **l10n_gr_edi_aade_id** (Char)


  - **l10n_gr_edi_aade_key** (Char)


  - **l10n_gr_edi_branch_number** (Integer)


  - **l10n_gr_edi_test_env** (Boolean)





### account.move.line


- Hereda de:

  - account.move.line




- Campos:

  - **l10n_gr_edi_available_cls_category** (Char)


  - **l10n_gr_edi_available_cls_type** (Char)


  - **l10n_gr_edi_available_cls_vat** (Char)


  - **l10n_gr_edi_need_exemption_category** (Boolean)


  - **l10n_gr_edi_detail_type** (Selection)


  - **l10n_gr_edi_cls_category** (Selection)


  - **l10n_gr_edi_cls_type** (Selection)


  - **l10n_gr_edi_cls_vat** (Selection)


  - **l10n_gr_edi_tax_exemption_category** (Selection)





### res.company


- Hereda de:

  - res.company




- Campos:

  - **l10n_gr_edi_aade_id** (Char)


  - **l10n_gr_edi_aade_key** (Char)


  - **l10n_gr_edi_branch_number** (Integer)


  - **l10n_gr_edi_test_env** (Boolean)





### res.partner


- Hereda de:

  - res.partner




- Campos:

  - **l10n_gr_edi_branch_number** (Integer)








## Vistas


### account.move

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | account.move.form.inherit.l10n_gr_edi | `l10n_gr_edi.account_move_form_inherit_l10n_gr_edi` | account.view_move_form |



### product.template

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | product.template.form.inherit.l10n.gr.edi | `l10n_gr_edi.product_template_form_view_inherit_l10n_gr_edi` | account.product_template_form_view |



### account.fiscal.position

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | account.fiscal.position.form | `l10n_gr_edi.view_account_position_form` | account.view_account_position_form |


