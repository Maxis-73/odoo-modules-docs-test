# Módulo: Event Meeting / Rooms

## Información General
- **Nombre técnico:** website_event_meet
- **Versión:** 1.0
- **Categoría:** Marketing/Events
- **Dependencias:** website_event_jitsi


## Propósito
Event: meeting and chat rooms





## Modelos

### event.type


- Hereda de:

  - event.type




#### Campos
- **meeting_room_allow_creation** (Boolean) → Allow Room Creation





### website.event.menu


- Hereda de:

  - website.event.menu




#### Campos
- **menu_type** (Selection)





### event.meeting.room


- Hereda de:


  - chat.room.mixin

  - website.published.mixin





#### Campos
- **name** (Char) → Topic
- **active** (Boolean) → Active
- **is_published** (Boolean)
- **event_id** (Many2one) → event.event
- **is_pinned** (Boolean) → Is Pinned
- **chat_room_id** (Many2one) → chat.room
- **room_max_capacity** (Selection)
- **summary** (Char) → Summary
- **target_audience** (Char) → Audience





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| search | event.meeting.room.search | `website_event_meet.event_meeting_room_view_search` | - |
| form | event.meeting.room.form | `website_event_meet.event_meeting_room_view_form` | - |
| list | event.meeting.room.list | `website_event_meet.event_meeting_room_view_tree` | - |
| search | event.meeting.room.search | `website_event_meet.event_meeting_room_view_search` | - |



**Filtros de búsqueda (website_event_meet.event_meeting_room_view_search):**

- **Unpublished** (`[('is_published', '=', False)]`)


*Agrupar por:*
- Event



### event.event


- Hereda de:

  - event.event




#### Campos
- **meeting_room_ids** (One2many) → event.meeting.room
- **meeting_room_count** (Integer) → Room count
- **meeting_room_allow_creation** (Boolean) → Allow Room Creation










