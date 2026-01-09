# Módulo: Outlook Calendar

## Información General
- **Nombre técnico:** microsoft_calendar
- **Versión:** 1.0
- **Categoría:** Productivity
- **Dependencias:** microsoft_account, calendar






## Modelos

### calendar.alarm_manager


- Hereda de:

  - calendar.alarm_manager




- No agrega campos




### microsoft.calendar.sync


- Hereda de: Base



#### Campos
- **microsoft_id** (Char) → Organizer event Id
- **ms_universal_event_id** (Char) → Universal event Id
- **need_sync_m** (Boolean)
- **active** (Boolean)





### calendar.attendee


- Hereda de:

  - calendar.attendee




- No agrega campos




### res.users


- Hereda de:

  - res.users




#### Campos
- **microsoft_calendar_sync_token** (Char)
- **microsoft_synchronization_stopped** (Boolean)
- **microsoft_last_sync_date** (Datetime)





### calendar.event


- Hereda de:


  - calendar.event

  - microsoft.calendar.sync





#### Campos
- **microsoft_recurrence_master_id** (Char) → Microsoft Recurrence Master Id





### res.config.settings


- Hereda de:

  - res.config.settings




#### Campos
- **cal_microsoft_client_id** (Char) → Microsoft Client_id
- **cal_microsoft_client_secret** (Char) → Microsoft Client_key
- **cal_microsoft_sync_paused** (Boolean) → Microsoft Synchronization Paused





### calendar.recurrence


- Hereda de:


  - calendar.recurrence

  - microsoft.calendar.sync





#### Campos
- **need_sync_m** (Boolean)





### res.users.settings


- Hereda de:

  - res.users.settings




#### Campos
- **microsoft_calendar_sync_token** (Char) → Microsoft Next Sync Token
- **microsoft_synchronization_stopped** (Boolean) → Outlook Synchronization stopped
- **microsoft_last_sync_date** (Datetime) → Last Sync Date










## Vistas Adicionales


### microsoft.calendar.account.reset

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | microsoft.calendar.account.reset.form | `microsoft_calendar.microsoft_calendar_reset_account_view_form` | - |



**Botones (microsoft_calendar.microsoft_calendar_reset_account_view_form):**
- **Confirm** (object)



