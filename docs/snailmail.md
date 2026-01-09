# Módulo: Snail Mail

## Información General
- **Nombre técnico:** snailmail
- **Versión:** 0.4
- **Categoría:** Hidden/Tools
- **Dependencias:** iap_mail, mail




## Descripción

Allows users to send documents by post
=====================================================
        



## Modelos

### mail.thread


- Hereda de:

  - mail.thread




- No agrega campos




### ir.actions.report


- Hereda de:

  - ir.actions.report




- No agrega campos




### mail.notification


- Hereda de:

  - mail.notification




#### Campos
- **notification_type** (Selection)
- **letter_id** (Many2one) → snailmail.letter
- **failure_type** (Selection)





### mail.message


- Hereda de:

  - mail.message




#### Campos
- **snailmail_error** (Boolean)
- **letter_ids** (One2many) → snailmail.letter
- **message_type** (Selection)





### snailmail.letter


- Hereda de: Base



#### Campos
- **user_id** (Many2one) → res.users
- **model** (Char) → Model
- **res_id** (Integer) → Document ID
- **partner_id** (Many2one) → res.partner
- **company_id** (Many2one) → res.company
- **report_template** (Many2one) → ir.actions.report
- **attachment_id** (Many2one) → ir.attachment
- **attachment_datas** (Binary) → Document
- **attachment_fname** (Char) → Attachment Filename
- **color** (Boolean)
- **cover** (Boolean)
- **duplex** (Boolean)
- **state** (Selection)
- **error_code** (Selection)
- **info_msg** (Html) → Information
- **reference** (Char)
- **message_id** (Many2one) → mail.message
- **notification_ids** (One2many) → mail.notification
- **street** (Char) → Street
- **street2** (Char) → Street2
- **zip** (Char) → Zip
- **city** (Char) → City
- **state_id** (Many2one) → res.country.state
- **country_id** (Many2one) → res.country





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | snailmail.letter.list | `snailmail.snailmail_letter_list` | - |
| form | snailmail.letter.form | `snailmail.snailmail_letter_form` | - |



**Botones (snailmail.snailmail_letter_form):**
- **Send Now** (object)
- **Cancel** (object)



### res.config.settings


- Hereda de:

  - res.config.settings




#### Campos
- **snailmail_color** (Boolean)
- **snailmail_cover** (Boolean)
- **snailmail_duplex** (Boolean)
- **snailmail_cover_readonly** (Boolean)





### res.company


- Hereda de:

  - res.company




#### Campos
- **snailmail_color** (Boolean)
- **snailmail_cover** (Boolean)
- **snailmail_duplex** (Boolean)





### res.partner


- Hereda de:

  - res.partner




- No agrega campos









## Vistas Adicionales


### snailmail.letter.format.error

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | snailmail.letter.format.error.form | `snailmail.snailmail_letter_format_error` | - |



**Botones (snailmail.snailmail_letter_format_error):**
- **Update Config and Re-send** (object)
- **Cancel Letter** (object)


### snailmail.letter.missing.required.fields

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | snailmail.letter.missing.required.fields.form | `snailmail.snailmail_letter_missing_required_fields` | - |



**Botones (snailmail.snailmail_letter_missing_required_fields):**
- **Update address and re-send** (object)
- **Cancel letter** (object)



