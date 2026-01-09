# Módulo: SMS Tests

## Información General
- **Nombre técnico:** test_mail_sms
- **Versión:** 1.0
- **Categoría:** Hidden
- **Dependencias:** mail, sms, sms_twilio, test_performance


## Propósito
SMS Tests: performances and tests specific to SMS



## Descripción
This module contains tests related to SMS. Those are
present in a separate module as it contains models used only to perform
tests independently to functional aspects of other models. 



## Modelos

### mail.test.sms


- Hereda de:


  - mail.thread





#### Campos
- **name** (Char)
- **subject** (Char)
- **email_from** (Char)
- **guest_ids** (Many2many) → res.partner
- **phone_nbr** (Char)
- **mobile_nbr** (Char)
- **customer_id** (Many2one) → res.partner
- **country_id** (Many2one) → res.country





### mail.test.sms.bl


- Hereda de:


  - mail.thread.phone





#### Campos
- **name** (Char)
- **subject** (Char)
- **email_from** (Char)
- **phone_nbr** (Char)
- **mobile_nbr** (Char)
- **customer_id** (Many2one) → res.partner





### mail.test.sms.bl.activity


- Hereda de:


  - mail.test.sms.bl

  - mail.activity.mixin





- No agrega campos




### mail.test.sms.bl.optout


- Hereda de:


  - mail.thread.phone





#### Campos
- **name** (Char)
- **subject** (Char)
- **email_from** (Char)
- **phone_nbr** (Char)
- **mobile_nbr** (Char)
- **customer_id** (Many2one) → res.partner
- **opt_out** (Boolean)





### mail.test.sms.partner


- Hereda de:


  - mail.thread





#### Campos
- **name** (Char)
- **customer_id** (Many2one) → res.partner
- **opt_out** (Boolean)





### mail.test.sms.partner.2many


- Hereda de:


  - mail.thread





#### Campos
- **name** (Char)
- **customer_ids** (Many2many) → res.partner
- **opt_out** (Boolean)





### sms.test.nothread


- Hereda de: Base



#### Campos
- **name** (Char)
- **company_id** (Many2one) → res.company
- **customer_id** (Many2one) → res.partner







