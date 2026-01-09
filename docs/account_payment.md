# Módulo: Payment - Account

## Información General
- **Nombre técnico:** account_payment
- **Versión:** 2.0
- **Categoría:** Accounting/Accounting
- **Dependencias:** account, payment


## Propósito
Enable customers to pay invoices on the portal and post payments when transactions are processed.





## Modelos

### account.payment.method.line


- Hereda de:

  - account.payment.method.line




- Campos:

  - **payment_provider_id** (Many2one) → payment.provider


  - **payment_provider_state** (Selection)





### payment.transaction


- Hereda de:

  - payment.transaction




- Campos:

  - **payment_id** (Many2one) → account.payment


  - **invoice_ids** (Many2many) → account.move


  - **invoices_count** (Integer)





### account.payment


- Hereda de:

  - account.payment




- Campos:

  - **payment_transaction_id** (Many2one) → payment.transaction


  - **payment_token_id** (Many2one) → payment.token


  - **amount_available_for_refund** (Monetary)


  - **suitable_payment_token_ids** (Many2many) → payment.token


  - **use_electronic_payment_method** (Boolean)


  - **source_payment_id** (Many2one) → account.payment


  - **refunds_count** (Integer)





### onboarding.onboarding.step


- Hereda de:

  - onboarding.onboarding.step




- No agrega campos



### account.payment.method


- Hereda de:

  - account.payment.method




- No agrega campos



### account.move


- Hereda de:

  - account.move




- Campos:

  - **transaction_ids** (Many2many) → payment.transaction


  - **authorized_transaction_ids** (Many2many) → payment.transaction


  - **transaction_count** (Integer)


  - **amount_paid** (Monetary)





### account.journal


- Hereda de:

  - account.journal




- No agrega campos



### payment.provider


- Hereda de:

  - payment.provider




- Campos:

  - **journal_id** (Many2one) → account.journal







