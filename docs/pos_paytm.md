# Módulo: POS PayTM

## Información General
- **Nombre técnico:** pos_paytm
- **Versión:** 1.0
- **Categoría:** Sales/Point of Sale
- **Dependencias:** point_of_sale


## Propósito
Integrate your POS with a PayTM payment terminal



## Descripción

Allow Paytm POS payments
==============================

This module allows customers to pay for their orders with debit/credit
cards and UPI. The transactions are processed by Paytm POS. A Paytm merchant account is necessary. It allows the
following:

* Fast payment by just swiping/scanning a credit/debit card or a QR code while on the payment screen
* Supported cards: Visa, MasterCard, Rupay, UPI
    



## Modelos

### pos.payment.method


- Hereda de:

  - pos.payment.method




#### Campos
- **paytm_tid** (Char)
- **channel_id** (Char)
- **accept_payment** (Selection)
- **allowed_payment_modes** (Selection)
- **paytm_mid** (Char)
- **paytm_merchant_key** (Char)
- **paytm_test_mode** (Boolean)







