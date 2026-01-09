# Módulo: Advanced Events

## Información General
- **Nombre técnico:** website_event_track
- **Versión:** 1.3
- **Categoría:** Marketing
- **Dependencias:** website_event


## Propósito
Sponsors, Tracks, Agenda, Event News





## Modelos

### website


- Hereda de:

  - website




- Campos:

  - **app_icon** (Image)


  - **events_app_name** (Char)





### event.track.location


- Hereda de: Base



- Campos:

  - **name** (Char) → Location


  - **sequence** (Integer)





### event.track.tag.category


- Hereda de: Base



- Campos:

  - **name** (Char) → Name


  - **sequence** (Integer) → Sequence


  - **tag_ids** (One2many) → event.track.tag





### website.menu


- Hereda de:

  - website.menu




- No agrega campos



### event.type


- Hereda de:

  - event.type




- Campos:

  - **website_track** (Boolean)


  - **website_track_proposal** (Boolean)





### website.event.menu


- Hereda de:

  - website.event.menu




- Campos:

  - **menu_type** (Selection)





### event.track.visitor


- Hereda de: Base



- Campos:

  - **partner_id** (Many2one) → res.partner


  - **visitor_id** (Many2one) → website.visitor


  - **track_id** (Many2one) → event.track


  - **is_wishlisted** (Boolean)


  - **is_blacklisted** (Boolean)





### event.track


- Hereda de:


  - mail.thread

  - mail.activity.mixin

  - website.seo.metadata

  - website.published.mixin





- Campos:

  - **name** (Char) → Title


  - **event_id** (Many2one) → event.event


  - **active** (Boolean)


  - **user_id** (Many2one) → res.users


  - **company_id** (Many2one) → res.company


  - **tag_ids** (Many2many) → event.track.tag


  - **description** (Html)


  - **color** (Integer) → Agenda Color


  - **priority** (Selection)


  - **stage_id** (Many2one) → event.track.stage


  - **legend_blocked** (Char)


  - **legend_done** (Char)


  - **legend_normal** (Char)


  - **kanban_state** (Selection)


  - **kanban_state_label** (Char)


  - **partner_id** (Many2one) → res.partner


  - **partner_name** (Char)


  - **partner_email** (Char)


  - **partner_phone** (Char)


  - **partner_biography** (Html)


  - **partner_function** (Char) → Job Position


  - **partner_company_name** (Char) → Company Name


  - **partner_tag_line** (Char) → Tag Line


  - **image** (Image)


  - **contact_email** (Char)


  - **contact_phone** (Char)


  - **location_id** (Many2one) → event.track.location


  - **date** (Datetime) → Track Date


  - **date_end** (Datetime) → Track End Date


  - **duration** (Float) → Duration


  - **is_track_live** (Boolean) → Is Track Live


  - **is_track_soon** (Boolean) → Is Track Soon


  - **is_track_today** (Boolean) → Is Track Today


  - **is_track_upcoming** (Boolean) → Is Track Upcoming


  - **is_track_done** (Boolean) → Is Track Done


  - **track_start_remaining** (Integer) → Minutes before track starts


  - **track_start_relative** (Integer) → Minutes compare to track start


  - **website_image** (Image)


  - **website_image_url** (Char)


  - **event_track_visitor_ids** (One2many) → event.track.visitor


  - **is_reminder_on** (Boolean) → Is Reminder On


  - **wishlist_visitor_ids** (Many2many) → website.visitor


  - **wishlist_visitor_count** (Integer)


  - **wishlisted_by_default** (Boolean)


  - **website_cta** (Boolean) → Magic Button


  - **website_cta_title** (Char) → Button Title


  - **website_cta_url** (Char) → Button Target URL


  - **website_cta_delay** (Integer) → Show Button


  - **is_website_cta_live** (Boolean) → Is CTA Live


  - **website_cta_start_remaining** (Integer) → Minutes before CTA starts





### event.track.tag


- Hereda de: Base



- Campos:

  - **name** (Char) → Tag Name


  - **track_ids** (Many2many) → event.track


  - **color** (Integer)


  - **sequence** (Integer) → Sequence


  - **category_id** (Many2one) → event.track.tag.category





### event.event


- Hereda de:

  - event.event




- Campos:

  - **track_ids** (One2many) → event.track


  - **track_count** (Integer) → Track Count


  - **website_track** (Boolean) → Tracks on Website


  - **website_track_proposal** (Boolean) → Proposals on Website


  - **track_menu_ids** (One2many) → website.event.menu


  - **track_proposal_menu_ids** (One2many) → website.event.menu


  - **allowed_track_tag_ids** (Many2many) → event.track.tag


  - **tracks_tag_ids** (Many2many) → event.track.tag





### event.track.stage


- Hereda de: Base



- Campos:

  - **name** (Char)


  - **sequence** (Integer)


  - **mail_template_id** (Many2one) → mail.template


  - **color** (Integer)


  - **description** (Text)


  - **legend_blocked** (Char) → Red Kanban Label


  - **legend_done** (Char) → Green Kanban Label


  - **legend_normal** (Char) → Grey Kanban Label


  - **fold** (Boolean)


  - **is_visible_in_agenda** (Boolean)


  - **is_fully_accessible** (Boolean)


  - **is_cancel** (Boolean)





### res.config.settings


- Hereda de:

  - res.config.settings




- Campos:

  - **events_app_name** (Char) → Events App Name





### website.visitor


- Hereda de:


  - website.visitor





- Campos:

  - **event_track_visitor_ids** (One2many) → event.track.visitor


  - **event_track_wishlisted_ids** (Many2many) → event.track


  - **event_track_wishlisted_count** (Integer)








## Vistas


### event.track

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | event.track.view.form.quick.create | `website_event_track.event_track_view_form_quick_create` | - |
| kanban | event.track.kanban | `website_event_track.view_event_track_kanban` | - |
| calendar | event.track.calendar | `website_event_track.view_event_track_calendar` | - |
| search | event.track.search | `website_event_track.view_event_track_search` | - |
| form | event.track.form | `website_event_track.view_event_track_form` | - |
| list | event.track.list | `website_event_track.view_event_track_tree` | - |
| graph | event.track.graph | `website_event_track.view_event_track_graph` | - |



#### Filtros de búsqueda (website_event_track.view_event_track_search)

**Filtros:**
- **My Tracks** (`[('user_id', '=', uid)]`)
- **Published** (`[('website_published', '=', True)]`)
- **Unread Messages** (`[('message_needaction', '=', True)]`)
- **Always Wishlisted** (`[('wishlisted_by_default', '=', True)]`)
- **filter_date**
- **Archived** (`[('active', '=', False)]`)
- **Late Activities** (`[('my_activity_date_deadline', '<', context_today().strftime('%Y-%m-%d'))]`)
- **Today Activities** (`[('my_activity_date_deadline', '=', context_today().strftime('%Y-%m-%d'))]`)
- **Future Activities** (`[('my_activity_date_deadline', '>', context_today().strftime('%Y-%m-%d'))]`)


**Agrupar por:**
- Responsible
- Stage
- Date
- Event
- Location


#### Botones (website_event_track.view_event_track_form)
- **%(website_event_track.website_visitor_action_from_track)d** (action) - Grupos: `event.group_event_user`


### event.track.stage

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| search | event.track.stage.view.search | `website_event_track.event_track_stage_view_search` | - |
| form | event.track.stage.view.form | `website_event_track.event_track_stage_view_form` | - |
| list | event.track.stage.view.list | `website_event_track.event_track_stage_view_tree` | - |
| kanban | event.track.stage.kanban | `website_event_track.view_event_track_stage_kanban` | - |



### event.track.tag.category

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | event.track.tag.category.view.form | `website_event_track.event_track_tag_category_view_form` | - |
| list | event.track.tag.category.view.list | `website_event_track.event_track_tag_category_view_list` | - |



### event.track.tag

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | Track Tags | `website_event_track.view_event_track_tag_form` | - |
| list | Tracks Tag | `website_event_track.view_event_track_tag_tree` | - |



### event.track.location

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | Event Locations | `website_event_track.view_event_location_form` | - |
| list | Event Location | `website_event_track.view_event_location_tree` | - |



### event.track.visitor

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| search | event.track.visitor.view.search | `website_event_track.event_track_visitor_view_search` | - |
| form | event.track.visitor.view.form | `website_event_track.event_track_visitor_view_form` | - |
| list | event.track.visitor.view.list | `website_event_track.event_track_visitor_view_list` | - |



#### Filtros de búsqueda (website_event_track.event_track_visitor_view_search)


**Agrupar por:**
- Track
- Visitor
- Customer

