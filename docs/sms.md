# Módulo: SMS gateway

## Información General
- **Nombre técnico:** sms
- **Versión:** 3.0
- **Categoría:** Hidden/Tools
- **Dependencias:** base, iap_mail, mail, phone_validation


## Propósito
SMS Text Messaging



## Descripción

This module gives a framework for SMS text messaging
----------------------------------------------------

The service is provided by the In App Purchase Odoo platform.




## Modelos

### ir.actions.server


- Hereda de:


  - ir.actions.server





- Campos:

  - **state** (Selection)


  - **sms_template_id** (Many2one) → sms.template


  - **sms_method** (Selection)





### mail.thread


- Hereda de:

  - mail.thread




- Campos:

  - **message_has_sms_error** (Boolean) → SMS Delivery error





### ['mail.followers']


- Hereda de:


  - mail.followers





- No agrega campos



### sms.tracker


- Hereda de: Base



- Campos:

  - **sms_uuid** (Char) → SMS uuid


  - **mail_notification_id** (Many2one) → mail.notification





### ir.model


- Hereda de:

  - ir.model




- Campos:

  - **is_mail_thread_sms** (Boolean)





### mail.notification


- Hereda de:

  - mail.notification




- Campos:

  - **notification_type** (Selection)


  - **sms_id_int** (Integer) → SMS ID


  - **sms_id** (Many2one) → sms.sms


  - **sms_tracker_ids** (One2many) → sms.tracker


  - **sms_number** (Char) → SMS Number


  - **failure_type** (Selection)





### mail.message


- Hereda de:

  - mail.message




- Campos:

  - **message_type** (Selection)


  - **has_sms_error** (Boolean) → Has SMS error





### sms.sms


- Hereda de: Base



- Campos:

  - **uuid** (Char) → UUID


  - **number** (Char) → Number


  - **body** (Text)


  - **partner_id** (Many2one) → res.partner


  - **mail_message_id** (Many2one) → mail.message


  - **state** (Selection)


  - **failure_type** (Selection)


  - **sms_tracker_id** (Many2one) → sms.tracker


  - **to_delete** (Boolean) → Marked for deletion





### res.company


- Hereda de:

  - res.company




- No agrega campos



### sms.template


- Hereda de:


  - mail.render.mixin

  - template.reset.mixin





- Campos:

  - **name** (Char) → Name


  - **model_id** (Many2one) → ir.model


  - **model** (Char) → Related Document Model


  - **body** (Char) → Body


  - **sidebar_action_id** (Many2one) → ir.actions.act_window





### iap.account


- Hereda de:

  - iap.account




- Campos:

  - **sender_name** (Char)





### res.partner


- Hereda de:


  - mail.thread.phone

  - res.partner





- No agrega campos



### base


- Hereda de:

  - base




- No agrega campos






## Vistas


### sms.sms

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | sms.sms.view.form | `sms.sms_tsms_view_form` | - |
| list | sms.sms.view.list | `sms.sms_sms_view_tree` | - |
| search | sms.sms.view.search | `sms.sms_sms_view_search` | - |



#### Botones (sms.sms_tsms_view_form)
- **Send Now** (object)
- **Retry** (object)
- **Cancel** (object)


### sms.template

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | sms.template.view.form | `sms.sms_template_view_form` | - |
| list | sms.template.view.list | `sms.sms_template_view_tree` | - |
| search | sms.template.view.search | `sms.sms_template_view_search` | - |



#### Botones (sms.sms_template_view_form)
- **Reset Template** (action) - Grupos: `base.group_system`
- **action_create_sidebar_action** (object) - Grupos: `base.group_no_one`
- **action_unlink_sidebar_action** (object) - Grupos: `base.group_no_one`
- **%(sms_template_preview_action)d** (action)


### sms.resend

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | sms.resend.form | `sms.mail_resend_message_view_form` | - |



#### Botones (sms.mail_resend_message_view_form)
- **Buy credits** (object)
- **Set up an account** (object)
- **Send & Close** (object)
- **Ignore all** (object)
- **Ignore all** (object)


### sms.template.reset

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | sms.template.reset.view.form | `sms.sms_template_reset_view_form` | - |



#### Botones (sms.sms_template_reset_view_form)
- **Proceed** (object)


### sms.account.sender

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | sms.account.sender.view.form | `sms.sms_account_sender_view_form` | - |



#### Botones (sms.sms_account_sender_view_form)
- **Set sender name** (object)


### sms.template.preview

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | sms.template.preview.form | `sms.sms_template_preview_form` | - |



### sms.composer

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | sms.composer.view.form | `sms.sms_composer_view_form` | - |



#### Botones (sms.sms_composer_view_form)
- **Send SMS** (object)
- **Send SMS** (object)
- **Put in queue** (object)
- **Send Now** (object)


### sms.account.code

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | sms.account.code.view.form | `sms.sms_account_code_view_form` | - |



#### Botones (sms.sms_account_code_view_form)
- **Register** (object)


### sms.account.phone

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | sms.account.phone.view.form | `sms.sms_account_phone_view_form` | - |



#### Botones (sms.sms_account_phone_view_form)
- **Send verification code** (object)

