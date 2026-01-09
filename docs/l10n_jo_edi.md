# Módulo: Jordan E-Invoicing

## Información General
- **Nombre técnico:** l10n_jo_edi
- **Versión:** 1.0
- **Categoría:** Accounting/Localizations/EDI
- **Dependencias:** account_edi_ubl_cii, l10n_jo


## Propósito
Electronic Invoicing for Jordan UBL 2.1



## Descripción

       Allows the users to integrate with JoFotara.
    



## Modelos

### account.move.send


- Hereda de:

  - account.move.send




- No agrega campos



### account.move


- Hereda de:

  - account.move




- Campos:

  - **l10n_jo_edi_uuid** (Char)


  - **l10n_jo_edi_qr** (Char)


  - **l10n_jo_edi_is_needed** (Boolean)


  - **l10n_jo_edi_state** (Selection)


  - **l10n_jo_edi_error** (Text)


  - **l10n_jo_edi_computed_xml** (Binary)


  - **l10n_jo_edi_xml_attachment_file** (Binary)


  - **l10n_jo_edi_xml_attachment_id** (Many2one) → ir.attachment


  - **reversed_entry_id** (Many2one)





### ir.attachment


- Hereda de:

  - ir.attachment




- No agrega campos



### account.tax


- Hereda de:

  - account.tax




- No agrega campos



### res.config.settings


- Hereda de:

  - res.config.settings




- Campos:

  - **l10n_jo_edi_sequence_income_source** (Char)


  - **l10n_jo_edi_secret_key** (Char)


  - **l10n_jo_edi_client_identifier** (Char)


  - **l10n_jo_edi_taxpayer_type** (Selection)





### res.company


- Hereda de:

  - res.company




- Campos:

  - **l10n_jo_edi_sequence_income_source** (Char)


  - **l10n_jo_edi_secret_key** (Char)


  - **l10n_jo_edi_client_identifier** (Char)


  - **l10n_jo_edi_taxpayer_type** (Selection)





### account.edi.xml.ubl_21.jo


- Hereda de:

  - account.edi.xml.ubl_21




- No agrega campos





