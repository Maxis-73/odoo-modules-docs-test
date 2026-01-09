# Módulo: Online Event Booths

## Información General
- **Nombre técnico:** website_event_booth
- **Versión:** 1.0
- **Categoría:** Marketing/Events
- **Dependencias:** website_event, event_booth


## Propósito
Events, display your booths on your website



## Descripción

Display your booths on your website for the users to register.
    



## Modelos

### event.type


- Hereda de:

  - event.type




#### Campos
- **booth_menu** (Boolean)





### website.event.menu


- Hereda de:

  - website.event.menu




#### Campos
- **menu_type** (Selection)





### event.event


- Hereda de:

  - event.event




#### Campos
- **exhibition_map** (Image)
- **booth_menu** (Boolean)
- **booth_menu_ids** (One2many) → website.event.menu







