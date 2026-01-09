# Módulo: Events Organization

## Información General
- **Nombre técnico:** event
- **Versión:** 1.9
- **Categoría:** Marketing/Events
- **Dependencias:** barcodes, base_setup, mail, phone_validation, portal, utm


## Propósito
Trainings, Conferences, Meetings, Exhibitions, Registrations



## Descripción

Organization and management of Events.

The event module allows you to efficiently organize events and all related tasks: planning, registration tracking,
attendances, etc.

Key Features
------------
* Manage your Events and Registrations
* Use emails to automatically confirm and send acknowledgments for any event registration




## Modelos

### event.tag.category


- Hereda de: Base



- Campos:

  - **name** (Char) → Name


  - **sequence** (Integer) → Sequence


  - **tag_ids** (One2many) → event.tag





### event.tag


- Hereda de: Base



- Campos:

  - **name** (Char) → Name


  - **sequence** (Integer) → Sequence


  - **category_id** (Many2one) → event.tag.category


  - **category_sequence** (Integer)


  - **color** (Integer)





### event.question.answer


- Hereda de: Base



- Campos:

  - **name** (Char) → Answer


  - **question_id** (Many2one) → event.question


  - **sequence** (Integer)





### event.type.ticket


- Hereda de: Base



- Campos:

  - **sequence** (Integer) → Sequence


  - **name** (Char)


  - **description** (Text) → Description


  - **event_type_id** (Many2one) → event.type


  - **seats_limited** (Boolean)


  - **seats_max** (Integer)





### event.event.ticket


- Hereda de:

  - event.type.ticket




- Campos:

  - **event_type_id** (Many2one)


  - **event_id** (Many2one) → event.event


  - **company_id** (Many2one) → res.company


  - **start_sale_datetime** (Datetime)


  - **end_sale_datetime** (Datetime)


  - **is_launched** (Boolean)


  - **is_expired** (Boolean)


  - **sale_available** (Boolean)


  - **registration_ids** (One2many) → event.registration


  - **seats_reserved** (Integer)


  - **seats_available** (Integer)


  - **seats_used** (Integer)


  - **seats_taken** (Integer)


  - **is_sold_out** (Boolean) → Sold Out


  - **color** (Char) → Color





### event.mail.registration


- Hereda de: Base



- Campos:

  - **scheduler_id** (Many2one) → event.mail


  - **registration_id** (Many2one) → event.registration


  - **scheduled_date** (Datetime) → Scheduled Time


  - **mail_sent** (Boolean) → Mail Sent





### event.registration.answer


- Hereda de: Base



- Campos:

  - **question_id** (Many2one) → event.question


  - **registration_id** (Many2one) → event.registration


  - **partner_id** (Many2one) → res.partner


  - **event_id** (Many2one) → event.event


  - **question_type** (Selection)


  - **value_answer_id** (Many2one) → event.question.answer


  - **value_text_box** (Text) → Text answer





### event.type


- Hereda de: Base



- Campos:

  - **name** (Char) → Event Template


  - **note** (Html)


  - **sequence** (Integer)


  - **event_type_ticket_ids** (One2many) → event.type.ticket


  - **tag_ids** (Many2many) → event.tag


  - **has_seats_limitation** (Boolean) → Limited Seats


  - **seats_max** (Integer) → Maximum Registrations


  - **default_timezone** (Selection)


  - **event_type_mail_ids** (One2many) → event.type.mail


  - **ticket_instructions** (Html) → Ticket Instructions


  - **question_ids** (One2many) → event.question





### event.event


- Hereda de:


  - mail.thread

  - mail.activity.mixin





- Campos:

  - **name** (Char)


  - **note** (Html)


  - **description** (Html)


  - **active** (Boolean)


  - **user_id** (Many2one) → res.users


  - **use_barcode** (Boolean)


  - **company_id** (Many2one) → res.company


  - **organizer_id** (Many2one) → res.partner


  - **event_type_id** (Many2one) → event.type


  - **event_mail_ids** (One2many) → event.mail


  - **tag_ids** (Many2many) → event.tag


  - **registration_properties_definition** (PropertiesDefinition) → Registration Properties


  - **kanban_state** (Selection)


  - **kanban_state_label** (Char)


  - **stage_id** (Many2one) → event.stage


  - **legend_blocked** (Char)


  - **legend_done** (Char)


  - **legend_normal** (Char)


  - **seats_max** (Integer)


  - **seats_limited** (Boolean) → Limit Attendees


  - **seats_reserved** (Integer)


  - **seats_available** (Integer)


  - **seats_used** (Integer)


  - **seats_taken** (Integer)


  - **registration_ids** (One2many) → event.registration


  - **event_ticket_ids** (One2many) → event.event.ticket


  - **event_registrations_started** (Boolean) → Registrations started


  - **event_registrations_open** (Boolean) → Registration open


  - **event_registrations_sold_out** (Boolean) → Sold Out


  - **start_sale_datetime** (Datetime) → Start sale date


  - **date_tz** (Selection)


  - **date_begin** (Datetime)


  - **date_end** (Datetime)


  - **date_begin_located** (Char)


  - **date_end_located** (Char)


  - **is_ongoing** (Boolean) → Is Ongoing


  - **is_one_day** (Boolean)


  - **is_finished** (Boolean)


  - **address_id** (Many2one) → res.partner


  - **address_search** (Many2one) → res.partner


  - **address_inline** (Char)


  - **country_id** (Many2one) → res.country


  - **lang** (Selection)


  - **badge_format** (Selection)


  - **badge_image** (Image) → Badge Background


  - **ticket_instructions** (Html) → Ticket Instructions


  - **question_ids** (One2many) → event.question


  - **general_question_ids** (One2many) → event.question


  - **specific_question_ids** (One2many) → event.question





### res.config.settings


- Hereda de:

  - res.config.settings




- Campos:

  - **google_maps_static_api_key** (Char) → Google Maps API key


  - **google_maps_static_api_secret** (Char) → Google Maps API secret


  - **module_event_sale** (Boolean) → Tickets with Sale


  - **module_pos_event** (Boolean) → Tickets with PoS


  - **module_website_event_meet** (Boolean) → Discussion Rooms


  - **module_website_event_track** (Boolean) → Tracks and Agenda


  - **module_website_event_track_live** (Boolean) → Live Mode


  - **module_website_event_track_quiz** (Boolean) → Quiz on Tracks


  - **module_website_event_exhibitor** (Boolean) → Advanced Sponsors


  - **use_event_barcode** (Boolean)


  - **barcode_nomenclature_id** (Many2one) → barcode.nomenclature


  - **module_website_event_sale** (Boolean) → Online Ticketing


  - **module_event_booth** (Boolean) → Booth Management


  - **use_google_maps_static_api** (Boolean) → Google Maps static API





### mail.template


- Hereda de:

  - mail.template




- No agrega campos



### event.type.mail


- Hereda de: Base



- Campos:

  - **event_type_id** (Many2one) → event.type


  - **interval_nbr** (Integer) → Interval


  - **interval_unit** (Selection)


  - **interval_type** (Selection)


  - **notification_type** (Selection)


  - **template_ref** (Reference)





### event.mail


- Hereda de: Base



- Campos:

  - **event_id** (Many2one) → event.event


  - **sequence** (Integer) → Display order


  - **interval_nbr** (Integer) → Interval


  - **interval_unit** (Selection)


  - **interval_type** (Selection)


  - **scheduled_date** (Datetime) → Schedule Date


  - **last_registration_id** (Many2one) → event.registration


  - **mail_registration_ids** (One2many) → event.mail.registration


  - **mail_done** (Boolean) → Sent


  - **mail_state** (Selection)


  - **mail_count_done** (Integer) → # Sent


  - **notification_type** (Selection)


  - **template_ref** (Reference)





### event.registration


- Hereda de:


  - mail.thread

  - mail.activity.mixin





- Campos:

  - **event_id** (Many2one) → event.event


  - **event_ticket_id** (Many2one) → event.event.ticket


  - **active** (Boolean)


  - **barcode** (Char)


  - **utm_campaign_id** (Many2one) → utm.campaign


  - **utm_source_id** (Many2one) → utm.source


  - **utm_medium_id** (Many2one) → utm.medium


  - **partner_id** (Many2one) → res.partner


  - **name** (Char)


  - **email** (Char)


  - **phone** (Char)


  - **company_name** (Char)


  - **date_closed** (Datetime)


  - **event_begin_date** (Datetime)


  - **event_end_date** (Datetime)


  - **event_date_range** (Char) → Date Range


  - **event_organizer_id** (Many2one)


  - **event_user_id** (Many2one)


  - **company_id** (Many2one) → res.company


  - **state** (Selection)


  - **registration_answer_ids** (One2many) → event.registration.answer


  - **registration_answer_choice_ids** (One2many) → event.registration.answer


  - **mail_registration_ids** (One2many) → event.mail.registration


  - **registration_properties** (Properties) → Properties





### event.stage


- Hereda de: Base



- Campos:

  - **name** (Char)


  - **description** (Text)


  - **sequence** (Integer) → Sequence


  - **fold** (Boolean)


  - **pipe_end** (Boolean)


  - **legend_blocked** (Char) → Red Kanban Label


  - **legend_done** (Char) → Green Kanban Label


  - **legend_normal** (Char) → Grey Kanban Label





### res.partner


- Hereda de:

  - res.partner




- Campos:

  - **event_count** (Integer) → # Events


  - **static_map_url** (Char)


  - **static_map_url_is_valid** (Boolean)





### event.question


- Hereda de: Base



- Campos:

  - **title** (Char)


  - **question_type** (Selection)


  - **event_type_id** (Many2one) → event.type


  - **event_id** (Many2one) → event.event


  - **answer_ids** (One2many) → event.question.answer


  - **sequence** (Integer)


  - **once_per_order** (Boolean) → Ask once per order


  - **is_mandatory_answer** (Boolean) → Mandatory Answer








## Vistas


### event.event

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | event.event.form | `event.view_event_form` | - |
| list | event.event.list | `event.view_event_tree` | - |
| activity | event.event.view.activity | `event.event_event_view_activity` | - |
| form | event.event.form.quick_create | `event.event_event_view_form_quick_create` | - |
| kanban | event.event.kanban | `event.view_event_kanban` | - |
| calendar | event.event.calendar | `event.view_event_calendar` | - |
| search | event.event.search | `event.view_event_search` | - |



#### Botones (event.view_event_form)
- **%(event_barcode_action_main_view)d** (action)
- **%(event.event_registration_action_stats_from_event)d** (action)
- **%(event.act_event_registration_from_event)d** (action)
- **Stats** (object)


#### Filtros de búsqueda (event.view_event_search)

**Filtros:**
- **My Events** (`[('user_id', '=', uid)]`)
- **Upcoming/Running** (`[('date_end', '>=', datetime.datetime.combine(context_today(), datetime.time(0,0,0)))]`)
- **Start Date**
- **Archived** (`[('active', '=', False)]`)
- **Late Activities** (`[('my_activity_date_deadline', '<', context_today().strftime('%Y-%m-%d'))]`)
- **Today Activities** (`[('my_activity_date_deadline', '=', context_today().strftime('%Y-%m-%d'))]`)
- **Future Activities** (`[('my_activity_date_deadline', '>', context_today().strftime('%Y-%m-%d'))]`)
- **Online** (`[('address_id', '=', False)]`)


**Agrupar por:**
- Responsible
- Template
- Stage
- Start Date
- Venue


### event.type

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | event.type.form | `event.view_event_type_form` | - |
| list | event.type.list | `event.view_event_type_tree` | - |
| search | event.type.search | `event.event_type_view_search` | - |



### event.registration.answer

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| search | event.registration.answer.view.search | `event.event_registration_answer_view_search` | - |
| list | event.registration.answer.view.list | `event.event_registration_answer_view_tree` | - |
| graph | event.registration.answer.view.graph | `event.event_registration_answer_view_graph` | - |
| pivot | event.registration.answer.view.pivot | `event.event_registration_answer_view_pivot` | - |



### event.type.ticket

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | event.type.ticket.view.list.from.type | `event.event_type_ticket_view_tree_from_type` | - |
| form | event.type.ticket.view.form.from.type | `event.event_type_ticket_view_form_from_type` | - |



### event.event.ticket

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | event.event.ticket.view.list.from.event | `event.event_event_ticket_view_tree_from_event` | - |
| form | event.event.ticket.view.form.from.event | `event.event_event_ticket_view_form_from_event` | - |
| kanban | event.event.ticket.view.kanban.from.event | `event.event_event_ticket_view_kanban_from_event` | - |
| form | event.event.ticket.view.form | `event.event_event_ticket_form_view` | - |



### event.mail

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | event.mail.form | `event.view_event_mail_form` | - |
| list | event.mail.list | `event.view_event_mail_tree` | - |



### event.stage

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | event.stage.view.form | `event.event_stage_view_form` | - |
| list | event.stage.view.list | `event.event_stage_view_tree` | - |



### event.tag.category

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | event.tag.category.view.list | `event.event_tag_category_view_tree` | - |
| form | event.tag.category.view.form | `event.event_tag_category_view_form` | - |



### event.tag

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | event.tag.view.list | `event.event_tag_view_tree` | - |
| form | event.tag.view.form | `event.event_tag_view_form` | - |



### event.question

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | event.question.view.form | `event.event_question_view_form` | - |



### event.registration

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | event.registration.list | `event.view_event_registration_tree` | - |
| form | event.registration.form | `event.view_event_registration_form` | - |
| kanban | event.registration.kanban | `event.event_registration_view_kanban` | - |
| calendar | event.registration.calendar | `event.view_event_registration_calendar` | - |
| pivot | event.registration.pivot | `event.view_event_registration_pivot` | - |
| graph | event.registration.graph | `event.view_event_registration_graph` | - |
| search | event.registration.search | `event.view_registration_search` | - |



#### Botones (event.view_event_registration_form)
- **Send by Email** (object)
- **Registered** (object)
- **Attended** (object)
- **Cancel Registration** (object)


#### Filtros de búsqueda (event.view_registration_search)

**Filtros:**
- **Ongoing Events** (`[('event_id.is_ongoing', '=', True)]`)
- **Taken** (`[('state', 'in', ['open', 'done'])]`)
- **Unconfirmed** (`[('state', '=', 'draft')]`)
- **Registered** (`[('state', '=', 'open')]`)
- **Attended** (`[('state', '=', 'done')]`)
- **Registration Date**
- **Event Start Date**
- **Attended Date**
- **Late Activities** (`[('my_activity_date_deadline', '<', context_today().strftime('%Y-%m-%d'))]`)
- **Today Activities** (`[('my_activity_date_deadline', '=', context_today().strftime('%Y-%m-%d'))]`)
- **Future Activities** (`[('my_activity_date_deadline', '>', context_today().strftime('%Y-%m-%d'))]`)
- **Last 30 days** (`[('create_date','>', (context_today() - datetime.timedelta(days=30)).strftime('%Y-%m-%d'))]`)
- **Archived** (`[('active', '=', False)]`)


**Agrupar por:**
- Partner
- Event
- Ticket Type
- Status
- Registration Date
- Registration Date
- Campaign
- Medium
- Source

