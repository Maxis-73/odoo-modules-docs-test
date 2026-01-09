# Módulo: Booths/Exhibitors Bridge

## Información General
- **Nombre técnico:** website_event_booth_exhibitor
- **Versión:** 1.1
- **Categoría:** Marketing/Events
- **Dependencias:** website_event_exhibitor, website_event_booth


## Propósito
Event Booths, automatically create a sponsor.



## Descripción

Automatically create a sponsor when renting a booth.
    



## Modelos

### event.booth


- Hereda de:

  - event.booth




#### Campos
- **use_sponsor** (Boolean)
- **sponsor_type_id** (Many2one)
- **sponsor_id** (Many2one) → event.sponsor
- **sponsor_name** (Char)
- **sponsor_email** (Char)
- **sponsor_mobile** (Char)
- **sponsor_phone** (Char)
- **sponsor_subtitle** (Char)
- **sponsor_website_description** (Html)
- **sponsor_image_512** (Image)





### event.booth.category


- Hereda de:

  - event.booth.category




#### Campos
- **use_sponsor** (Boolean)
- **sponsor_type_id** (Many2one) → event.sponsor.type
- **exhibitor_type** (Selection)







