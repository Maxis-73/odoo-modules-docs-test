# Módulo: Email Marketing

## Información General
- **Nombre técnico:** mass_mailing
- **Versión:** 2.7
- **Categoría:** Marketing/Email Marketing
- **Dependencias:** contacts, mail, utm, link_tracker, web_editor, social_media, web_tour, digest


## Propósito
Design, send and track emails





## Modelos

### mailing.mailing


- Hereda de:


  - mail.thread

  - mail.activity.mixin

  - mail.render.mixin

  - utm.source.mixin





#### Campos
- **active** (Boolean)
- **subject** (Char) → Subject
- **preview** (Char) → Preview
- **email_from** (Char)
- **favorite** (Boolean) → Favorite
- **favorite_date** (Datetime) → Favorite Date
- **sent_date** (Datetime)
- **schedule_type** (Selection)
- **schedule_date** (Datetime)
- **calendar_date** (Datetime) → Calendar Date
- **body_arch** (Html)
- **body_html** (Html)
- **is_body_empty** (Boolean)
- **attachment_ids** (Many2many) → ir.attachment
- **keep_archives** (Boolean)
- **campaign_id** (Many2one) → utm.campaign
- **medium_id** (Many2one) → utm.medium
- **state** (Selection)
- **color** (Integer)
- **user_id** (Many2one) → res.users
- **mailing_type** (Selection)
- **mailing_type_description** (Char) → Mailing Type Description
- **reply_to_mode** (Selection)
- **reply_to** (Char)
- **mailing_model_real** (Char)
- **mailing_model_id** (Many2one) → ir.model
- **mailing_model_name** (Char)
- **mailing_on_mailing_list** (Boolean)
- **mailing_domain** (Char)
- **mail_server_available** (Boolean)
- **mail_server_id** (Many2one) → ir.mail_server
- **contact_list_ids** (Many2many) → mailing.list
- **mailing_filter_id** (Many2one) → mailing.filter
- **mailing_filter_domain** (Char) → Favorite filter domain
- **mailing_filter_count** (Integer) → # Favorite Filters
- **ab_testing_completed** (Boolean)
- **ab_testing_description** (Html) → A/B Testing Description
- **ab_testing_enabled** (Boolean)
- **ab_testing_is_winner_mailing** (Boolean) → Is the Winner of its Campaign
- **ab_testing_mailings_count** (Integer)
- **ab_testing_pc** (Integer)
- **ab_testing_schedule_datetime** (Datetime)
- **ab_testing_winner_selection** (Selection)
- **is_ab_test_sent** (Boolean)
- **kpi_mail_required** (Boolean) → KPI mail required
- **mailing_trace_ids** (One2many) → mailing.trace
- **total** (Integer)
- **scheduled** (Integer)
- **expected** (Integer)
- **canceled** (Integer)
- **sent** (Integer)
- **process** (Integer)
- **pending** (Integer)
- **delivered** (Integer)
- **opened** (Integer)
- **clicked** (Integer)
- **replied** (Integer)
- **bounced** (Integer)
- **failed** (Integer)
- **received_ratio** (Float)
- **opened_ratio** (Float)
- **replied_ratio** (Float)
- **bounced_ratio** (Float)
- **clicks_ratio** (Float)
- **link_trackers_count** (Integer)
- **next_departure** (Datetime)
- **next_departure_is_past** (Boolean)
- **warning_message** (Char) → Warning Message





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| search | mailing.mailing.search | `mass_mailing.view_mail_mass_mailing_search` | - |
| list | mailing.mailing.list | `mass_mailing.view_mail_mass_mailing_tree` | - |
| form | mailing.mailing.form | `mass_mailing.view_mail_mass_mailing_form` | - |
| kanban | mailing.mailing.kanban | `mass_mailing.view_mail_mass_mailing_kanban` | - |
| calendar | mailing.mailing.view.calendar | `mass_mailing.mailing_mailing_view_calendar` | - |



**Filtros de búsqueda (mass_mailing.view_mail_mass_mailing_search):**

- **My Mailings** (`[('user_id', '=', uid)]`)
- **filter_sent_date**
- **A/B Tests** (`[('ab_testing_enabled', '=', True)]`)
- **A/B Tests to review** (`[('ab_testing_enabled', '=', True), ('ab_testing_winner_selection', '=', 'manual'), ('ab_testing_completed', '=', False)]`)
- **Archived** (`[('active', '=', False)]`)


*Agrupar por:*
- Status
- Sent By
- Mailing List
- Sent Period


**Botones (mass_mailing.view_mail_mass_mailing_form):**
- **Send** (object)
- **Schedule** (object)
- **Duplicate** (object)
- **Test** (object)
- **Cancel** (object)
- **Retry** (object)
- **Add to Templates** (object)
- **Remove from Templates** (object)
- **action_view_traces_canceled** (object)
- **action_view_traces_scheduled** (object)
- **action_view_traces_process** (object)
- **action_view_traces_sent** (object)
- **action_view_traces_failed** (object)
- **action_reload** (object)
- **action_reload** (object)
- **action_view_opened** (object)
- **action_view_replied** (object)
- **action_view_clicked** (object)
- **action_view_delivered** (object)
- **action_view_bounced** (object)
- **action_view_link_trackers** (object)
- **action_view_mailing_contacts** (object)
- **action_compare_versions** (object)
- **action_duplicate** (object)
- **action_send_winner_mailing** (object)
- **action_select_as_winner** (object)
- **action_duplicate** (object)



### ir.mail_server


- Hereda de:


  - ir.mail_server





#### Campos
- **active_mailing_ids** (One2many) → mailing.mailing





### mailing.contact


- Hereda de:


  - mail.thread.blacklist





#### Campos
- **name** (Char) → Name
- **first_name** (Char) → First Name
- **last_name** (Char) → Last Name
- **company_name** (Char)
- **title_id** (Many2one) → res.partner.title
- **email** (Char) → Email
- **list_ids** (Many2many) → mailing.list
- **subscription_ids** (One2many) → mailing.subscription
- **country_id** (Many2one) → res.country
- **tag_ids** (Many2many) → res.partner.category
- **opt_out** (Boolean) → Opt Out





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| search | mailing.contact.view.search | `mass_mailing.mailing_contact_view_search` | - |
| list | mailing.contact.view.list | `mass_mailing.mailing_contact_view_tree` | - |
| kanban | mailing.contact.view.kanban | `mass_mailing.mailing_contact_view_kanban` | - |
| form | mailing.contact.view.form | `mass_mailing.mailing_contact_view_form` | - |
| pivot | mailing.contact.pivot | `mass_mailing.mailing_contact_view_pivot` | - |
| graph | mailing.contact.view.graph | `mass_mailing.mailing_contact_view_graph` | - |



**Filtros de búsqueda (mass_mailing.mailing_contact_view_search):**

- **Valid Email Recipients** (`[('opt_out', '=', False), ('is_blacklisted', '=', False), ('email_normalized', '!=', False)]`)
- **Bounced** (`[('message_bounce', '>', 0)]`)
- **Blacklisted** (`[('is_blacklisted','=',True)]`)
- **Opted-out** (`[('opt_out', '=', True)]`)
- **Exclude Blacklisted Emails** (`[('is_blacklisted', '=', False)]`)
- **Exclude Opt Out** (`[('opt_out', '=', False)]`)


*Agrupar por:*
- Creation Date


**Botones (mass_mailing.mailing_contact_view_form):**
- **mail_action_blacklist_remove** (object) - Grupos: `base.group_user`



### ['mail.mail']


- Hereda de:


  - mail.mail





#### Campos
- **mailing_id** (Many2one) → mailing.mailing
- **mailing_trace_ids** (One2many) → mailing.trace





### ['mail.blacklist']


- Hereda de:


  - mail.blacklist





#### Campos
- **opt_out_reason_id** (Many2one) → mailing.subscription.optout





### mail.thread


- Hereda de:

  - mail.thread




- No agrega campos




### utm.campaign


- Hereda de:

  - utm.campaign




#### Campos
- **mailing_mail_ids** (One2many) → mailing.mailing
- **mailing_mail_count** (Integer) → Number of Mass Mailing
- **is_mailing_campaign_activated** (Boolean)
- **ab_testing_mailings_count** (Integer) → A/B Test Mailings #
- **ab_testing_completed** (Boolean) → A/B Testing Campaign Finished
- **ab_testing_winner_mailing_id** (Many2one) → mailing.mailing
- **ab_testing_schedule_datetime** (Datetime) → Send Final On
- **ab_testing_winner_selection** (Selection)
- **received_ratio** (Float)
- **opened_ratio** (Float)
- **replied_ratio** (Float)
- **bounced_ratio** (Float)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | utm.campaign.view.form | `mass_mailing.utm_campaign_view_form` | utm.utm_campaign_view_form |




### mail.render.mixin


- Hereda de:

  - mail.render.mixin




- No agrega campos




### utm.medium


- Hereda de:

  - utm.medium




- No agrega campos




### ir.model


- Hereda de:

  - ir.model




#### Campos
- **is_mailing_enabled** (Boolean)





### mailing.list


- Hereda de: Base



#### Campos
- **name** (Char)
- **active** (Boolean)
- **contact_count** (Integer)
- **contact_count_email** (Integer)
- **contact_count_opt_out** (Integer)
- **contact_pct_opt_out** (Float)
- **contact_count_blacklisted** (Integer)
- **contact_pct_blacklisted** (Float)
- **contact_pct_bounce** (Float)
- **contact_ids** (Many2many) → mailing.contact
- **mailing_count** (Integer)
- **mailing_ids** (Many2many) → mailing.mailing
- **subscription_ids** (One2many) → mailing.subscription
- **is_public** (Boolean)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| search | mailing.list.view.search | `mass_mailing.mailing_list_view_search` | - |
| list | mailing.list.view.list | `mass_mailing.mailing_list_view_tree` | - |
| form | mailing.list.form | `mass_mailing.mailing_list_view_form` | - |
| form | mailing.list.form.simplified | `mass_mailing.mailing_list_view_form_simplified` | - |
| kanban | mailing.list.view.kanban | `mass_mailing.mailing_list_view_kanban` | - |



**Filtros de búsqueda (mass_mailing.mailing_list_view_search):**

- **Archived** (`[('active','=',False)]`)


*Agrupar por:*
- Creation Period


**Botones (mass_mailing.mailing_list_view_form):**
- **Send Mailing** (object)
- **Import Contacts** (object)
- **action_view_contacts** (object)
- **action_view_mailings** (object)
- **action_view_contacts_bouncing** (object)
- **action_view_contacts_opt_out** (object)
- **action_view_contacts_blacklisted** (object)



### utm.source


- Hereda de:

  - utm.source




- No agrega campos




### mailing.trace


- Hereda de: Base



#### Campos
- **trace_type** (Selection)
- **mail_mail_id** (Many2one) → mail.mail
- **mail_mail_id_int** (Integer)
- **email** (Char)
- **message_id** (Char)
- **medium_id** (Many2one)
- **source_id** (Many2one)
- **model** (Char)
- **res_id** (Many2oneReference)
- **mass_mailing_id** (Many2one) → mailing.mailing
- **campaign_id** (Many2one)
- **sent_datetime** (Datetime) → Sent On
- **open_datetime** (Datetime) → Opened On
- **reply_datetime** (Datetime) → Replied On
- **trace_status** (Selection)
- **failure_type** (Selection)
- **failure_reason** (Text) → Failure reason
- **links_click_ids** (One2many) → link.tracker.click
- **links_click_datetime** (Datetime) → Clicked On





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| search | mailing.trace.view.search | `mass_mailing.mailing_trace_view_search` | - |
| list | mailing.trace.view.list | `mass_mailing.mailing_trace_view_tree` | - |
| list | mailing.trace.view.list.mail | `mass_mailing.mailing_trace_view_tree_mail` | - |
| form | mailing.trace.view.form | `mass_mailing.mailing_trace_view_form` | - |
| graph | Mail Statistics Graph | `mass_mailing.view_mail_mail_statistics_graph` | - |



**Filtros de búsqueda (mass_mailing.mailing_trace_view_search):**

- **Scheduled** (`[('trace_status', '=', 'outgoing')]`)
- **Cancelled** (`[('trace_status', '=', 'cancel')]`)
- **Processing** (`[('trace_status', '=', 'process')]`)
- **Sent** (`[('sent_datetime', '!=', False)]`)
- **Clicked** (`[('links_click_datetime', '!=', False)]`)
- **Delivered** (`[('sent_datetime', '!=', False), ('trace_status', 'not in', ['error', 'cancel', 'process', 'pending'])]`)
- **Opened** (`[('trace_status', 'in', ['open', 'reply'])]`)
- **Replied** (`[('trace_status', '=', 'reply')]`)
- **Bounced** (`[('trace_status', '=', 'bounce')]`)
- **Failed** (`[('trace_status', '=', 'error')]`)


*Agrupar por:*
- State
- Open Date
- Reply Date
- Last State Update
- Mass Mailing


**Botones (mass_mailing.mailing_trace_view_form):**
- **action_view_contact** (object)



### mailing.subscription


- Hereda de: Base



#### Campos
- **contact_id** (Many2one) → mailing.contact
- **list_id** (Many2one) → mailing.list
- **opt_out** (Boolean)
- **opt_out_reason_id** (Many2one) → mailing.subscription.optout
- **opt_out_datetime** (Datetime)
- **message_bounce** (Integer)
- **is_blacklisted** (Boolean)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | mailing.subscription.view.form | `mass_mailing.mailing_subscription_view_form` | - |
| graph | mailing.subscription.view.graph | `mass_mailing.mailing_subscription_view_graph` | - |
| pivot | mailing.subscription.view.pivot | `mass_mailing.mailing_subscription_view_pivot` | - |
| list | mailing.subscription.view.list | `mass_mailing.mailing_subscription_view_tree` | - |
| search | mailing.subscription.view.search | `mass_mailing.mailing_subscription_view_search` | - |



**Filtros de búsqueda (mass_mailing.mailing_subscription_view_search):**

- **Subscription Date**
- **Unsubscription Date**


*Agrupar por:*
- Unsubscription Date
- Mailing List
- Reason



### res.users


- Hereda de:


  - res.users





- No agrega campos




### res.config.settings


- Hereda de:

  - res.config.settings




#### Campos
- **group_mass_mailing_campaign** (Boolean)
- **mass_mailing_outgoing_mail_server** (Boolean)
- **mass_mailing_mail_server_id** (Many2one) → ir.mail_server
- **show_blacklist_buttons** (Boolean)
- **mass_mailing_reports** (Boolean)
- **mass_mailing_split_contact_name** (Boolean)





### res.company


- Hereda de:

  - res.company




- No agrega campos




### ir.http


- Hereda de:

  - ir.http




- No agrega campos




### mailing.subscription.optout


- Hereda de: Base



#### Campos
- **name** (Char)
- **sequence** (Integer)
- **is_feedback** (Boolean)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | mailing.subscription.optout.view.form | `mass_mailing.mailing_subscription_optout_view_form` | - |
| list | mailing.subscription.optout.view.list | `mass_mailing.mailing_subscription_optout_view_tree` | - |
| search | mailing.subscription.optout.view.search | `mass_mailing.mailing_subscription_optout_view_search` | - |




### link.tracker


- Hereda de:

  - link.tracker




#### Campos
- **mass_mailing_id** (Many2one) → mailing.mailing





### link.tracker.click


- Hereda de:

  - link.tracker.click




#### Campos
- **mailing_trace_id** (Many2one) → mailing.trace
- **mass_mailing_id** (Many2one) → mailing.mailing





### res.partner


- Hereda de:

  - res.partner




- No agrega campos




### mailing.filter


- Hereda de: Base



#### Campos
- **create_uid** (Many2one) → res.users
- **name** (Char)
- **mailing_domain** (Char)
- **mailing_model_id** (Many2one) → ir.model
- **mailing_model_name** (Char)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| search | mailing.filter.view.search | `mass_mailing.mailing_filter_view_search` | - |
| list | mailing.filter.view.list | `mass_mailing.mailing_filter_view_tree` | - |
| form | mailing.filter.view.form | `mass_mailing.mailing_filter_view_form` | - |



**Filtros de búsqueda (mass_mailing.mailing_filter_view_search):**

- **My Filters** (`[('create_uid', '=', uid)]`)


*Agrupar por:*
- Recipients








## Vistas Adicionales


### mailing.contact.import

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | mailing.contact.import.view.form | `mass_mailing.mailing_contact_import_view_form` | - |



**Botones (mass_mailing.mailing_contact_import_view_form):**
- **action_open_base_import** (object)
- **Import** (object)


### mailing.list.merge

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | mailing.list.merge.form | `mass_mailing.mailing_list_merge_view_form` | - |



**Botones (mass_mailing.mailing_list_merge_view_form):**
- **Merge** (object)


### mailing.mailing.test

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | mailing.mailing.test.form | `mass_mailing.view_mail_mass_mailing_test_form` | - |



**Botones (mass_mailing.view_mail_mass_mailing_test_form):**
- **Send test** (object)


### mailing.contact.to.list

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | mailing.contact.to.list.view.form | `mass_mailing.mailing_contact_to_list_view_form` | - |



**Botones (mass_mailing.mailing_contact_to_list_view_form):**
- **Add** (object)
- **Add and Send Mailing** (object)


### mailing.mailing.schedule.date

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | mailing.mailing.schedule.date.view.form | `mass_mailing.mailing_mailing_schedule_date_view_form` | - |



**Botones (mass_mailing.mailing_mailing_schedule_date_view_form):**
- **Schedule** (object)


### mailing.trace.report

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | mailing.trace.report.view.list | `mass_mailing.mailing_trace_report_view_tree` | - |
| pivot | mailing.trace.report.view.pivot | `mass_mailing.mailing_trace_report_view_pivot` | - |
| graph | mailing.trace.report.view.graph | `mass_mailing.mailing_trace_report_view_graph` | - |
| search | mailing.trace.report.view.search | `mass_mailing.mailing_trace_report_view_search` | - |



**Filtros de búsqueda (mass_mailing.mailing_trace_report_view_search):**

- **filter_scheduled_date**


*Agrupar por:*
- Mass Mailing Campaign
- State
- Sent By
- Scheduled Period



