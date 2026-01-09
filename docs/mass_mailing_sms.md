# Módulo: SMS Marketing

## Información General
- **Nombre técnico:** mass_mailing_sms
- **Versión:** 1.1
- **Categoría:** Marketing/Email Marketing
- **Dependencias:** portal, mass_mailing, sms


## Propósito
Design, send and track SMS





## Modelos

### utm.campaign


- Hereda de:

  - utm.campaign




#### Campos
- **mailing_sms_ids** (One2many) → mailing.mailing
- **mailing_sms_count** (Integer) → Number of Mass SMS
- **ab_testing_mailings_sms_count** (Integer) → A/B Test Mailings SMS #
- **ab_testing_sms_winner_selection** (Selection)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | utm.campaign.view.form | `mass_mailing_sms.utm_campaign_view_form` | utm.utm_campaign_view_form |




### utm.medium


- Hereda de:

  - utm.medium




- No agrega campos




### mailing.contact


- Hereda de:


  - mailing.contact

  - mail.thread.phone





#### Campos
- **mobile** (Char)





### sms.tracker


- Hereda de:

  - sms.tracker




#### Campos
- **mailing_trace_id** (Many2one) → mailing.trace





### mailing.list


- Hereda de:

  - mailing.list




#### Campos
- **contact_count_sms** (Integer)





### mailing.trace


- Hereda de:

  - mailing.trace




#### Campos
- **trace_type** (Selection)
- **sms_id** (Many2one) → sms.sms
- **sms_id_int** (Integer)
- **sms_tracker_ids** (One2many) → sms.tracker
- **sms_number** (Char) → Number
- **sms_code** (Char) → Code
- **failure_type** (Selection)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | mailing.trace.view.list.sms | `mass_mailing_sms.mailing_trace_view_tree_sms` | - |
| form | mailing.trace.view.form.sms | `mass_mailing_sms.mailing_trace_view_form_sms` | - |



**Botones (mass_mailing_sms.mailing_trace_view_form_sms):**
- **action_view_contact** (object)



### ['sms.sms']


- Hereda de:


  - sms.sms





#### Campos
- **mailing_id** (Many2one) → mailing.mailing
- **mailing_trace_ids** (One2many) → mailing.trace





### res.users


- Hereda de:


  - res.users





- No agrega campos




### mailing.mailing


- Hereda de:

  - mailing.mailing




#### Campos
- **mailing_type** (Selection)
- **sms_subject** (Char) → Title
- **body_plaintext** (Text) → SMS Body
- **sms_template_id** (Many2one) → sms.template
- **sms_has_insufficient_credit** (Boolean) → Insufficient IAP credits
- **sms_has_unregistered_account** (Boolean) → Unregistered IAP account
- **sms_force_send** (Boolean) → Send Directly
- **sms_allow_unsubscribe** (Boolean) → Include opt-out link
- **ab_testing_sms_winner_selection** (Selection)
- **ab_testing_mailings_sms_count** (Integer)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | mailing.mailing.view.list.sms | `mass_mailing_sms.mailing_mailing_view_tree_sms` | - |









## Vistas Adicionales


### mailing.sms.test

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | mailing.sms.test.view.form | `mass_mailing_sms.mailing_sms_test_view_form` | - |



**Botones (mass_mailing_sms.mailing_sms_test_view_form):**
- **Send Test** (object)



