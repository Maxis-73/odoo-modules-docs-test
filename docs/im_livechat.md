# Módulo: Live Chat

## Información General
- **Nombre técnico:** im_livechat
- **Versión:** 1.0
- **Categoría:** Website/Live Chat
- **Dependencias:** mail, rating, digest, utm


## Propósito
Chat with your website visitors



## Descripción

Live Chat Support

Allow to drop instant messaging widgets on any web page that will communicate
with the current server and dispatch visitors request amongst several live
chat operators.
Help your customers with this chat, and analyse their feedback.

        



## Modelos

### chatbot.script


- Hereda de:


  - image.mixin

  - utm.source.mixin





- Campos:

  - **title** (Char) → Title


  - **active** (Boolean)


  - **image_1920** (Image)


  - **script_step_ids** (One2many) → chatbot.script.step


  - **operator_partner_id** (Many2one) → res.partner


  - **livechat_channel_count** (Integer)


  - **first_step_warning** (Selection)





### chatbot.message


- Hereda de: Base



- Campos:

  - **mail_message_id** (Many2one) → mail.message


  - **discuss_channel_id** (Many2one) → discuss.channel


  - **script_step_id** (Many2one) → chatbot.script.step


  - **user_script_answer_id** (Many2one) → chatbot.script.answer


  - **user_raw_answer** (Html)





### discuss.channel.member


- Hereda de:

  - discuss.channel.member




- No agrega campos



### im_livechat.channel


- Hereda de:


  - rating.parent.mixin





- Campos:

  - **name** (Char) → Channel Name


  - **button_text** (Char) → Text of the Button


  - **default_message** (Char) → Welcome Message


  - **input_placeholder** (Char) → Chat Input Placeholder


  - **header_background_color** (Char)


  - **title_color** (Char)


  - **button_background_color** (Char)


  - **button_text_color** (Char)


  - **web_page** (Char) → Web Page


  - **are_you_inside** (Boolean)


  - **available_operator_ids** (Many2many) → res.users


  - **script_external** (Html) → Script (external)


  - **nbr_channel** (Integer) → Number of conversation


  - **image_128** (Image) → Image


  - **user_ids** (Many2many) → res.users


  - **channel_ids** (One2many) → discuss.channel


  - **chatbot_script_count** (Integer)


  - **rule_ids** (One2many) → im_livechat.channel.rule





### im_livechat.channel.rule


- Hereda de: Base



- Campos:

  - **regex_url** (Char) → URL Regex


  - **action** (Selection)


  - **auto_popup_timer** (Integer) → Open automatically timer


  - **chatbot_script_id** (Many2one) → chatbot.script


  - **chatbot_only_if_no_operator** (Boolean)


  - **channel_id** (Many2one) → im_livechat.channel


  - **country_ids** (Many2many) → res.country


  - **sequence** (Integer) → Matching order





### digest.digest


- Hereda de:

  - digest.digest




- Campos:

  - **kpi_livechat_rating** (Boolean) → % of Happiness


  - **kpi_livechat_rating_value** (Float)


  - **kpi_livechat_conversations** (Boolean) → Conversations handled


  - **kpi_livechat_conversations_value** (Integer)


  - **kpi_livechat_response** (Boolean) → Time to answer (sec)


  - **kpi_livechat_response_value** (Float)





### mail.message


- Hereda de:

  - mail.message




- Campos:

  - **parent_author_name** (Char)


  - **parent_body** (Html)





### chatbot.script.answer


- Hereda de: Base



- Campos:

  - **name** (Char)


  - **sequence** (Integer)


  - **redirect_link** (Char) → Redirect Link


  - **script_step_id** (Many2one) → chatbot.script.step


  - **chatbot_script_id** (Many2one)





### discuss.channel


- Hereda de:


  - rating.mixin

  - discuss.channel





- Campos:

  - **anonymous_name** (Char) → Anonymous Name


  - **channel_type** (Selection)


  - **duration** (Float) → Duration


  - **livechat_active** (Boolean) → Is livechat ongoing?


  - **livechat_channel_id** (Many2one) → im_livechat.channel


  - **livechat_operator_id** (Many2one) → res.partner


  - **chatbot_current_step_id** (Many2one) → chatbot.script.step


  - **chatbot_message_ids** (One2many) → chatbot.message


  - **country_id** (Many2one) → res.country





### res.users


- Hereda de:

  - res.users




- Campos:

  - **livechat_username** (Char)


  - **livechat_lang_ids** (Many2many) → res.lang


  - **has_access_livechat** (Boolean)





### rating.rating


- Hereda de:

  - rating.rating




- No agrega campos



### chatbot.script.step


- Hereda de: Base



- Campos:

  - **message** (Text)


  - **sequence** (Integer)


  - **chatbot_script_id** (Many2one) → chatbot.script


  - **step_type** (Selection)


  - **answer_ids** (One2many) → chatbot.script.answer


  - **triggering_answer_ids** (Many2many) → chatbot.script.answer


  - **is_forward_operator_child** (Boolean)





### res.partner


- Hereda de:

  - res.partner




- Campos:

  - **user_livechat_username** (Char)





### res.users.settings


- Hereda de:

  - res.users.settings




- Campos:

  - **livechat_username** (Char) → Livechat Username


  - **livechat_lang_ids** (Many2many) → res.lang








## Vistas


### im_livechat.channel

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| kanban | im_livechat.channel.kanban | `im_livechat.im_livechat_channel_view_kanban` | - |
| form | im_livechat.channel.form | `im_livechat.im_livechat_channel_view_form` | - |
| search | im.livechat.channel.view.search | `im_livechat.im_livechat_channel_view_search` | - |



#### Botones (im_livechat.im_livechat_channel_view_form)
- **Join Channel** (object)
- **Leave Channel** (object)
- **action_view_chatbot_scripts** (object)
- **%(discuss_channel_action_from_livechat_channel)d** (action)
- **action_view_rating** (object)


### im_livechat.channel.rule

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | im.livechat.channel.rule.list | `im_livechat.im_livechat_channel_rule_view_tree` | - |
| kanban | im_livechat.channel.rule.kanban | `im_livechat.im_livechat_channel_rule_view_kanban` | - |
| form | im_livechat.channel.rule.form | `im_livechat.im_livechat_channel_rule_view_form` | - |



### discuss.channel

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| search | discuss.channel.search | `im_livechat.discuss_channel_view_search` | - |
| list | discuss.channel.list | `im_livechat.discuss_channel_view_tree` | - |
| kanban | discuss.channel.kanban | `im_livechat.discuss_channel_view_kanban` | - |
| form | discuss.channel.form | `im_livechat.discuss_channel_view_form` | - |



#### Filtros de búsqueda (im_livechat.discuss_channel_view_search)

**Filtros:**
- **My Sessions** (`[('is_member', '=', True)]`)
- **Session Date**
- **Bad Ratings** (`[('rating_ids', '!=', False), ('rating_avg', '<', 2.5)]`)
- **Good Ratings** (`[('rating_ids', '!=', False), ('rating_avg', '>=', 2.5)]`)
- **Unrated** (`[('rating_ids', '=', False)]`)


**Agrupar por:**
- Channel
- Session Date


### chatbot.script.step

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | chatbot.script.step.view.form | `im_livechat.chatbot_script_step_view_form` | - |
| list | chatbot.script.step.view.list | `im_livechat.chatbot_script_step_view_tree` | - |



### chatbot.script.answer

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | chatbot.script.answer.view.form | `im_livechat.chatbot_script_answer_view_form` | - |
| list | chatbot.script.answer.view.list | `im_livechat.chatbot_script_answer_view_tree` | - |



### chatbot.script

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | chatbot.script.view.form | `im_livechat.chatbot_script_view_form` | - |
| list | chatbot.script.view.list | `im_livechat.chatbot_script_view_tree` | - |
| search | chatbot.script.view.search | `im_livechat.chatbot_script_view_search` | - |



#### Botones (im_livechat.chatbot_script_view_form)
- **action_view_livechat_channels** (object)


#### Filtros de búsqueda (im_livechat.chatbot_script_view_search)

**Filtros:**
- **Archived** (`[('active', '=', False)]`)


### im_livechat.report.channel

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| pivot | im_livechat.report.channel.pivot | `im_livechat.im_livechat_report_channel_view_pivot` | - |
| graph | im_livechat.report.channel.graph | `im_livechat.im_livechat_report_channel_view_graph` | - |
| search | im_livechat.report.channel.search | `im_livechat.im_livechat_report_channel_view_search` | - |



#### Filtros de búsqueda (im_livechat.im_livechat_report_channel_view_search)

**Filtros:**
- **Missed sessions** (`[('nbr_speaker','<=', 1)]`)
- **Treated sessions** (`[('nbr_speaker','>', 1)]`)
- **Last 24h** (`[('start_date','>', (context_today() - datetime.timedelta(days=1)).strftime('%Y-%m-%d') )]`)
- **This Week** (`[                         ('start_date', '>=', (datetime.datetime.combine(context_today() + relativedelta(weeks=-1,days=1,weekday=0), datetime.time(0,0,0)).to_utc()).strftime('%Y-%m-%d %H:%M:%S')),                         ('start_date', '<', (datetime.datetime.combine(context_today() + relativedelta(days=1,weekday=0), datetime.time(0,0,0)).to_utc()).strftime('%Y-%m-%d %H:%M:%S'))]`)
- **filter_start_date**


**Agrupar por:**
- Code
- Channel
- Operator
- Creation date (hour)
- Creation date


### im_livechat.report.operator

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| pivot | im_livechat.report.operator.pivot | `im_livechat.im_livechat_report_operator_view_pivot` | - |
| graph | im_livechat.report.operator.graph | `im_livechat.im_livechat_report_operator_view_graph` | - |
| search | im_livechat.report.operator.search | `im_livechat.im_livechat_report_operator_view_search` | - |



#### Filtros de búsqueda (im_livechat.im_livechat_report_operator_view_search)

**Filtros:**
- **Last 24h** (`[('start_date','>', (context_today() - datetime.timedelta(days=1)).strftime('%Y-%m-%d') )]`)
- **This Week** (`[                         ('start_date', '>=', (datetime.datetime.combine(context_today() + relativedelta(weeks=-1,days=1,weekday=0), datetime.time(0,0,0)).to_utc()).strftime('%Y-%m-%d %H:%M:%S')),                         ('start_date', '<', (datetime.datetime.combine(context_today() + relativedelta(days=1,weekday=0), datetime.time(0,0,0)).to_utc()).strftime('%Y-%m-%d %H:%M:%S'))]`)
- **This Month** (`[                         ('start_date', '>=', (datetime.datetime.combine(context_today() + relativedelta(months=-1,days=1,weekday=0), datetime.time(0,0,0)).to_utc()).strftime('%Y-%m-%d %H:%M:%S')),                         ('start_date', '<', (datetime.datetime.combine(context_today() + relativedelta(days=1,weekday=0), datetime.time(0,0,0)).to_utc()).strftime('%Y-%m-%d %H:%M:%S'))]`)
- **filter_start_date**


**Agrupar por:**
- Channel
- Operator
- Creation date

