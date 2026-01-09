# Módulo: Events

## Información General
- **Nombre técnico:** website_event
- **Versión:** 1.4
- **Categoría:** Marketing/Events
- **Dependencias:** event, website, website_partner, website_mail


## Propósito
Publish events, sell tickets





## Modelos

### website


- Hereda de:

  - website




- No agrega campos




### event.tag


- Hereda de:


  - event.tag

  - website.published.multi.mixin





- No agrega campos




### event.tag.category


- Hereda de:


  - event.tag.category

  - website.published.multi.mixin





- No agrega campos




### website.menu


- Hereda de:

  - website.menu




- No agrega campos




### event.type


- Hereda de:


  - event.type





#### Campos
- **website_menu** (Boolean) → Display a dedicated menu on Website
- **community_menu** (Boolean) → Community Menu





### website.event.menu


- Hereda de: Base



#### Campos
- **menu_id** (Many2one) → website.menu
- **event_id** (Many2one) → event.event
- **view_id** (Many2one) → ir.ui.view
- **menu_type** (Selection)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| search | website.event.menu.view.search | `website_event.website_event_menu_view_search` | - |
| form | website.event.menu.view.form | `website_event.website_event_menu_view_form` | - |
| list | website.event.menu.view.list | `website_event.website_event_menu_view_tree` | - |




### website.snippet.filter


- Hereda de:

  - website.snippet.filter




- No agrega campos




### event.event


- Hereda de:


  - event.event

  - website.seo.metadata

  - website.published.multi.mixin

  - website.cover_properties.mixin

  - website.searchable.mixin





#### Campos
- **subtitle** (Char) → Event Subtitle
- **is_participating** (Boolean) → Is Participating
- **is_visible_on_website** (Boolean)
- **event_register_url** (Char) → Event Registration Link
- **website_visibility** (Selection)
- **website_published** (Boolean)
- **website_menu** (Boolean)
- **menu_id** (Many2one) → website.menu
- **introduction_menu** (Boolean) → Introduction Menu
- **introduction_menu_ids** (One2many) → website.event.menu
- **location_menu** (Boolean) → Location Menu
- **location_menu_ids** (One2many) → website.event.menu
- **address_name** (Char)
- **register_menu** (Boolean) → Register Menu
- **register_menu_ids** (One2many) → website.event.menu
- **community_menu** (Boolean) → Community Menu
- **community_menu_ids** (One2many) → website.event.menu
- **is_ongoing** (Boolean) → Is Ongoing
- **is_done** (Boolean) → Is Done
- **start_today** (Boolean) → Start Today
- **start_remaining** (Integer) → Remaining before start





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | event.event.view.form.add | `website_event.event_event_view_form_add` | - |




### event.registration


- Hereda de:

  - event.registration




#### Campos
- **visitor_id** (Many2one) → website.visitor





### website.visitor


- Hereda de:


  - website.visitor





#### Campos
- **event_registration_ids** (One2many) → event.registration
- **event_registration_count** (Integer) → # Registrations
- **event_registered_ids** (Many2many) → event.event










