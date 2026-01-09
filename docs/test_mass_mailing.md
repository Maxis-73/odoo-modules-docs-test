# Módulo: Mass Mail Tests

## Información General
- **Nombre técnico:** test_mass_mailing
- **Versión:** 1.0
- **Categoría:** Hidden
- **Dependencias:** mass_mailing, mass_mailing_sms, sms_twilio, test_mail, test_mail_sms


## Propósito
Mass Mail Tests: feature and performance tests for mass mailing



## Descripción
This module contains tests related to mass mailing. Those
are present in a separate module to use specific test models defined in
test_mail. 



## Modelos

### mailing.test.customer


- Hereda de:


  - mail.thread





- Campos:

  - **name** (Char)


  - **email_from** (Char)


  - **customer_id** (Many2one) → res.partner





### mailing.test.simple


- Hereda de:


  - mail.thread





- Campos:

  - **name** (Char)


  - **email_from** (Char)





### mailing.test.utm


- Hereda de:


  - mail.thread

  - utm.mixin





- Campos:

  - **name** (Char)





### mailing.test.blacklist


- Hereda de:


  - mail.thread.blacklist





- Campos:

  - **name** (Char)


  - **email_from** (Char)


  - **customer_id** (Many2one) → res.partner


  - **user_id** (Many2one) → res.users





### mailing.test.optout


- Hereda de:


  - mail.thread.blacklist





- Campos:

  - **name** (Char)


  - **email_from** (Char)


  - **opt_out** (Boolean)


  - **customer_id** (Many2one) → res.partner


  - **user_id** (Many2one) → res.users





### mailing.test.partner


- Hereda de:


  - mail.thread.blacklist





- Campos:

  - **name** (Char)


  - **email_from** (Char)


  - **partner_id** (Many2one) → res.partner





### mailing.performance


- Hereda de:


  - mail.thread





- Campos:

  - **name** (Char)


  - **email_from** (Char)





### mailing.performance.blacklist


- Hereda de:


  - mail.thread.blacklist





- Campos:

  - **name** (Char)


  - **email_from** (Char)


  - **user_id** (Many2one) → res.users


  - **container_id** (Many2one) → mail.test.container





### utm.test.source.mixin


- Hereda de:


  - utm.source.mixin





- Campos:

  - **name** (Char)


  - **title** (Char)





### utm.test.source.mixin.other


- Hereda de:


  - mail.thread

  - utm.source.mixin





- Campos:

  - **name** (Char)


  - **title** (Char)





### mailing.test.partner.unstored


- Hereda de:


  - mail.thread.blacklist





- Campos:

  - **name** (Char)


  - **email_from** (Char)


  - **partner_id** (Many2one) → res.partner





### ir.qweb


- Hereda de:

  - ir.qweb




- No agrega campos





