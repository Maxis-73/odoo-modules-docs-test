# Módulo: Check Printing Base

## Información General
- **Nombre técnico:** account_check_printing
- **Versión:** 1.0
- **Categoría:** Accounting/Accounting
- **Dependencias:** account


## Propósito
Check printing basic features



## Descripción

This module offers the basic functionalities to make payments by printing checks.
It must be used as a dependency for modules that provide country-specific check templates.
The check settings are located in the accounting journals configuration page.
    



## Modelos

### account.payment


- Hereda de:

  - account.payment




- Campos:

  - **check_amount_in_words** (Char)


  - **check_manual_sequencing** (Boolean)


  - **check_number** (Char)


  - **payment_method_line_id** (Many2one)


  - **show_check_number** (Boolean)





### account.payment.method


- Hereda de:

  - account.payment.method




- No agrega campos



### account.journal


- Hereda de:

  - account.journal




- Campos:

  - **check_manual_sequencing** (Boolean)


  - **check_sequence_id** (Many2one) → ir.sequence


  - **check_next_number** (Char)


  - **bank_check_printing_layout** (Selection)





### res.config.settings


- Hereda de:

  - res.config.settings




- Campos:

  - **account_check_printing_layout** (Selection)


  - **account_check_printing_date_label** (Boolean)


  - **account_check_printing_multi_stub** (Boolean)


  - **account_check_printing_margin_top** (Float)


  - **account_check_printing_margin_left** (Float)


  - **account_check_printing_margin_right** (Float)





### res.company


- Hereda de:

  - res.company




- Campos:

  - **account_check_printing_layout** (Selection)


  - **account_check_printing_date_label** (Boolean)


  - **account_check_printing_multi_stub** (Boolean)


  - **account_check_printing_margin_top** (Float)


  - **account_check_printing_margin_left** (Float)


  - **account_check_printing_margin_right** (Float)








## Vistas


### print.prenumbered.checks

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | Print Pre-numbered Checks | `account_check_printing.print_pre_numbered_checks_view` | - |



#### Botones (account_check_printing.print_pre_numbered_checks_view)
- **Print** (object)

