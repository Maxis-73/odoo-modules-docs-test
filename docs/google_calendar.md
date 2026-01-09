# Módulo: Google Calendar

## Información General
- **Nombre técnico:** google_calendar
- **Versión:** 1.0
- **Categoría:** Productivity
- **Dependencias:** google_account, calendar






## Modelos

### google.calendar.sync


- Hereda de: Base



#### Campos
- **google_id** (Char) → Google Calendar Id
- **need_sync** (Boolean)
- **active** (Boolean)





### calendar.alarm_manager


- Hereda de:

  - calendar.alarm_manager




- No agrega campos




### calendar.attendee


- Hereda de:

  - calendar.attendee




- No agrega campos




### res.users


- Hereda de:

  - res.users




#### Campos
- **google_calendar_rtoken** (Char)
- **google_calendar_token** (Char)
- **google_calendar_token_validity** (Datetime)
- **google_calendar_sync_token** (Char)
- **google_calendar_cal_id** (Char)
- **google_synchronization_stopped** (Boolean)





### calendar.event


- Hereda de:


  - calendar.event

  - google.calendar.sync





#### Campos
- **google_id** (Char) → Google Calendar Event Id
- **guests_readonly** (Boolean) → Guests Event Modification Permission
- **videocall_source** (Selection)





### res.config.settings


- Hereda de:

  - res.config.settings




#### Campos
- **cal_client_id** (Char) → Client_id
- **cal_client_secret** (Char) → Client_key
- **cal_sync_paused** (Boolean) → Google Synchronization Paused





### calendar.recurrence


- Hereda de:


  - calendar.recurrence

  - google.calendar.sync





- No agrega campos




### res.users.settings


- Hereda de:

  - res.users.settings




#### Campos
- **google_calendar_rtoken** (Char) → Refresh Token
- **google_calendar_token** (Char) → User token
- **google_calendar_token_validity** (Datetime) → Token Validity
- **google_calendar_sync_token** (Char) → Next Sync Token
- **google_calendar_cal_id** (Char) → Calendar ID
- **google_synchronization_stopped** (Boolean) → Google Synchronization stopped










## Vistas Adicionales


### google.calendar.account.reset

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | google.calendar.account.reset.form | `google_calendar.google_calendar_reset_account_view_form` | - |



**Botones (google_calendar.google_calendar_reset_account_view_form):**
- **Confirm** (object)



