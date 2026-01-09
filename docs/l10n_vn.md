# Módulo: Vietnam - Accounting

## Información General
- **Nombre técnico:** l10n_vn
- **Versión:** 2.0.3
- **Categoría:** Accounting/Localizations/Account Charts
- **Dependencias:** account_qr_code_emv, base_iban, account




## Descripción

This is the module to manage the accounting chart, bank information for Vietnam in Odoo.

- This module applies to companies based in Vietnamese Accounting Standard (VAS)
  with Chart of account under Circular No. 200/2014/TT-BTC
- Add Vietnamese bank information (like name, bic ..) as announced and yearly updated by State Bank
  of Viet Nam (https://sbv.gov.vn/webcenter/portal/en/home/sbv/paytreasury/bankidno).
- Add VietQR feature for invoice

**Credits:**
    - General Solutions.
    - Trobz
    - Jean Nguyen - The Bean Family (https://github.com/anhjean/vietqr) for VietQR.





## Modelos

### account.move


- Hereda de:

  - account.move




- Campos:

  - **l10n_vn_e_invoice_number** (Char)





### account.chart.template


- Hereda de:

  - account.chart.template




- No agrega campos



### res.partner.bank


- Hereda de:

  - res.partner.bank




- Campos:

  - **proxy_type** (Selection)







