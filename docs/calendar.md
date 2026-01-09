# Módulo: Calendar

## Información General
- **Nombre técnico:** calendar
- **Versión:** 1.1
- **Categoría:** Productivity/Calendar
- **Dependencias:** base, mail


## Propósito
Schedule employees' meetings



## Descripción

This is a full-featured calendar system.

It supports:
------------
    - Calendar of events
    - Recurring events

If you need to manage your meetings, you should install the CRM module.
    



## Modelos

### calendar.recurrence


- Hereda de: Base



- Campos:

  - **name** (Char)


  - **base_event_id** (Many2one) → calendar.event


  - **calendar_event_ids** (One2many) → calendar.event


  - **event_tz** (Selection)


  - **rrule** (Char)


  - **dtstart** (Datetime)


  - **rrule_type** (Selection)


  - **end_type** (Selection)


  - **interval** (Integer)


  - **count** (Integer)


  - **mon** (Boolean)


  - **tue** (Boolean)


  - **wed** (Boolean)


  - **thu** (Boolean)


  - **fri** (Boolean)


  - **sat** (Boolean)


  - **sun** (Boolean)


  - **month_by** (Selection)


  - **day** (Integer)


  - **weekday** (Selection)


  - **byday** (Selection)


  - **until** (Date) → Repeat Until


  - **trigger_id** (Many2one) → ir.cron.trigger





### mail.activity.type


- Hereda de:

  - mail.activity.type




- Campos:

  - **category** (Selection)





### calendar.alarm_manager


- Hereda de: Base



- No agrega campos



### mail.activity.mixin


- Hereda de:

  - mail.activity.mixin




- Campos:

  - **activity_calendar_event_id** (Many2one) → calendar.event





### calendar.attendee


- Hereda de: Base



- Campos:

  - **event_id** (Many2one) → calendar.event


  - **recurrence_id** (Many2one) → calendar.recurrence


  - **partner_id** (Many2one) → res.partner


  - **email** (Char) → Email


  - **phone** (Char) → Phone


  - **common_name** (Char) → Common name


  - **access_token** (Char) → Invitation Token


  - **mail_tz** (Selection)


  - **state** (Selection)


  - **availability** (Selection)





### res.users


- Hereda de:

  - res.users




- Campos:

  - **calendar_default_privacy** (Selection)





### calendar.alarm


- Hereda de: Base



- Campos:

  - **name** (Char) → Name


  - **alarm_type** (Selection)


  - **duration** (Integer) → Remind Before


  - **interval** (Selection)


  - **duration_minutes** (Integer) → Duration in minutes


  - **mail_template_id** (Many2one) → mail.template


  - **body** (Text) → Additional Message





### calendar.event


- Hereda de:


  - mail.thread





- Campos:

  - **name** (Char) → Meeting Subject


  - **description** (Html) → Description


  - **user_id** (Many2one) → res.users


  - **partner_id** (Many2one) → res.partner


  - **location** (Char) → Location


  - **videocall_location** (Char) → Meeting URL


  - **access_token** (Char) → Invitation Token


  - **videocall_source** (Selection)


  - **videocall_channel_id** (Many2one) → discuss.channel


  - **privacy** (Selection)


  - **show_as** (Selection)


  - **is_highlighted** (Boolean)


  - **is_organizer_alone** (Boolean)


  - **active** (Boolean) → Active


  - **categ_ids** (Many2many) → calendar.event.type


  - **start** (Datetime) → Start


  - **stop** (Datetime) → Stop


  - **display_time** (Char) → Event Time


  - **allday** (Boolean) → All Day


  - **start_date** (Date) → Start Date


  - **stop_date** (Date) → End Date


  - **duration** (Float) → Duration


  - **res_id** (Many2oneReference) → Document ID


  - **res_model_id** (Many2one) → ir.model


  - **res_model** (Char) → Document Model Name


  - **res_model_name** (Char)


  - **activity_ids** (One2many) → mail.activity


  - **attendee_ids** (One2many) → calendar.attendee


  - **current_attendee** (Many2one) → calendar.attendee


  - **current_status** (Selection)


  - **should_show_status** (Boolean)


  - **partner_ids** (Many2many) → res.partner


  - **invalid_email_partner_ids** (Many2many) → res.partner


  - **alarm_ids** (Many2many) → calendar.alarm


  - **recurrency** (Boolean) → Recurrent


  - **recurrence_id** (Many2one) → calendar.recurrence


  - **follow_recurrence** (Boolean)


  - **recurrence_update** (Selection)


  - **rrule** (Char) → Recurrent Rule


  - **rrule_type_ui** (Selection)


  - **rrule_type** (Selection)


  - **event_tz** (Selection)


  - **end_type** (Selection)


  - **interval** (Integer)


  - **count** (Integer)


  - **mon** (Boolean)


  - **tue** (Boolean)


  - **wed** (Boolean)


  - **thu** (Boolean)


  - **fri** (Boolean)


  - **sat** (Boolean)


  - **sun** (Boolean)


  - **month_by** (Selection)


  - **day** (Integer) → Date of month


  - **weekday** (Selection)


  - **byday** (Selection)


  - **until** (Date)


  - **display_description** (Boolean)


  - **attendees_count** (Integer)


  - **accepted_count** (Integer)


  - **declined_count** (Integer)


  - **tentative_count** (Integer)


  - **awaiting_count** (Integer)


  - **user_can_edit** (Boolean)





### mail.activity


- Hereda de:

  - mail.activity




- Campos:

  - **calendar_event_id** (Many2one) → calendar.event





### calendar.event.type


- Hereda de: Base



- Campos:

  - **name** (Char) → Name


  - **color** (Integer) → Color





### ir.http


- Hereda de:

  - ir.http




- No agrega campos



### res.partner


- Hereda de:

  - res.partner




- Campos:

  - **meeting_count** (Integer) → # Meetings


  - **meeting_ids** (Many2many) → calendar.event


  - **calendar_last_notif_ack** (Datetime) → Last notification marked as read from base Calendar





### calendar.filters


- Hereda de: Base



- Campos:

  - **user_id** (Many2one) → res.users


  - **partner_id** (Many2one) → res.partner


  - **active** (Boolean) → Active


  - **partner_checked** (Boolean) → Checked





### res.users.settings


- Hereda de:

  - res.users.settings




- Campos:

  - **calendar_default_privacy** (Selection)








## Vistas


### calendar.event.type

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | calendar.event.type | `calendar.view_calendar_event_type_tree` | - |



### calendar.alarm

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | calendar.alarm.list | `calendar.view_calendar_alarm_tree` | - |
| form | calendar.alarm.form | `calendar.calendar_alarm_view_form` | - |



### calendar.event

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | calendar.event.list | `calendar.view_calendar_event_tree` | - |
| form | calendar.event.form | `calendar.view_calendar_event_form` | - |
| form | calendar.event.form.quick_create | `calendar.view_calendar_event_form_quick_create` | - |
| calendar | calendar.event.calendar | `calendar.view_calendar_event_calendar` | - |
| search | calendar.event.search | `calendar.view_calendar_event_search` | - |



#### Botones (calendar.view_calendar_event_form)
- **action_open_calendar_event** (object)
- **clear_videocall_location** (object)
- **set_discuss_videocall_location** (object)
- **action_join_video_call** (object)
- ** EMAIL** (object)
- **Send Invitations** (object)
- **Uncertain** (object)
- **Accept** (object)
- **Decline** (object)
- **Uncertain** (object)
- **Accept** (object)
- **Decline** (object)


#### Botones (calendar.view_calendar_event_form_quick_create)
- **clear_videocall_location** (object)
- **set_discuss_videocall_location** (object)
- **action_join_video_call** (object)


#### Filtros de búsqueda (calendar.view_calendar_event_search)

**Filtros:**
- **My Meetings** (`[('partner_ids.user_ids', 'in', [uid])]`)
- **Date**
- **Busy** (`[('show_as', '=', 'busy')]`)
- **Free** (`[('show_as', '=', 'free')]`)
- **Default Privacy** (`[('privacy', '=', False)]`)
- **Public** (`[('privacy', '=', 'public')]`)
- **Private** (`[('privacy', '=', 'private')]`)
- **Only Internal Users** (`[('privacy', '=', 'confidential')]`)
- **Recurrent** (`[('recurrency', '=', True)]`)
- **Archived** (`[('active', '=', False)]`)


**Agrupar por:**
- Responsible


### calendar.popover.delete.wizard

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | calendar.popover.delete.wizard.view.form | `calendar.calendar_popover_delete_view` | - |



#### Botones (calendar.calendar_popover_delete_view)
- **Submit** (object)


### calendar.provider.config

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | calendar.provider.config.view.form | `calendar.calendar_provider_config_view_form` | - |


