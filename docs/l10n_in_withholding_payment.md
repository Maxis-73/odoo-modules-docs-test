# Módulo: Indian - TDS For Payment

## Información General
- **Nombre técnico:** l10n_in_withholding_payment
- **Versión:** 1.0
- **Categoría:** Accounting/Localizations
- **Dependencias:** l10n_in_withholding




## Descripción

        Support for Indian TDS (Tax Deducted at Source) for Payment.
    



## Modelos

### account.payment


- Hereda de:

  - account.payment




- Campos:

  - **l10n_in_withhold_move_ids** (One2many) → account.move


  - **l10n_in_total_withholding_amount** (Monetary)





### account.move


- Hereda de:

  - account.move




- Campos:

  - **l10n_in_withholding_ref_payment_id** (Many2one) → account.payment







