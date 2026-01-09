# Módulo: Italy - E-invoicing

## Información General
- **Nombre técnico:** l10n_it_edi
- **Versión:** 0.4
- **Categoría:** Accounting/Localizations/EDI
- **Dependencias:** l10n_it, account_edi_proxy_client




## Descripción

E-invoice implementation
    



## Modelos

### account.move.send


- Hereda de:

  - account.move.send




- No agrega campos



### account.move


- Hereda de:

  - account.move




- Campos:

  - **l10n_it_edi_state** (Selection)


  - **l10n_it_edi_header** (Html)


  - **l10n_it_edi_transaction** (Char)


  - **l10n_it_edi_attachment_file** (Binary)


  - **l10n_it_edi_attachment_id** (Many2one) → ir.attachment


  - **l10n_it_edi_is_self_invoice** (Boolean)


  - **l10n_it_stamp_duty** (Float)


  - **l10n_it_ddt_id** (Many2one) → l10n_it.ddt


  - **l10n_it_origin_document_type** (Selection)


  - **l10n_it_origin_document_name** (Char)


  - **l10n_it_origin_document_date** (Date)


  - **l10n_it_cig** (Char)


  - **l10n_it_cup** (Char)


  - **l10n_it_partner_pa** (Boolean)





### account_edi_proxy_client.user


- Hereda de:

  - account_edi_proxy_client.user




- Campos:

  - **proxy_type** (Selection)





### ir.attachment


- Hereda de:

  - ir.attachment




- No agrega campos



### res.config.settings


- Hereda de:

  - res.config.settings




- Campos:

  - **is_edi_proxy_active** (Boolean)


  - **company_parent_id** (Many2one)


  - **use_root_proxy_user** (Boolean)


  - **l10n_it_edi_proxy_current_state** (Char)


  - **l10n_it_edi_register** (Boolean)


  - **l10n_it_edi_demo_mode** (Selection)





### l10n_it.ddt


- Hereda de: Base



- Campos:

  - **invoice_id** (One2many) → account.move


  - **name** (Char)


  - **date** (Date)





### res.company


- Hereda de:

  - res.company




- Campos:

  - **l10n_it_codice_fiscale** (Char)


  - **l10n_it_tax_system** (Selection)


  - **l10n_it_edi_proxy_user_id** (Many2one) → account_edi_proxy_client.user


  - **l10n_it_has_eco_index** (Boolean)


  - **l10n_it_eco_index_office** (Many2one) → res.country.state


  - **l10n_it_eco_index_number** (Char)


  - **l10n_it_eco_index_share_capital** (Float)


  - **l10n_it_eco_index_sole_shareholder** (Selection)


  - **l10n_it_eco_index_liquidation_state** (Selection)


  - **l10n_it_has_tax_representative** (Boolean)


  - **l10n_it_tax_representative_partner_id** (Many2one) → res.partner





### res.partner


- Hereda de:

  - res.partner




- Campos:

  - **invoice_edi_format** (Selection)


  - **l10n_it_pec_email** (Char)


  - **l10n_it_codice_fiscale** (Char)


  - **l10n_it_pa_index** (Char)








## Vistas


### l10n_it.ddt

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | ddt.form.l10n.it | `l10n_it_edi.l10n_it_ddt` | - |
| list | l10n_it.ddt.list.view | `l10n_it_edi.l10n_it_ddt_list_view` | - |


