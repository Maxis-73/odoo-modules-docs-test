# Módulo: Spain - SII EDI Suministro de Libros

## Información General
- **Nombre técnico:** l10n_es_edi_sii
- **Versión:** 1.1
- **Categoría:** Accounting/Localizations/EDI
- **Dependencias:** certificate, l10n_es, account_edi




## Descripción

This module sends the taxes information (mostly VAT) of the
vendor bills and customer invoices to the SII.  It is called
Procedimiento G417 - IVA. Llevanza de libros registro.  It is
required for every company with a turnover of +6M€ and others can
already make use of it.  The invoices are automatically
sent after validation.

How the information is sent to the SII depends on the
configuration that is put in the taxes.  The taxes
that were in the chart template (l10n_es) are automatically
configured to have the right type.  It is possible however
that extra taxes need to be created for certain exempt/no sujeta reasons.

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

  - **l10n_es_edi_is_required** (Boolean)


  - **l10n_es_edi_csv** (Char)


  - **l10n_es_registration_date** (Date)





### account.edi.format


- Hereda de:

  - account.edi.format




- No agrega campos



### res.config.settings


- Hereda de:

  - res.config.settings




- Campos:

  - **l10n_es_sii_certificate_ids** (One2many)


  - **l10n_es_sii_tax_agency** (Selection)


  - **l10n_es_sii_test_env** (Boolean)





### res.company


- Hereda de:

  - res.company




- Campos:

  - **l10n_es_sii_certificate_id** (Many2one) → certificate.certificate


  - **l10n_es_sii_certificate_ids** (One2many) → certificate.certificate


  - **l10n_es_sii_tax_agency** (Selection)


  - **l10n_es_sii_test_env** (Boolean)





### certificate.certificate


- Hereda de:

  - certificate.certificate




- Campos:

  - **scope** (Selection)







