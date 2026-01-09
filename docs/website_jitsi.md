# Módulo: Website Jitsi

## Información General
- **Nombre técnico:** website_jitsi
- **Versión:** 1.0
- **Categoría:** Hidden
- **Dependencias:** website


## Propósito
Create Jitsi room on website.



## Descripción
Create Jitsi room on website.



## Modelos

### chat.room


- Hereda de: Base



- Campos:

  - **name** (Char) → Room Name


  - **is_full** (Boolean) → Full


  - **jitsi_server_domain** (Char) → Jitsi Server Domain


  - **lang_id** (Many2one) → res.lang


  - **max_capacity** (Selection)


  - **participant_count** (Integer) → Participant count


  - **last_activity** (Datetime) → Last Activity


  - **max_participant_reached** (Integer) → Max participant reached





### chat.room.mixin


- Hereda de: Base



- Campos:

  - **chat_room_id** (Many2one) → chat.room


  - **room_name** (Char) → Room Name


  - **room_is_full** (Boolean) → Room Is Full


  - **room_lang_id** (Many2one) → res.lang


  - **room_max_capacity** (Selection)


  - **room_participant_count** (Integer) → Participant count


  - **room_last_activity** (Datetime) → Last activity


  - **room_max_participant_reached** (Integer) → Peak participants








## Vistas


### chat.room

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| search | chat.room.search | `website_jitsi.chat_room_view_search` | - |
| form | chat.room.form | `website_jitsi.chat_room_view_form` | - |
| list | chat.room.list | `website_jitsi.chat_room_view_tree` | - |


