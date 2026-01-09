# Módulo: POS Razorpay

## Información General
- **Nombre técnico:** pos_razorpay
- **Versión:** 1.0
- **Categoría:** Sales/Point of Sale
- **Dependencias:** point_of_sale


## Propósito
Integrate your POS with a Razorpay payment terminal



## Descripción

Allow Razorpay POS payments
==============================

This module allows customers to pay for their orders with debit/credit
cards and UPI. The transactions are processed by Razorpay POS. A Razorpay merchant account is necessary. It allows the
following:

* Fast payment by just swiping/scanning a credit/debit card or a QR code while on the payment screen
* Supported cards: Visa, MasterCard, Rupay, UPI
    



## Modelos

### pos.payment.method


- Hereda de:

  - pos.payment.method




#### Campos
- **razorpay_tid** (Char)
- **razorpay_allowed_payment_modes** (Selection)
- **razorpay_username** (Char)
- **razorpay_api_key** (Char)
- **razorpay_test_mode** (Boolean)





### pos.payment


- Hereda de:

  - pos.payment




#### Campos
- **razorpay_reverse_ref_no** (Char) → Razorpay Reverse Reference No.







