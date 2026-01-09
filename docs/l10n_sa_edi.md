# Módulo: Saudi Arabia - E-invoicing

## Información General
- **Nombre técnico:** l10n_sa_edi
- **Versión:** 0.2
- **Categoría:** Accounting/Localizations/EDI
- **Dependencias:** account_edi, account_edi_ubl_cii, account_debit_note, l10n_sa, base_vat, certificate


## Propósito

        E-Invoicing, Universal Business Language
    



## Descripción

E-invoice implementation for Saudi Arabia; Integration with ZATCA
    



## Modelos

### account.move.send


- Hereda de:

  - account.move.send




- No agrega campos



### account.edi.xml.ubl_21.zatca


- Hereda de:

  - account.edi.xml.ubl_21




- No agrega campos



### account.move


- Hereda de:

  - account.move




- Campos:

  - **l10n_sa_uuid** (Char)


  - **l10n_sa_invoice_signature** (Char) → Unsigned XML Signature


  - **l10n_sa_chain_index** (Integer)





### account.move.line


- Hereda de:

  - account.move.line




- No agrega campos



### account.journal


- Hereda de:

  - account.journal




- Campos:

  - **l10n_sa_csr** (Binary)


  - **l10n_sa_csr_errors** (Html) → Onboarding Errors


  - **l10n_sa_compliance_csid_json** (Char) → CCSID JSON


  - **l10n_sa_production_csid_certificate_id** (Many2one) → certificate.certificate


  - **l10n_sa_production_csid_json** (Char) → PCSID JSON


  - **l10n_sa_production_csid_validity** (Datetime)


  - **l10n_sa_compliance_csid_certificate_id** (Many2one) → certificate.certificate


  - **l10n_sa_compliance_checks_passed** (Boolean) → Compliance Checks Done


  - **l10n_sa_chain_sequence_id** (Many2one) → ir.sequence


  - **l10n_sa_serial_number** (Char) → Serial Number


  - **l10n_sa_latest_submission_hash** (Char) → Latest Submission Hash





### account.edi.format


- Hereda de:

  - account.edi.format




- No agrega campos



### ir.attachment


- Hereda de:

  - ir.attachment




- No agrega campos



### account.tax


- Hereda de:

  - account.tax




- Campos:

  - **l10n_sa_is_retention** (Boolean) → Is Retention


  - **l10n_sa_exemption_reason_code** (Selection)





### res.config.settings


- Hereda de:

  - res.config.settings




- Campos:

  - **l10n_sa_api_mode** (Selection)





### account.edi.document


- Hereda de:

  - account.edi.document




- No agrega campos



### res.company


- Hereda de:

  - res.company




- Campos:

  - **l10n_sa_private_key_id** (Many2one) → certificate.key


  - **l10n_sa_api_mode** (Selection)


  - **l10n_sa_edi_building_number** (Char)


  - **l10n_sa_edi_plot_identification** (Char)


  - **l10n_sa_additional_identification_scheme** (Selection)


  - **l10n_sa_additional_identification_number** (Char)





### certificate.certificate


- Hereda de:

  - certificate.certificate




- No agrega campos



### res.partner


- Hereda de:

  - res.partner




- Campos:

  - **l10n_sa_edi_building_number** (Char) → Building Number


  - **l10n_sa_edi_plot_identification** (Char) → Plot Identification


  - **l10n_sa_additional_identification_scheme** (Selection)


  - **l10n_sa_additional_identification_number** (Char) → Identification Number (SA)








## Vistas


### l10n_sa_edi.otp.wizard

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | l10n_sa_edi.otp.wizard.form | `l10n_sa_edi.l10n_sa_edi_otp_wizard_view_form` | - |



#### Botones (l10n_sa_edi.l10n_sa_edi_otp_wizard_view_form)
- **Request** (object)

