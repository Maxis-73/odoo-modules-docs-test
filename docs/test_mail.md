# Módulo: Mail Tests

## Información General
- **Nombre técnico:** test_mail
- **Versión:** 1.0
- **Categoría:** Hidden
- **Dependencias:** mail, test_performance


## Propósito
Mail Tests: performances and tests specific to mail



## Descripción
This module contains tests related to mail. Those are
present in a separate module as it contains models used only to perform
tests independently to functional aspects of other models. 



## Modelos

### mail.test.cc


- Hereda de:


  - mail.thread.cc





#### Campos
- **name** (Char)





### mail.test.properties


- Hereda de:


  - mail.thread





#### Campos
- **name** (Char) → Name
- **parent_id** (Many2one) → mail.test.properties
- **properties** (Properties) → Properties
- **definition_properties** (PropertiesDefinition) → Definitions





### mail.test.lead


- Hereda de:


  - mail.thread.blacklist

  - mail.thread.cc

  - mail.activity.mixin





#### Campos
- **name** (Char)
- **company_id** (Many2one) → res.company
- **user_id** (Many2one) → res.users
- **email_from** (Char)
- **customer_name** (Char)
- **partner_id** (Many2one) → res.partner
- **lang_code** (Char)
- **mobile** (Char)
- **phone** (Char)





### mail.test.access


- Hereda de:


  - mail.thread.blacklist





#### Campos
- **name** (Char)
- **email_from** (Char)
- **phone** (Char)
- **customer_id** (Many2one) → res.partner
- **access** (Selection)





### mail.test.access.custo


- Hereda de:


  - mail.thread.blacklist





#### Campos
- **name** (Char)
- **email_from** (Char)
- **phone** (Char)
- **customer_id** (Many2one) → res.partner
- **is_locked** (Boolean)





### mail.test.simple


- Hereda de:


  - mail.thread





#### Campos
- **name** (Char)
- **email_from** (Char)





### mail.test.simple.unnamed


- Hereda de:


  - mail.thread





#### Campos
- **description** (Char)





### mail.test.simple.main.attachment


- Hereda de:


  - mail.test.simple

  - mail.thread.main.attachment





- No agrega campos




### mail.test.simple.unfollow


- Hereda de:


  - mail.thread





#### Campos
- **name** (Char)
- **company_id** (Many2one) → res.company
- **email_from** (Char)





### mail.test.alias.optional


- Hereda de:


  - mail.alias.mixin.optional





#### Campos
- **name** (Char)
- **company_id** (Many2one) → res.company
- **email_from** (Char)





### mail.test.gateway


- Hereda de:


  - mail.thread.blacklist





#### Campos
- **name** (Char)
- **email_from** (Char)
- **custom_field** (Char)





### mail.test.gateway.company


- Hereda de:


  - mail.test.gateway





#### Campos
- **company_id** (Many2one) → res.company





### mail.test.gateway.main.attachment


- Hereda de:


  - mail.test.gateway

  - mail.thread.main.attachment





#### Campos
- **company_id** (Many2one) → res.company





### mail.test.gateway.groups


- Hereda de:


  - mail.thread.blacklist

  - mail.alias.mixin





#### Campos
- **name** (Char)
- **email_from** (Char)
- **custom_field** (Char)
- **customer_id** (Many2one) → res.partner





### mail.test.track


- Hereda de:


  - mail.thread





#### Campos
- **name** (Char)
- **email_from** (Char)
- **user_id** (Many2one) → res.users
- **container_id** (Many2one) → mail.test.container
- **company_id** (Many2one) → res.company
- **track_fields_tofilter** (Char)
- **track_enable_default_log** (Boolean)





### mail.test.activity


- Hereda de:


  - mail.thread

  - mail.activity.mixin





#### Campos
- **name** (Char)
- **date** (Date)
- **email_from** (Char)
- **active** (Boolean)
- **company_id** (Many2one) → res.company





### mail.test.ticket


- Hereda de:


  - mail.thread





#### Campos
- **name** (Char)
- **email_from** (Char)
- **mobile_number** (Char)
- **phone_number** (Char)
- **count** (Integer)
- **datetime** (Datetime)
- **mail_template** (Many2one) → mail.template
- **customer_id** (Many2one) → res.partner
- **user_id** (Many2one) → res.users
- **container_id** (Many2one) → mail.test.container





### mail.test.ticket.el


- Hereda de:


  - mail.test.ticket

  - mail.thread.blacklist





#### Campos
- **email_from** (Char) → Email





### mail.test.ticket.mc


- Hereda de:


  - mail.test.ticket





#### Campos
- **company_id** (Many2one) → res.company
- **container_id** (Many2one) → mail.test.container.mc





### mail.test.container


- Hereda de:


  - mail.thread

  - mail.alias.mixin





#### Campos
- **name** (Char)
- **description** (Text)
- **customer_id** (Many2one) → res.partner





### mail.test.container.mc


- Hereda de:


  - mail.test.container





#### Campos
- **company_id** (Many2one) → res.company





### mail.test.composer.mixin


- Hereda de:


  - mail.composer.mixin





#### Campos
- **name** (Char) → Name
- **author_id** (Many2one) → res.partner
- **description** (Html) → Description
- **source_ids** (Many2many) → mail.test.composer.source





### mail.test.composer.source


- Hereda de:


  - mail.thread.blacklist





#### Campos
- **name** (Char) → Name
- **customer_id** (Many2one) → res.partner
- **email_from** (Char) → Email





### mail.test.mail.tracking.duration


- Hereda de:


  - mail.thread

  - mail.tracking.duration.mixin





#### Campos
- **name** (Char)
- **customer_id** (Many2one) → res.partner





### mail.test.public


- Hereda de:


  - mail.thread





#### Campos
- **name** (Char) → Name





### mail.performance.thread


- Hereda de:


  - mail.thread





#### Campos
- **name** (Char)
- **value** (Integer)
- **value_pc** (Float)
- **track** (Char)
- **partner_id** (Many2one) → res.partner





### mail.performance.tracking


- Hereda de:


  - mail.thread





#### Campos
- **name** (Char)
- **field_0** (Char)
- **field_1** (Char)
- **field_2** (Char)





### mail.test.field.type


- Hereda de:


  - mail.thread





#### Campos
- **name** (Char)
- **email_from** (Char)
- **datetime** (Datetime)
- **customer_id** (Many2one) → res.partner
- **type** (Selection)
- **user_id** (Many2one) → res.users





### mail.test.lang


- Hereda de:


  - mail.thread





#### Campos
- **name** (Char)
- **email_from** (Char)
- **customer_id** (Many2one) → res.partner
- **lang** (Char) → Lang





### mail.test.track.all.m2m


- Hereda de:


  - mail.thread





#### Campos
- **name** (Char) → Name





### mail.test.track.all.o2m


- Hereda de:


  - mail.thread





#### Campos
- **name** (Char) → Name
- **mail_track_all_id** (Many2one) → mail.test.track.all





### mail.test.track.all


- Hereda de:


  - mail.thread





#### Campos
- **boolean_field** (Boolean) → Boolean
- **char_field** (Char) → Char
- **company_id** (Many2one) → res.company
- **currency_id** (Many2one) → res.currency
- **date_field** (Date) → Date
- **datetime_field** (Datetime) → Datetime
- **float_field** (Float) → Float
- **float_field_with_digits** (Float) → Precise Float
- **html_field** (Html) → Html
- **integer_field** (Integer) → Integer
- **many2many_field** (Many2many) → mail.test.track.all.m2m
- **many2one_field_id** (Many2one) → res.partner
- **monetary_field** (Monetary) → Monetary
- **one2many_field** (One2many) → mail.test.track.all.o2m
- **selection_field** (Selection)
- **text_field** (Text) → Text
- **name** (Char) → Name





### mail.test.track.compute


- Hereda de:


  - mail.thread





#### Campos
- **partner_id** (Many2one) → res.partner
- **partner_name** (Char)
- **partner_email** (Char)
- **partner_phone** (Char)





### mail.test.track.groups


- Hereda de:


  - mail.thread





#### Campos
- **name** (Char)
- **partner_id** (Many2one) → res.partner
- **secret** (Char)





### mail.test.track.monetary


- Hereda de:


  - mail.thread





#### Campos
- **company_id** (Many2one) → res.company
- **company_currency** (Many2one) → res.currency
- **revenue** (Monetary) → Revenue





### mail.test.track.selection


- Hereda de:


  - mail.thread





#### Campos
- **name** (Char)
- **selection_type** (Selection)





### mail.test.multi.company


- Hereda de:

  - mail.thread.main.attachment




#### Campos
- **name** (Char)
- **company_id** (Many2one) → res.company





### mail.test.multi.company.read


- Hereda de:


  - mail.test.multi.company





- No agrega campos




### mail.test.multi.company.with.activity


- Hereda de:


  - mail.thread

  - mail.activity.mixin





#### Campos
- **name** (Char)
- **company_id** (Many2one) → res.company





### mail.test.nothread


- Hereda de: Base



#### Campos
- **name** (Char)
- **company_id** (Many2one) → res.company
- **customer_id** (Many2one) → res.partner







