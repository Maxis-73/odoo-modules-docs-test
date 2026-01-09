# Módulo: IM Bus

## Información General
- **Nombre técnico:** bus
- **Versión:** 1.0
- **Categoría:** Hidden
- **Dependencias:** base, web




## Descripción
Instant Messaging Bus allow you to send messages to users, in live.



## Modelos

### res.groups


- Hereda de:


  - res.groups

  - bus.listener.mixin





- No agrega campos



### ir.model


- Hereda de:

  - ir.model




- No agrega campos



### bus.bus


- Hereda de: Base



- Campos:

  - **channel** (Char) → Channel


  - **message** (Char) → Message





### res.users


- Hereda de:


  - res.users

  - bus.listener.mixin





- Campos:

  - **im_status** (Char) → IM Status





### ir.attachment


- Hereda de:


  - ir.attachment

  - bus.listener.mixin





- No agrega campos



### bus.listener.mixin


- Hereda de: Base



- No agrega campos



### ir.http


- Hereda de:

  - ir.http




- No agrega campos



### ir.websocket


- Hereda de: Base



- No agrega campos



### res.partner


- Hereda de:


  - res.partner

  - bus.listener.mixin





- Campos:

  - **im_status** (Char) → IM Status





### bus.presence


- Hereda de: Base



- Campos:

  - **user_id** (Many2one) → res.users


  - **last_poll** (Datetime) → Last Poll


  - **last_presence** (Datetime) → Last Presence


  - **status** (Selection)





### res.users.settings


- Hereda de:


  - res.users.settings

  - bus.listener.mixin





- No agrega campos





