# Módulo: Event Exhibitors

## Información General
- **Nombre técnico:** website_event_exhibitor
- **Versión:** 1.1
- **Categoría:** Marketing/Events
- **Dependencias:** website_event_jitsi


## Propósito
Event: manage sponsors and exhibitors





## Modelos

### event.type


- Hereda de:

  - event.type




#### Campos
- **exhibitor_menu** (Boolean)





### website.event.menu


- Hereda de:

  - website.event.menu




#### Campos
- **menu_type** (Selection)





### event.sponsor


- Hereda de:


  - mail.thread

  - mail.activity.mixin

  - website.published.mixin

  - chat.room.mixin





#### Campos
- **event_id** (Many2one) → event.event
- **sponsor_type_id** (Many2one) → event.sponsor.type
- **url** (Char) → Sponsor Website
- **sequence** (Integer) → Sequence
- **active** (Boolean)
- **subtitle** (Char) → Slogan
- **exhibitor_type** (Selection)
- **website_description** (Html) → Description
- **partner_id** (Many2one) → res.partner
- **partner_name** (Char) → Name
- **partner_email** (Char) → Email
- **partner_phone** (Char) → Phone
- **partner_mobile** (Char) → Mobile
- **name** (Char) → Sponsor Name
- **email** (Char) → Sponsor Email
- **phone** (Char) → Sponsor Phone
- **mobile** (Char) → Sponsor Mobile
- **image_512** (Image)
- **image_256** (Image) → Image 256
- **image_128** (Image) → Image 128
- **website_image_url** (Char)
- **hour_from** (Float) → Opening hour
- **hour_to** (Float) → End hour
- **event_date_tz** (Selection)
- **is_in_opening_hours** (Boolean) → Within opening hours
- **chat_room_id** (Many2one)
- **room_name** (Char)
- **country_id** (Many2one) → res.country
- **country_flag_url** (Char)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| search | event.sponsor.search | `website_event_exhibitor.event_sponsor_view_search` | - |
| form | event.sponsor.view.form | `website_event_exhibitor.event_sponsor_view_form` | - |
| list | event.sponsor.view.list | `website_event_exhibitor.event_sponsor_view_tree` | - |
| kanban | event.sponsor.view.kanban | `website_event_exhibitor.event_sponsor_view_kanban` | - |



**Filtros de búsqueda (website_event_exhibitor.event_sponsor_view_search):**

- **Published** (`[('website_published', '=', True)]`)
- **Archived** (`[('active', '=', False)]`)
- **Exhibitors** (`[('exhibitor_type', 'in', ['exhibitor', 'online'])]`)
- **Online** (`[('exhibitor_type', '=', 'online')]`)


*Agrupar por:*
- Event
- Level



### event.sponsor.type


- Hereda de: Base



#### Campos
- **name** (Char) → Sponsor Level
- **sequence** (Integer) → Sequence
- **display_ribbon_style** (Selection)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | Sponsor Levels | `website_event_exhibitor.event_sponsor_type_view_form` | - |
| list | Sponsor Levels | `website_event_exhibitor.event_sponsor_type_view_tree` | - |




### event.event


- Hereda de:

  - event.event




#### Campos
- **sponsor_ids** (One2many) → event.sponsor
- **sponsor_count** (Integer) → Sponsor Count
- **exhibitor_menu** (Boolean)
- **exhibitor_menu_ids** (One2many) → website.event.menu










