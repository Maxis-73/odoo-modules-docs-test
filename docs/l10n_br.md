# Módulo: Brazilian - Accounting

## Información General
- **Nombre técnico:** l10n_br
- **Versión:** 1.1
- **Categoría:** Accounting/Localizations/Account Charts
- **Dependencias:** account, account_qr_code_emv, base_address_extended, l10n_latam_base, l10n_latam_invoice_document




## Descripción

Base module for the Brazilian localization

This module consists of:

- Generic Brazilian chart of accounts
- Brazilian taxes such as:

  - IPI
  - ICMS
  - PIS
  - COFINS
  - ISS
  - IR
  - CSLL

- Document Types as NFC-e, NFS-e, etc.
- Identification Documents as CNPJ and CPF

In addition to this module, the Brazilian Localizations is also
extended and complemented with several additional modules.

Brazil - Accounting Reports (l10n_br_reports)
---------------------------------------------
Adds a simple tax report that helps check the tax amount per tax group
in a given period of time. Also adds the P&L and BS adapted for the
Brazilian market.

Avatax Brazil (l10n_br_avatax)
------------------------------
Add Brazilian tax calculation via Avatax and all necessary fields needed to
configure Odoo in order to properly use Avatax and send the needed fiscal
information to retrieve the correct taxes.

Avatax for SOs in Brazil (l10n_br_avatax_sale)
----------------------------------------------
Same as the l10n_br_avatax module with the extension to the sales order module.

Electronic invoicing through Avatax (l10n_br_edi)
-------------------------------------------------
Create electronic sales invoices with Avatax.




## Modelos

### res.partner.bank


- Hereda de:

  - res.partner.bank




- Campos:

  - **proxy_type** (Selection)





### account.chart.template


- Hereda de:

  - account.chart.template




- No agrega campos



### res.city


- Hereda de:

  - res.city




- Campos:

  - **l10n_br_zip_range_ids** (One2many) → l10n_br.zip.range


  - **l10n_br_zip_ranges** (Char)





### l10n_br.zip.range


- Hereda de: Base



- Campos:

  - **city_id** (Many2one) → res.city


  - **start** (Char)


  - **end** (Char)





### account.move


- Hereda de:

  - account.move




- No agrega campos



### account.fiscal.position


- Hereda de:

  - account.fiscal.position




- Campos:

  - **l10n_br_fp_type** (Selection)





### account.journal


- Hereda de:

  - account.journal




- Campos:

  - **l10n_br_invoice_serial** (Char) → Series





### res.company


- Hereda de:

  - res.company




- Campos:

  - **l10n_br_cpf_code** (Char)


  - **l10n_br_ie_code** (Char)


  - **l10n_br_im_code** (Char)


  - **l10n_br_nire_code** (Char)





### account.tax


- Hereda de:

  - account.tax




- Campos:

  - **tax_discount** (Boolean)


  - **base_reduction** (Float)


  - **amount_mva** (Float)





### res.partner


- Hereda de:

  - res.partner




- Campos:

  - **l10n_br_ie_code** (Char)


  - **l10n_br_im_code** (Char)


  - **l10n_br_isuf_code** (Char)








## Vistas


### res.partner

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | partner.form.address.extended | `l10n_br.br_partner_address_form` | - |


