# Módulo: Italy - E-invoicing (Withholding)

## Información General
- **Nombre técnico:** l10n_it_edi_withholding
- **Versión:** 0.1
- **Categoría:** Accounting/Localizations/EDI
- **Dependencias:** l10n_it_edi




## Descripción

Withholding and Pension Fund handling for the E-invoice implementation for Italy.

    The Withholding tax and the Pension Fund tax are computed like every other tax
    with the ordering by sequence, so please be careful with the order of the taxes
    in your tax configuration.

    Please also update the Italian Accounting module (l10n_it) when you install this module.
    



## Modelos

### account.move


- Hereda de:

  - account.move




- Campos:

  - **l10n_it_amount_vat_signed** (Monetary)


  - **l10n_it_amount_pension_fund_signed** (Monetary)


  - **l10n_it_amount_withholding_signed** (Monetary)


  - **l10n_it_amount_before_withholding_signed** (Monetary)





### account.tax


- Hereda de:

  - account.tax




- Campos:

  - **l10n_it_withholding_type** (Selection)


  - **l10n_it_withholding_reason** (Selection)


  - **l10n_it_pension_fund_type** (Selection)





### account.chart.template


- Hereda de:

  - account.chart.template




- No agrega campos





