# Módulo: Twilio SMS

## Información General
- **Nombre técnico:** sms_twilio
- **Versión:** 1.0
- **Categoría:** Hidden/Tools
- **Dependencias:** sms


## Propósito
Send SMS messages using Twilio



## Descripción

This module allows using Twilio as a provider for SMS messaging.
The user has to create an account on twilio.com and top
up their account to start sending SMS messages.




## Modelos

### sms.tracker


- Hereda de:

  - sms.tracker




- Campos:

  - **sms_twilio_sid** (Char)





### mail.notification


- Hereda de:

  - mail.notification




- Campos:

  - **failure_type** (Selection)





### sms.twilio.number


- Hereda de: Base



- Campos:

  - **company_id** (Many2one) → res.company


  - **sequence** (Integer)


  - **number** (Char)


  - **country_id** (Many2one) → res.country


  - **country_code** (Char)





### sms.sms


- Hereda de:

  - sms.sms




- Campos:

  - **sms_twilio_sid** (Char)


  - **record_company_id** (Many2one) → res.company


  - **failure_type** (Selection)





### res.config.settings


- Hereda de:

  - res.config.settings




- Campos:

  - **sms_provider** (Selection)





### res.company


- Hereda de:

  - res.company




- Campos:

  - **sms_provider** (Selection)


  - **sms_twilio_account_sid** (Char) → Account SID


  - **sms_twilio_auth_token** (Char) → Auth Token


  - **sms_twilio_number_ids** (One2many) → sms.twilio.number





### sms.composer


- Hereda de:

  - sms.composer




- No agrega campos






## Vistas


### sms.twilio.account.manage

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | sms.twilio.account.manage.view.form | `sms_twilio.sms_twilio_account_manage_view_form` | - |



#### Botones (sms_twilio.sms_twilio_account_manage_view_form)
- **Send test SMS** (object)
- **Reload Numbers from Twilio** (object)
- **action_unlink** (object)
- **Update Account** (object)

