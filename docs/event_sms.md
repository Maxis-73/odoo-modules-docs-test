# Módulo: SMS on Events

## Información General
- **Nombre técnico:** event_sms
- **Versión:** 1.0
- **Categoría:** Marketing/Events
- **Dependencias:** event, sms




## Descripción
Schedule SMS in event management



## Modelos

### event.mail.registration


- Hereda de:

  - event.mail.registration




- No agrega campos




### event.type.mail


- Hereda de:

  - event.type.mail




#### Campos
- **notification_type** (Selection)
- **template_ref** (Reference)





### event.mail


- Hereda de:

  - event.mail




#### Campos
- **notification_type** (Selection)
- **template_ref** (Reference)





### sms.template


- Hereda de:

  - sms.template




- No agrega campos






