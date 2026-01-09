# Módulo: POS Pine Labs

## Información General
- **Nombre técnico:** pos_pine_labs
- **Versión:** 1.0
- **Categoría:** Sales/Point of Sale
- **Dependencias:** point_of_sale


## Propósito
Integrate your POS with Pine Labs payment terminals



## Descripción

Allow Pine Labs POS payments

This module is available only for companies that use INR currency.
It enables customers to pay for their orders using debit/credit cards and UPI through Pine Labs POS terminals.
A Pine Labs merchant account is required to process transactions.
Features include:

* Quick payments by swiping, scanning, or tapping your credit/debit card or UPI QR code at the payment terminal.
* Supported cards: Visa, MasterCard, RuPay.
    



## Modelos

### pos.payment.method


- Hereda de:

  - pos.payment.method




- Campos:

  - **pine_labs_merchant** (Char)


  - **pine_labs_store** (Char)


  - **pine_labs_client** (Char)


  - **pine_labs_security_token** (Char)


  - **pine_labs_allowed_payment_mode** (Selection)


  - **pine_labs_test_mode** (Boolean)





### pos.payment


- Hereda de:

  - pos.payment




- Campos:

  - **pine_labs_plutus_transaction_ref** (Char)







