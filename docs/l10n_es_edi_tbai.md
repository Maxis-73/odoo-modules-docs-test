# Módulo: Spain - TicketBAI

## Información General
- **Nombre técnico:** l10n_es_edi_tbai
- **Versión:** 1.1
- **Categoría:** Accounting/Localizations/EDI
- **Dependencias:** l10n_es, certificate




## Descripción

This module sends invoices and vendor bills to the "Diputaciones
Forales" of Araba/Álava, Bizkaia and Gipuzkoa.

Invoices and bills get converted to XML and regularly sent to the
Basque government servers which provides them with a unique identifier.
A hash chain ensures the continuous nature of the invoice/bill
sequences. QR codes are added to emitted (sent/printed) invoices,
bills and tickets to allow anyone to check they have been declared.

You need to configure your certificate and the tax agency.
    



## Modelos

### account.move.send


- Hereda de:

  - account.move.send




- No agrega campos



### account.move


- Hereda de:

  - account.move




- Campos:

  - **l10n_es_tbai_state** (Selection)


  - **l10n_es_tbai_chain_index** (Integer)


  - **l10n_es_tbai_post_document_id** (Many2one) → l10n_es_edi_tbai.document


  - **l10n_es_tbai_cancel_document_id** (Many2one) → l10n_es_edi_tbai.document


  - **l10n_es_tbai_post_file** (Binary)


  - **l10n_es_tbai_post_file_name** (Char)


  - **l10n_es_tbai_cancel_file** (Binary)


  - **l10n_es_tbai_cancel_file_name** (Char)


  - **l10n_es_tbai_is_required** (Boolean)


  - **l10n_es_tbai_refund_reason** (Selection)


  - **l10n_es_tbai_reversed_ids** (Many2many) → account.move





### res.config.settings


- Hereda de:

  - res.config.settings




- Campos:

  - **l10n_es_tbai_certificate_ids** (One2many)


  - **l10n_es_tbai_tax_agency** (Selection)


  - **l10n_es_tbai_test_env** (Boolean)





### account.move.line


- Hereda de:

  - account.move.line




- No agrega campos



### l10n_es_edi_tbai.document


- Hereda de: Base



- Campos:

  - **name** (Char)


  - **date** (Date)


  - **xml_attachment_id** (Many2one) → ir.attachment


  - **company_id** (Many2one) → res.company


  - **state** (Selection)


  - **chain_index** (Integer)


  - **response_message** (Text)


  - **is_cancel** (Boolean)





### res.company


- Hereda de:

  - res.company




- Campos:

  - **l10n_es_tbai_certificate_id** (Many2one) → certificate.certificate


  - **l10n_es_tbai_certificate_ids** (One2many) → certificate.certificate


  - **l10n_es_tbai_tax_agency** (Selection)


  - **l10n_es_tbai_license_html** (Html)


  - **l10n_es_tbai_chain_sequence_id** (Many2one) → ir.sequence


  - **l10n_es_tbai_test_env** (Boolean)


  - **l10n_es_tbai_is_enabled** (Boolean)





### certificate.certificate


- Hereda de:

  - certificate.certificate




- Campos:

  - **scope** (Selection)







