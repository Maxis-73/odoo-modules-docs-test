# Módulo: Calendar - SMS

## Información General
- **Nombre técnico:** calendar_sms
- **Versión:** 1.1
- **Categoría:** Hidden
- **Dependencias:** calendar, sms


## Propósito
Send text messages as event reminders



## Descripción
Send text messages as event reminders



## Modelos

### calendar.alarm_manager


- Hereda de:

  - calendar.alarm_manager




- No agrega campos



### calendar.alarm


- Hereda de:

  - calendar.alarm




- Campos:

  - **alarm_type** (Selection)


  - **sms_template_id** (Many2one) → sms.template


  - **sms_notify_responsible** (Boolean) → Notify Responsible





### calendar.event


- Hereda de:

  - calendar.event




- No agrega campos





