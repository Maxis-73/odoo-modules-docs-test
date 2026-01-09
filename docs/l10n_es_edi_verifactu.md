# Módulo: Spain - Veri*Factu

## Información General
- **Nombre técnico:** l10n_es_edi_verifactu
- **Versión:** 1.0
- **Categoría:** Accounting/Localizations/EDI
- **Dependencias:** l10n_es


## Propósito
Module for sending Spanish Veri*Factu XML to the AEAT





## Modelos

### l10n_es_edi_verifactu.document


- Hereda de: Base



- Campos:

  - **company_id** (Many2one) → res.company


  - **move_id** (Many2one) → account.move


  - **chain_index** (Integer)


  - **document_type** (Selection)


  - **json_attachment_id** (Many2one) → ir.attachment


  - **json_attachment_base64** (Binary)


  - **json_attachment_filename** (Char)


  - **errors** (Html)


  - **response_csv** (Char)


  - **state** (Selection)





### account.move.send


- Hereda de:

  - account.move.send




- No agrega campos



### account.move


- Hereda de:

  - account.move




- Campos:

  - **l10n_es_edi_verifactu_required** (Boolean)


  - **l10n_es_edi_verifactu_document_ids** (One2many) → l10n_es_edi_verifactu.document


  - **l10n_es_edi_verifactu_state** (Selection)


  - **l10n_es_edi_verifactu_warning_level** (Char)


  - **l10n_es_edi_verifactu_warning** (Html)


  - **l10n_es_edi_verifactu_qr_code** (Char)


  - **l10n_es_edi_verifactu_show_cancel_button** (Boolean)


  - **l10n_es_edi_verifactu_available_clave_regimens** (Char)


  - **l10n_es_edi_verifactu_clave_regimen** (Selection)


  - **l10n_es_edi_verifactu_substituted_entry_id** (Many2one) → account.move


  - **l10n_es_edi_verifactu_substitution_move_ids** (One2many) → account.move


  - **l10n_es_edi_verifactu_refund_reason** (Selection)





### account.tax


- Hereda de:

  - account.tax




- Campos:

  - **l10n_es_applicability** (Selection)





### res.config.settings


- Hereda de:

  - res.config.settings




- Campos:

  - **l10n_es_edi_verifactu_required** (Boolean)


  - **l10n_es_edi_verifactu_certificate_ids** (One2many)


  - **l10n_es_edi_verifactu_test_environment** (Boolean)


  - **l10n_es_edi_verifactu_special_vat_regime** (Selection)





### res.company


- Hereda de:

  - res.company




- Campos:

  - **l10n_es_edi_verifactu_certificate_ids** (One2many) → certificate.certificate


  - **l10n_es_edi_verifactu_required** (Boolean)


  - **l10n_es_edi_verifactu_test_environment** (Boolean)


  - **l10n_es_edi_verifactu_chain_sequence_id** (Many2one) → ir.sequence


  - **l10n_es_edi_verifactu_next_batch_time** (Datetime)


  - **l10n_es_edi_verifactu_special_vat_regime** (Selection)





### certificate.certificate


- Hereda de:

  - certificate.certificate




- Campos:

  - **scope** (Selection)





### account.chart.template


- Hereda de:

  - account.chart.template




- No agrega campos



### res.partner


- Hereda de:

  - res.partner




- No agrega campos






## Vistas


### l10n_es_edi_verifactu.document

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | l10n_es_edi_verifactu.document.form | `l10n_es_edi_verifactu.view_l10n_es_edi_verifactu_document_form` | - |



### account.move

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | account.move.form.inherit.l10n_es_edi_verifactu | `l10n_es_edi_verifactu.view_move_form_inherit_l10n_es_edi_verifactu` | account.view_move_form |


