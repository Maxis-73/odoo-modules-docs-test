# Módulo: Discuss

## Información General
- **Nombre técnico:** mail
- **Versión:** 1.18
- **Categoría:** Productivity/Discuss
- **Dependencias:** base, base_setup, bus, web_tour, html_editor


## Propósito
Chat, mail gateway and private channels



## Descripción


Chat, mail gateway and private channel.

Communicate with your colleagues/customers/guest within Odoo.

Discuss/Chat
------------
User-friendly "Discuss" features that allows one 2 one or group communication
(text chat/voice call/video call), invite guests and share documents with
them, all real-time.

Mail gateway
------------
Sending information and documents made simplified. You can send emails
from Odoo itself, and that too with great possibilities. For example,
design a beautiful email template for the invoices, and use the same
for all your customers, no need to do the same exercise every time.

Chatter
-------
Do all the contextual conversation on a document. For example on an
applicant, directly post an update to send email to the applicant,
schedule the next interview call, attach the contract, add HR officer
to the follower list to notify them for important events(with help of
subtypes),...


Retrieve incoming email on POP/IMAP servers.
Enter the parameters of your POP/IMAP account(s), and any incoming emails on
these accounts will be automatically downloaded into your Odoo system. All
POP3/IMAP-compatible servers are supported, included those that require an
encrypted SSL/TLS connection.
This can be used to easily create email-based workflows for many email-enabled Odoo documents, such as:
----------------------------------------------------------------------------------------------------------
    * CRM Leads/Opportunities
    * CRM Claims
    * Project Issues
    * Project Tasks
    * Human Resource Recruitment (Applicants)
Just install the relevant application, and you can assign any of these document
types (Leads, Project Issues) to your incoming email accounts. New emails will
automatically spawn new documents of the chosen type, so it's a snap to create a
mailbox-to-Odoo integration. Even better: these documents directly act as mini
conversations synchronized by email. You can reply from within Odoo, and the
answers will automatically be collected when they come back, and attached to the
same *conversation* document.
For more specific needs, you may also assign custom-defined actions
(technically: Server Actions) to be triggered for each incoming mail.
    



## Modelos

### ir.actions.server


- Hereda de:


  - ir.actions.server





- Campos:

  - **state** (Selection)


  - **partner_ids** (Many2many) → res.partner


  - **template_id** (Many2one) → mail.template


  - **mail_post_autofollow** (Boolean) → Subscribe Recipients


  - **mail_post_method** (Selection)


  - **activity_type_id** (Many2one) → mail.activity.type


  - **activity_summary** (Char) → Title


  - **activity_note** (Html) → Note


  - **activity_date_deadline_range** (Integer)


  - **activity_date_deadline_range_type** (Selection)


  - **activity_user_type** (Selection)


  - **activity_user_id** (Many2one) → res.users


  - **activity_user_field_name** (Char) → User Field





### mail.thread.cc


- Hereda de:

  - mail.thread




- Campos:

  - **email_cc** (Char) → Email cc





### ir.mail_server


- Hereda de:


  - ir.mail_server





- Campos:

  - **mail_template_ids** (One2many) → mail.template





### mail.link.preview


- Hereda de:

  - bus.listener.mixin




- Campos:

  - **message_id** (Many2one) → mail.message


  - **is_hidden** (Boolean)


  - **source_url** (Char) → URL


  - **og_type** (Char) → Type


  - **og_title** (Char) → Title


  - **og_site_name** (Char) → Site name


  - **og_image** (Char) → Image


  - **og_description** (Text) → Description


  - **og_mimetype** (Char) → MIME type


  - **image_mimetype** (Char) → Image MIME type


  - **create_date** (Datetime)





### mail.mail


- Hereda de: Base



- Campos:

  - **mail_message_id** (Many2one) → mail.message


  - **mail_message_id_int** (Integer)


  - **message_type** (Selection)


  - **body_html** (Text) → Text Contents


  - **body_content** (Html) → Rich-text Contents


  - **references** (Text) → References


  - **headers** (Text) → Headers


  - **restricted_attachment_count** (Integer) → Restricted attachments


  - **unrestricted_attachment_ids** (Many2many) → ir.attachment


  - **is_notification** (Boolean) → Notification Email


  - **email_to** (Text) → To


  - **email_cc** (Char) → Cc


  - **recipient_ids** (Many2many) → res.partner


  - **state** (Selection)


  - **failure_type** (Selection)


  - **failure_reason** (Text) → Failure Reason


  - **auto_delete** (Boolean) → Auto Delete


  - **scheduled_date** (Datetime) → Scheduled Send Date


  - **fetchmail_server_id** (Many2one) → fetchmail.server





### mail.canned.response


- Hereda de: Base



- Campos:

  - **source** (Char) → Shortcut


  - **substitution** (Text) → Substitution


  - **description** (Char) → Description


  - **last_used** (Datetime) → Last Used


  - **group_ids** (Many2many) → res.groups


  - **is_shared** (Boolean)


  - **is_editable** (Boolean)





### mail.blacklist


- Hereda de:


  - mail.thread





- Campos:

  - **email** (Char)


  - **active** (Boolean)





### mail.thread


- Hereda de: Base



- Campos:

  - **message_is_follower** (Boolean) → Is Follower


  - **message_follower_ids** (One2many) → mail.followers


  - **message_partner_ids** (Many2many) → res.partner


  - **message_ids** (One2many) → mail.message


  - **has_message** (Boolean)


  - **message_needaction** (Boolean) → Action Needed


  - **message_needaction_counter** (Integer) → Number of Actions


  - **message_has_error** (Boolean) → Message Delivery error


  - **message_has_error_counter** (Integer) → Number of errors


  - **message_attachment_count** (Integer) → Attachment Count





### mail.activity.type


- Hereda de: Base



- Campos:

  - **name** (Char) → Name


  - **summary** (Char) → Default Summary


  - **sequence** (Integer) → Sequence


  - **active** (Boolean)


  - **create_uid** (Many2one) → res.users


  - **delay_count** (Integer) → Schedule


  - **delay_unit** (Selection)


  - **delay_label** (Char)


  - **delay_from** (Selection)


  - **icon** (Char) → Icon


  - **decoration_type** (Selection)


  - **res_model** (Selection)


  - **triggered_next_type_id** (Many2one) → mail.activity.type


  - **chaining_type** (Selection)


  - **suggested_next_type_ids** (Many2many) → mail.activity.type


  - **previous_type_ids** (Many2many) → mail.activity.type


  - **category** (Selection)


  - **mail_template_ids** (Many2many) → mail.template


  - **default_user_id** (Many2one) → res.users


  - **default_note** (Html)


  - **keep_done** (Boolean)


  - **initial_res_model** (Selection)


  - **res_model_change** (Boolean)





### mail.thread.main.attachment


- Hereda de:

  - mail.thread




- Campos:

  - **message_main_attachment_id** (Many2one) → ir.attachment





### mail.gateway.allowed


- Hereda de: Base



- Campos:

  - **email** (Char) → Email Address


  - **email_normalized** (Char)





### ir.ui.view


- Hereda de:

  - ir.ui.view




- Campos:

  - **type** (Selection)





### mail.scheduled.message


- Hereda de: Base



- Campos:

  - **subject** (Char) → Subject


  - **body** (Html) → Contents


  - **scheduled_date** (Datetime) → Scheduled Date


  - **attachment_ids** (Many2many) → ir.attachment


  - **model** (Char) → Related Document Model


  - **res_id** (Many2oneReference) → Related Document Id


  - **author_id** (Many2one) → res.partner


  - **partner_ids** (Many2many) → res.partner


  - **is_note** (Boolean) → Is a note


  - **notification_parameters** (Text) → Notification parameters





### mail.message.reaction


- Hereda de: Base



- Campos:

  - **message_id** (Many2one) → mail.message


  - **content** (Char)


  - **partner_id** (Many2one) → res.partner


  - **guest_id** (Many2one) → mail.guest





### mail.message.schedule


- Hereda de: Base



- Campos:

  - **mail_message_id** (Many2one) → mail.message


  - **notification_parameters** (Text) → Notification Parameter


  - **scheduled_datetime** (Datetime) → Scheduled Send Date





### mail.followers


- Hereda de: Base



- Campos:

  - **res_model** (Char) → Related Document Model Name


  - **res_id** (Many2oneReference) → Related Document ID


  - **partner_id** (Many2one) → res.partner


  - **subtype_ids** (Many2many) → mail.message.subtype


  - **name** (Char) → Name


  - **email** (Char) → Email


  - **is_active** (Boolean) → Is Active





### fetchmail.server


- Hereda de: Base



- Campos:

  - **name** (Char) → Name


  - **active** (Boolean) → Active


  - **state** (Selection)


  - **server** (Char)


  - **port** (Integer)


  - **server_type** (Selection)


  - **server_type_info** (Text) → Server Type Info


  - **is_ssl** (Boolean) → SSL/TLS


  - **attach** (Boolean) → Keep Attachments


  - **original** (Boolean) → Keep Original


  - **date** (Datetime)


  - **user** (Char)


  - **password** (Char)


  - **object_id** (Many2one) → ir.model


  - **priority** (Integer)


  - **message_ids** (One2many) → mail.mail


  - **configuration** (Text) → Configuration


  - **script** (Char)





### template.reset.mixin


- Hereda de: Base



- Campos:

  - **template_fs** (Char)





### mail.alias.mixin


- Hereda de:

  - mail.alias.mixin.optional




- Campos:

  - **alias_id** (Many2one)


  - **alias_name** (Char)


  - **alias_defaults** (Text)





### mail.render.mixin


- Hereda de: Base



- Campos:

  - **lang** (Char) → Language


  - **render_model** (Char) → Rendering Model





### ir.cron


- Hereda de:

  - ir.cron




- No agrega campos



### mail.message.subtype


- Hereda de: Base



- Campos:

  - **name** (Char) → Message Type


  - **description** (Text) → Description


  - **internal** (Boolean) → Internal Only


  - **parent_id** (Many2one) → mail.message.subtype


  - **relation_field** (Char) → Relation field


  - **res_model** (Char) → Model


  - **default** (Boolean) → Default


  - **sequence** (Integer) → Sequence


  - **hidden** (Boolean) → Hidden


  - **track_recipients** (Boolean) → Track Recipients





### mail.activity.plan


- Hereda de: Base



- Campos:

  - **name** (Char) → Name


  - **company_id** (Many2one) → res.company


  - **template_ids** (One2many) → mail.activity.plan.template


  - **active** (Boolean)


  - **res_model_id** (Many2one) → ir.model


  - **res_model** (Selection)


  - **steps_count** (Integer)


  - **has_user_on_demand** (Boolean) → Has on demand responsible





### ir.model


- Hereda de:

  - ir.model




- Campos:

  - **is_mail_thread** (Boolean)


  - **is_mail_activity** (Boolean)


  - **is_mail_blacklist** (Boolean)





### ir.model.fields


- Hereda de:

  - ir.model.fields




- Campos:

  - **tracking** (Integer)





### mail.activity.mixin


- Hereda de: Base



- Campos:

  - **activity_ids** (One2many) → mail.activity


  - **activity_state** (Selection)


  - **activity_user_id** (Many2one) → res.users


  - **activity_type_id** (Many2one) → mail.activity.type


  - **activity_type_icon** (Char) → Activity Type Icon


  - **activity_date_deadline** (Date) → Next Activity Deadline


  - **my_activity_date_deadline** (Date) → My Activity Deadline


  - **activity_summary** (Char) → Next Activity Summary


  - **activity_exception_decoration** (Selection)


  - **activity_exception_icon** (Char) → Icon





### mail.notification


- Hereda de: Base



- Campos:

  - **author_id** (Many2one) → res.partner


  - **mail_message_id** (Many2one) → mail.message


  - **mail_mail_id** (Many2one) → mail.mail


  - **res_partner_id** (Many2one) → res.partner


  - **notification_type** (Selection)


  - **notification_status** (Selection)


  - **is_read** (Boolean) → Is Read


  - **read_date** (Datetime) → Read Date


  - **failure_type** (Selection)


  - **failure_reason** (Text) → Failure reason





### mail.message


- Hereda de:


  - bus.listener.mixin





- Campos:

  - **subject** (Char) → Subject


  - **date** (Datetime) → Date


  - **body** (Html) → Contents


  - **preview** (Char) → Preview


  - **link_preview_ids** (One2many) → mail.link.preview


  - **reaction_ids** (One2many) → mail.message.reaction


  - **attachment_ids** (Many2many) → ir.attachment


  - **parent_id** (Many2one) → mail.message


  - **child_ids** (One2many) → mail.message


  - **model** (Char) → Related Document Model


  - **res_id** (Many2oneReference) → Related Document ID


  - **record_name** (Char) → Message Record Name


  - **record_alias_domain_id** (Many2one) → mail.alias.domain


  - **record_company_id** (Many2one) → res.company


  - **message_type** (Selection)


  - **subtype_id** (Many2one) → mail.message.subtype


  - **mail_activity_type_id** (Many2one) → mail.activity.type


  - **is_internal** (Boolean) → Employee Only


  - **email_from** (Char) → From


  - **author_id** (Many2one) → res.partner


  - **author_avatar** (Binary) → Author's avatar


  - **author_guest_id** (Many2one) → mail.guest


  - **is_current_user_or_guest_author** (Boolean)


  - **partner_ids** (Many2many) → res.partner


  - **notified_partner_ids** (Many2many) → res.partner


  - **needaction** (Boolean) → Need Action


  - **has_error** (Boolean) → Has error


  - **notification_ids** (One2many) → mail.notification


  - **starred_partner_ids** (Many2many) → res.partner


  - **pinned_at** (Datetime) → Pinned


  - **starred** (Boolean) → Starred


  - **tracking_value_ids** (One2many) → mail.tracking.value


  - **reply_to_force_new** (Boolean) → No threading for answers


  - **message_id** (Char) → Message-Id


  - **reply_to** (Char) → Reply-To


  - **mail_server_id** (Many2one) → ir.mail_server


  - **email_layout_xmlid** (Char) → Layout


  - **email_add_signature** (Boolean)


  - **mail_ids** (One2many) → mail.mail





### mail.alias.mixin.optional


- Hereda de: Base



- Campos:

  - **alias_id** (Many2one) → mail.alias


  - **alias_name** (Char)


  - **alias_domain_id** (Many2one) → mail.alias.domain


  - **alias_domain** (Char) → Alias Domain Name


  - **alias_defaults** (Text)


  - **alias_email** (Char) → Email Alias





### mail.tracking.value


- Hereda de: Base



- Campos:

  - **field_id** (Many2one) → ir.model.fields


  - **field_info** (Json) → Removed field information


  - **old_value_integer** (Integer) → Old Value Integer


  - **old_value_float** (Float) → Old Value Float


  - **old_value_char** (Char) → Old Value Char


  - **old_value_text** (Text) → Old Value Text


  - **old_value_datetime** (Datetime) → Old Value DateTime


  - **new_value_integer** (Integer) → New Value Integer


  - **new_value_float** (Float) → New Value Float


  - **new_value_char** (Char) → New Value Char


  - **new_value_text** (Text) → New Value Text


  - **new_value_datetime** (Datetime) → New Value Datetime


  - **currency_id** (Many2one) → res.currency


  - **mail_message_id** (Many2one) → mail.message





### mail.message.translation


- Hereda de: Base



- Campos:

  - **message_id** (Many2one) → mail.message


  - **source_lang** (Char) → Source Language


  - **target_lang** (Char) → Target Language


  - **body** (Html) → Translation Body


  - **create_date** (Datetime)





### res.users


- Hereda de:


  - res.users





- Campos:

  - **notification_type** (Selection)





### ir.attachment


- Hereda de:

  - ir.attachment




- No agrega campos



### mail.activity.plan.template


- Hereda de: Base



- Campos:

  - **plan_id** (Many2one) → mail.activity.plan


  - **res_model** (Selection)


  - **company_id** (Many2one)


  - **sequence** (Integer)


  - **activity_type_id** (Many2one) → mail.activity.type


  - **delay_count** (Integer) → Interval


  - **delay_unit** (Selection)


  - **delay_from** (Selection)


  - **icon** (Char) → Icon


  - **summary** (Char) → Summary


  - **responsible_type** (Selection)


  - **responsible_id** (Many2one) → res.users


  - **note** (Html) → Note





### res.users.settings.volumes


- Hereda de: Base



- Campos:

  - **user_setting_id** (Many2one) → res.users.settings


  - **partner_id** (Many2one) → res.partner


  - **guest_id** (Many2one) → res.partner


  - **volume** (Float)





### mail.push


- Hereda de: Base



- Campos:

  - **mail_push_device_id** (Many2one) → mail.push.device


  - **payload** (Text)





### res.config.settings


- Hereda de:

  - res.config.settings




- Campos:

  - **external_email_server_default** (Boolean) → Use Custom Email Servers


  - **fail_counter** (Integer) → Fail Mail


  - **alias_domain_id** (Many2one) → mail.alias.domain


  - **module_google_gmail** (Boolean) → Support Gmail Authentication


  - **module_microsoft_outlook** (Boolean) → Support Outlook Authentication


  - **restrict_template_rendering** (Boolean) → Restrict Template Rendering


  - **use_twilio_rtc_servers** (Boolean) → Use Twilio ICE servers


  - **twilio_account_sid** (Char) → Twilio Account SID


  - **twilio_account_token** (Char) → Twilio Account Auth Token


  - **sfu_server_url** (Char) → SFU Server URL


  - **sfu_server_key** (Char) → SFU Server key


  - **email_primary_color** (Char)


  - **email_secondary_color** (Char)


  - **tenor_api_key** (Char) → Tenor API key


  - **tenor_content_filter** (Selection)


  - **tenor_gif_limit** (Integer)


  - **google_translate_api_key** (Char) → Message Translation API Key





### publisher_warranty.contract


- Hereda de: Base



- No agrega campos



### mail.template


- Hereda de:


  - mail.render.mixin

  - template.reset.mixin





- Campos:

  - **name** (Char) → Name


  - **description** (Text) → Template Description


  - **active** (Boolean)


  - **template_category** (Selection)


  - **model_id** (Many2one) → ir.model


  - **model** (Char) → Related Document Model


  - **subject** (Char) → Subject


  - **email_from** (Char) → From


  - **user_id** (Many2one) → res.users


  - **use_default_to** (Boolean) → Default recipients


  - **email_to** (Char) → To (Emails)


  - **partner_to** (Char) → To (Partners)


  - **email_cc** (Char) → Cc


  - **reply_to** (Char) → Reply To


  - **body_html** (Html) → Body


  - **attachment_ids** (Many2many) → ir.attachment


  - **report_template_ids** (Many2many) → ir.actions.report


  - **email_layout_xmlid** (Char) → Email Notification Layout


  - **mail_server_id** (Many2one) → ir.mail_server


  - **scheduled_date** (Char) → Scheduled Date


  - **auto_delete** (Boolean) → Auto Delete


  - **ref_ir_act_window** (Many2one) → ir.actions.act_window


  - **can_write** (Boolean)


  - **is_template_editor** (Boolean)





### bus.listener.mixin


- Hereda de:

  - bus.listener.mixin




- No agrega campos



### ir.ui.menu


- Hereda de:

  - ir.ui.menu




- No agrega campos



### ir.config_parameter


- Hereda de:

  - ir.config_parameter




- No agrega campos



### mail.activity


- Hereda de: Base



- Campos:

  - **res_model_id** (Many2one) → ir.model


  - **res_model** (Char) → Related Document Model


  - **res_id** (Many2oneReference)


  - **res_name** (Char) → Document Name


  - **activity_type_id** (Many2one) → mail.activity.type


  - **activity_category** (Selection)


  - **activity_decoration** (Selection)


  - **icon** (Char) → Icon


  - **summary** (Char) → Summary


  - **note** (Html) → Note


  - **date_deadline** (Date) → Due Date


  - **date_done** (Date) → Done Date


  - **automated** (Boolean) → Automated activity


  - **attachment_ids** (Many2many) → ir.attachment


  - **user_id** (Many2one) → res.users


  - **user_tz** (Selection)


  - **request_partner_id** (Many2one) → res.partner


  - **state** (Selection)


  - **recommended_activity_type_id** (Many2one) → mail.activity.type


  - **previous_activity_type_id** (Many2one) → mail.activity.type


  - **has_recommended_activities** (Boolean) → Next activities available


  - **mail_template_ids** (Many2many)


  - **chaining_type** (Selection)


  - **can_write** (Boolean)


  - **active** (Boolean)





### mail.ice.server


- Hereda de: Base



- Campos:

  - **server_type** (Selection)


  - **uri** (Char) → URI


  - **username** (Char)


  - **credential** (Char)





### res.company


- Hereda de:

  - res.company




- Campos:

  - **alias_domain_id** (Many2one) → mail.alias.domain


  - **alias_domain_name** (Char) → Alias Domain Name


  - **bounce_email** (Char)


  - **bounce_formatted** (Char)


  - **catchall_email** (Char)


  - **catchall_formatted** (Char)


  - **default_from_email** (Char)


  - **email_formatted** (Char)


  - **email_primary_color** (Char) → Email Header Color


  - **email_secondary_color** (Char) → Email Button Color





### mail.tracking.duration.mixin


- Hereda de: Base



- Campos:

  - **duration_tracking** (Json)





### mail.thread.blacklist


- Hereda de:


  - mail.thread





- Campos:

  - **email_normalized** (Char)


  - **is_blacklisted** (Boolean)


  - **message_bounce** (Integer) → Bounce





### mail.alias


- Hereda de: Base



- Campos:

  - **alias_name** (Char) → Alias Name


  - **alias_full_name** (Char) → Alias Email


  - **display_name** (Char)


  - **alias_domain_id** (Many2one) → mail.alias.domain


  - **alias_domain** (Char) → Alias domain name


  - **alias_model_id** (Many2one) → ir.model


  - **alias_defaults** (Text) → Default Values


  - **alias_force_thread_id** (Integer) → Record Thread ID


  - **alias_parent_model_id** (Many2one) → ir.model


  - **alias_parent_thread_id** (Integer) → Parent Record Thread ID


  - **alias_contact** (Selection)


  - **alias_incoming_local** (Boolean) → Local-part based incoming detection


  - **alias_bounced_content** (Html) → Custom Bounced Message


  - **alias_status** (Selection)





### ir.http


- Hereda de:

  - ir.http




- No agrega campos



### ir.actions.act_window.view


- Hereda de:

  - ir.actions.act_window.view




- Campos:

  - **view_mode** (Selection)





### mail.push.device


- Hereda de: Base



- Campos:

  - **partner_id** (Many2one) → res.partner


  - **endpoint** (Char)


  - **keys** (Char)


  - **expiration_time** (Datetime)





### mail.composer.mixin


- Hereda de:

  - mail.render.mixin




- Campos:

  - **subject** (Char) → Subject


  - **body** (Html) → Contents


  - **body_has_template_value** (Boolean) → Body content is the same as the template


  - **template_id** (Many2one) → mail.template


  - **lang** (Char)


  - **is_mail_template_editor** (Boolean) → Is Editor


  - **can_edit_body** (Boolean) → Can Edit Body





### ir.qweb


- Hereda de:

  - ir.qweb




- No agrega campos



### res.partner


- Hereda de:


  - res.partner

  - mail.activity.mixin

  - mail.thread.blacklist





- Campos:

  - **name** (Char)


  - **email** (Char)


  - **phone** (Char)


  - **parent_id** (Many2one)


  - **user_id** (Many2one)


  - **vat** (Char)


  - **contact_address_inline** (Char)


  - **starred_message_ids** (Many2many) → mail.message





### ['bus.presence']


- Hereda de:


  - bus.presence





- Campos:

  - **guest_id** (Many2one) → mail.guest





### base


- Hereda de:

  - base




- No agrega campos



### res.users.settings


- Hereda de:

  - res.users.settings




- Campos:

  - **is_discuss_sidebar_category_channel_open** (Boolean)


  - **is_discuss_sidebar_category_chat_open** (Boolean)


  - **push_to_talk_key** (Char)


  - **use_push_to_talk** (Boolean)


  - **voice_active_duration** (Integer)


  - **volume_settings_ids** (One2many) → res.users.settings.volumes


  - **channel_notifications** (Selection)


  - **mute_until_dt** (Datetime)





### mail.alias.domain


- Hereda de: Base



- Campos:

  - **name** (Char) → Name


  - **company_ids** (One2many) → res.company


  - **sequence** (Integer)


  - **bounce_alias** (Char) → Bounce Alias


  - **bounce_email** (Char) → Bounce Email


  - **catchall_alias** (Char) → Catchall Alias


  - **catchall_email** (Char) → Catchall Email


  - **default_from** (Char) → Default From Alias


  - **default_from_email** (Char) → Default From








## Vistas


### mail.blacklist

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | mail.blacklist.view.list | `mail.mail_blacklist_view_tree` | - |
| form | mail.blacklist.view.form | `mail.mail_blacklist_view_form` | - |
| search | mail.blacklist.view.search | `mail.mail_blacklist_view_search` | - |



#### Botones (mail.mail_blacklist_view_form)
- **Unblacklist** (object)
- **Blacklist** (object)


#### Filtros de búsqueda (mail.mail_blacklist_view_search)

**Filtros:**
- **Archived** (`[('active','=',False)]`)


### mail.activity.type

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | mail.activity.type.view.form | `mail.mail_activity_type_view_form` | - |
| search | mail.activity.type.search | `mail.mail_activity_type_view_search` | - |
| list | mail.activity.type.view.list | `mail.mail_activity_type_view_tree` | - |
| kanban | mail.activity.type.view.kanban | `mail.mail_activity_type_view_kanban` | - |



#### Filtros de búsqueda (mail.mail_activity_type_view_search)

**Filtros:**
- **Archived** (`[('active', '=', False)]`)


### mail.activity

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | mail.activity.view.form.popup | `mail.mail_activity_view_form_popup` | - |
| form | mail.activity.view.form.without.record.access | `mail.mail_activity_view_form_without_record_access` | - |
| search | mail.activity.view.search | `mail.mail_activity_view_search` | - |
| list | mail.activity.view.list | `mail.mail_activity_view_tree` | - |
| kanban | mail.activity.view.kanban.open.target | `mail.mail_activity_view_kanban_open_target` | - |
| calendar | mail.activity.view.calendar | `mail.mail_activity_view_calendar` | - |



#### Botones (mail.mail_activity_view_form_popup)
- **action_open_document** (object)
- **Schedule** (object)
- **Save** (object)
- **Mark as Done** (object)
- **Done & Schedule Next** (object)
- **Done & Launch Next** (object)


#### Botones (mail.mail_activity_view_form_without_record_access)
- **Mark as Done** (object)


#### Filtros de búsqueda (mail.mail_activity_view_search)

**Filtros:**
- **My Activities** (`[('user_id', '=', uid)]`)
- **Overdue** (`[('date_deadline', '<', context_today().strftime('%Y-%m-%d'))]`)
- **Today** (`[('date_deadline', '=', context_today().strftime('%Y-%m-%d'))]`)
- **Future** (`[('date_deadline', '>', context_today().strftime('%Y-%m-%d'))                         ]`)
- **Done** (`[('active', '=', False)]`)


**Agrupar por:**
- Deadline
- Document Model
- Assigned To
- Created By
- Activity Type


### mail.scheduled.message

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | mail.scheduled.message.view.form | `mail.mail_scheduled_message_view_form` | - |



#### Botones (mail.mail_scheduled_message_view_form)
- **Send Now** (object)
- **Log Now** (object)


### mail.followers

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | mail.followers.list | `mail.view_followers_tree` | - |
| form | mail.followers.form | `mail.view_mail_subscription_form` | - |



### mail.ice.server

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | mail.ice.server.list | `mail.view_ice_server_tree` | - |
| form | mail.ice.server.form | `mail.view_ice_server_form` | - |



### mail.message.schedule

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | mail.message.schedule.view.form | `mail.mail_message_schedule_view_form` | - |
| list | mail.message.schedule.view.list | `mail.mail_message_schedule_view_tree` | - |
| search | mail.message.schedule.view.search | `mail.mail_message_schedule_view_search` | - |



#### Botones (mail.mail_message_schedule_view_form)
- **Force Send** (object)


### mail.tracking.value

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | mail.tracking.value.list | `mail.view_mail_tracking_value_tree` | - |
| form | mail.tracking.value.form | `mail.view_mail_tracking_value_form` | - |



### discuss.channel.rtc.session

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| search | discuss.channel.rtc.session.search | `mail.discuss_channel_rtc_session_view_search` | - |
| list | discuss.channel.rtc.session.list | `mail.discuss_channel_rtc_session_view_tree` | - |
| form | discuss.channel.rtc.session.form | `mail.discuss_channel_rtc_session_view_form` | - |



#### Filtros de búsqueda (mail.discuss_channel_rtc_session_view_search)


**Agrupar por:**
- Channel


### mail.message.subtype

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | mail.message.subtype.list | `mail.view_message_subtype_tree` | - |
| form | mail.message.subtype.form | `mail.view_mail_message_subtype_form` | - |
| search | mail.message.subtype.view.search | `mail.mail_message_subtype_view_search` | - |



#### Filtros de búsqueda (mail.mail_message_subtype_view_search)

**Filtros:**
- **Default** (`[('default', '=', True)]`)


### discuss.channel.member

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | discuss.channel.member.list | `mail.discuss_channel_member_view_tree` | - |
| form | discuss.channel.member.form | `mail.discuss_channel_member_view_form` | - |



### mail.activity.plan

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| search | mail.activity.plan.view.search | `mail.mail_activity_plan_view_search` | - |
| list | mail.activity.plan.view.list | `mail.mail_activity_plan_view_tree` | - |
| form | mail.activity.plan.view.form | `mail.mail_activity_plan_view_form` | - |
| kanban | mail.activity.plan.view.kanban | `mail.mail_activity_plan_view_kanban` | - |



#### Filtros de búsqueda (mail.mail_activity_plan_view_search)

**Filtros:**
- **Archived** (`[('active', '=', False)]`)


**Agrupar por:**
- Model


### mail.template

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | email.template.form | `mail.email_template_form` | - |
| form | mail.template.view.form.confirm.delete | `mail.mail_template_view_form_confirm_delete` | - |
| list | email.template.list | `mail.email_template_tree` | - |
| search | email.template.search | `mail.view_email_template_search` | - |



#### Botones (mail.email_template_form)
- **Preview** (action)
- **Reset Template** (action) - Grupos: `mail.group_mail_template_editor`
- **Delete** (object)
- **Add Context Action** (object) - Grupos: `base.group_system`
- **Remove Context Action** (object) - Grupos: `base.group_no_one`


#### Botones (mail.mail_template_view_form_confirm_delete)
- **Delete** (object)
- **Cancel** (object)


#### Filtros de búsqueda (mail.view_email_template_search)

**Filtros:**
- **My Templates** (`[('user_id', '=', uid)]`)
- **Base Templates** (`[('template_category', '=', 'base_template')]`)
- **Custom Templates** (`[('template_category', '=', 'custom_template')]`)


**Agrupar por:**
- SMTP Server
- Model


### mail.notification

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | mail.notification.view.list | `mail.mail_notification_view_tree` | - |
| form | mail.notification.view.form | `mail.mail_notification_view_form` | - |



### mail.canned.response

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| search | mail.canned.response.view.search | `mail.mail_canned_response_view_search` | - |
| list | mail.canned.response.list | `mail.mail_canned_response_view_tree` | - |
| form | mail.canned.response.form | `mail.mail_canned_response_view_form` | - |



#### Filtros de búsqueda (mail.mail_canned_response_view_search)

**Filtros:**
- **My canned responses** (`[('create_uid', '=', uid)]`)
- **Shared canned responses** (`[('is_shared', '=', True)]`)


### mail.activity.plan.template

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | mail.activity.plan.template.view.list | `mail.mail_activity_plan_template_view_tree` | - |
| form | mail.activity.plan.template.view.form | `mail.mail_activity_plan_template_view_form` | - |



### res.users.settings

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | res.users.settings.list | `mail.res_users_settings_view_tree` | - |
| form | res.users.settings.form | `mail.res_users_settings_view_form` | - |



### discuss.channel

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| kanban | discuss.channel.kanban | `mail.discuss_channel_view_kanban` | - |
| form | discuss.channel.form | `mail.discuss_channel_view_form` | - |
| list | discuss.channel.list | `mail.discuss_channel_view_tree` | - |
| search | discuss.channel.search | `mail.discuss_channel_view_search` | - |



#### Filtros de búsqueda (mail.discuss_channel_view_search)

**Filtros:**
- **Archived** (`[('active', '=', False)]`)


### mail.mail

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | mail.mail.form | `mail.view_mail_form` | - |
| list | mail.mail.list | `mail.view_mail_tree` | - |
| search | mail.mail.search | `mail.view_mail_search` | - |



#### Botones (mail.view_mail_form)
- **Send Now** (object)
- **Retry** (object)
- **Cancel** (object)
- **action_open_document** (object)
- **Reply** (action)


#### Filtros de búsqueda (mail.view_mail_search)

**Filtros:**
- **Received** (`[('state','=','received')]`)
- **Outgoing** (`[('state','=','outgoing')]`)
- **Sent** (`[('state','=','sent')]`)
- **Failed** (`[('state','=','exception')]`)
- **Outgoing Email** (`[('message_type','=','email_outgoing')]`)
- **Incoming Email** (`[('message_type','=','email')]`)
- **Comment** (`[('message_type','=','comment')]`)
- **Notification** (`[('message_type','=','notification')]`)


**Agrupar por:**
- Status
- Author
- Thread
- Date


### mail.guest

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | mail.guest.list | `mail.mail_guest_view_tree` | - |
| form | mail.guest.form | `mail.mail_guest_view_form` | - |



### mail.message

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | mail.message.list | `mail.view_message_tree` | - |
| form | mail.message.view.form | `mail.mail_message_view_form` | - |
| search | mail.message.search | `mail.view_message_search` | - |



#### Botones (mail.mail_message_view_form)
- **action_open_document** (object)


#### Filtros de búsqueda (mail.view_message_search)

**Filtros:**
- **Has Mentions** (`[('partner_ids.user_ids', 'in', [uid])]`)
- **Need Action** (`[('needaction', '=', True)]`)


### ir.attachment

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| kanban | ir.attachment kanban | `mail.view_document_file_kanban` | - |



### res.partner

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| activity | res.partner.activity | `mail.res_partner_view_activity` | - |



### mail.message.reaction

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | mail.message.reaction.form | `mail.mail_message_reaction_view_form` | - |
| list | mail.message.reaction.list | `mail.mail_message_reaction_view_tree` | - |



### fetchmail.server

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | fetchmail.server.list | `mail.view_email_server_tree` | - |
| form | fetchmail.server.form | `mail.view_email_server_form` | - |
| search | fetchmail.server.search | `mail.view_email_server_search` | - |



#### Botones (mail.view_email_server_form)
- **Test & Confirm** (object)
- **Fetch Now** (object)
- **Reset Confirmation** (object)


#### Filtros de búsqueda (mail.view_email_server_search)

**Filtros:**
- **IMAP** (`[('server_type', '=', 'imap')]`)
- **POP** (`[('server_type', '=', 'pop')]`)
- **SSL** (`[('is_ssl', '=', True)]`)
- **Archived** (`[('active', '=', False)]`)


### mail.link.preview

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | mail.link.preview.form | `mail.mail_link_preview_view_form` | - |
| list | mail.link.preview.list | `mail.mail_link_preview_view_tree` | - |



### mail.alias.domain

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | mail.alias.domain.view.form | `mail.mail_alias_domain_view_form` | - |
| list | mail.alias.domain.view.list | `mail.mail_alias_domain_view_tree` | - |
| search | mail.alias.domain.view.search | `mail.mail_alias_domain_view_search` | - |



#### Filtros de búsqueda (mail.mail_alias_domain_view_search)


**Agrupar por:**
- Company


### mail.alias

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | mail.alias.view.form | `mail.mail_alias_view_form` | - |
| list | mail.alias.view.list | `mail.mail_alias_view_tree` | - |
| search | mail.alias.view.search | `mail.mail_alias_view_search` | - |



#### Botones (mail.mail_alias_view_form)
- **Open Document** (object)
- **open_parent_document** (object)


#### Filtros de búsqueda (mail.mail_alias_view_search)

**Filtros:**
- **Active** (`[('alias_name', '!=', False)]`)


**Agrupar por:**
- Creator
- Alias Domain
- Document Model
- Container Model


### mail.gateway.allowed

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | mail.gateway.allowed.view.list | `mail.mail_gateway_allowed_view_tree` | - |
| search | mail.gateway.allowed.view.search | `mail.mail_gateway_allowed_view_search` | - |



### mail.template.reset

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | mail.template.reset.view.form | `mail.mail_template_reset_view_form` | - |



#### Botones (mail.mail_template_reset_view_form)
- **Reset Template** (object)


### mail.wizard.invite

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | Add Followers | `mail.mail_wizard_invite_form` | - |



#### Botones (mail.mail_wizard_invite_form)
- **Add and close** (object)


### mail.activity.schedule

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | Activity schedule | `mail.mail_activity_schedule_view_form` | - |



#### Botones (mail.mail_activity_schedule_view_form)
- **Schedule** (object)
- **Schedule & Mark as Done** (object)
- **Done & Schedule Next** (object)
- **Done & Launch Next** (object)
- **Schedule** (object)


### mail.template.preview

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | mail.template.preview.view.form | `mail.mail_template_preview_view_form` | - |



### mail.resend.message

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | mail.resend.message.view.form | `mail.mail_resend_message_view_form` | - |



#### Botones (mail.mail_resend_message_view_form)
- **See Error Details** (object)
- **Send & close** (object)
- **Ignore all** (object)
- **Ignore all** (object)


### mail.compose.message

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | mail.compose.message.form | `mail.email_compose_message_wizard_form` | - |
| form | mail.compose.message.view.form.template.save | `mail.mail_compose_message_view_form_template_save` | - |



#### Botones (mail.email_compose_message_wizard_form)
- **Send** (object)
- **Log** (object)


#### Botones (mail.mail_compose_message_view_form_template_save)
- **Save** (object)
- **Cancel** (object)


### mail.blacklist.remove

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | mail.blacklist.remove.form | `mail.mail_blacklist_remove_view_form` | - |



#### Botones (mail.mail_blacklist_remove_view_form)
- **Remove address from blacklist** (object)


### mail.resend.partner

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | mail.resend.partner.view.form | `mail.mail_resend_partner_view_form` | - |



#### Botones (mail.mail_resend_partner_view_form)
- **Resend** (object)
- **action_open_record** (object)

