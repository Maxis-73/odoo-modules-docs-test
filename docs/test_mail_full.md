# Módulo: Mail Tests (Full)

## Información General
- **Nombre técnico:** test_mail_full
- **Versión:** 1.0
- **Categoría:** Hidden
- **Dependencias:** mail, mail_bot, portal, rating, mass_mailing, mass_mailing_sms, phone_validation, sms, test_mail, test_mail_sms, test_mass_mailing


## Propósito
Mail Tests: performances and tests specific to mail with all sub-modules



## Descripción
This module contains tests related to various mail features
and mail-related sub modules. Those tests are present in a separate module as it
contains models used only to perform tests independently to functional aspects of
real applications. 



## Modelos

### mail.test.portal


- Hereda de:


  - portal.mixin

  - mail.thread





#### Campos
- **name** (Char) → Name
- **partner_id** (Many2one) → res.partner
- **user_id** (Many2one) → res.users





### mail.test.portal.no.partner


- Hereda de:


  - mail.thread

  - portal.mixin





#### Campos
- **name** (Char)





### mail.test.portal.public.access.action


- Hereda de:

  - mail.test.portal




- No agrega campos




### mail.test.rating


- Hereda de:


  - rating.mixin

  - mail.activity.mixin

  - portal.mixin





#### Campos
- **name** (Char) → Name
- **subject** (Char) → Subject
- **company_id** (Many2one) → res.company
- **customer_id** (Many2one) → res.partner
- **email_from** (Char) → From
- **mobile_nbr** (Char) → Mobile
- **phone_nbr** (Char) → Phone Number
- **user_id** (Many2one) → res.users





### mail.test.rating.thread


- Hereda de:

  - mail.thread




#### Campos
- **name** (Char) → Name
- **customer_id** (Many2one) → res.partner
- **user_id** (Many2one) → res.users





### mail.test.rating.thread.read


- Hereda de:

  - mail.test.rating.thread




- No agrega campos






