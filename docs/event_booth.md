# Módulo: Events Booths

## Información General
- **Nombre técnico:** event_booth
- **Versión:** 1.1
- **Categoría:** Marketing/Events
- **Dependencias:** event


## Propósito
Manage event booths



## Descripción

Create booths for your favorite event.
    



## Modelos

### event.booth


- Hereda de:


  - event.type.booth

  - mail.thread

  - mail.activity.mixin





- Campos:

  - **event_type_id** (Many2one)


  - **event_id** (Many2one) → event.event


  - **partner_id** (Many2one) → res.partner


  - **contact_name** (Char) → Renter Name


  - **contact_email** (Char) → Renter Email


  - **contact_phone** (Char) → Renter Phone


  - **state** (Selection)


  - **is_available** (Boolean)





### event.type.booth


- Hereda de: Base



- Campos:

  - **name** (Char)


  - **event_type_id** (Many2one) → event.type


  - **booth_category_id** (Many2one) → event.booth.category





### event.type


- Hereda de:

  - event.type




- Campos:

  - **event_type_booth_ids** (One2many) → event.type.booth





### event.event


- Hereda de:

  - event.event




- Campos:

  - **event_booth_ids** (One2many) → event.booth


  - **event_booth_count** (Integer)


  - **event_booth_count_available** (Integer)


  - **event_booth_category_ids** (Many2many) → event.booth.category


  - **event_booth_category_available_ids** (Many2many) → event.booth.category





### event.booth.category


- Hereda de:


  - image.mixin





- Campos:

  - **active** (Boolean)


  - **name** (Char)


  - **sequence** (Integer)


  - **description** (Html)


  - **booth_ids** (One2many) → event.booth








## Vistas


### event.booth

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | event.booth.view.form.from.event | `event_booth.event_booth_view_form_from_event` | - |
| list | event.booth.view.list.from.event | `event_booth.event_booth_view_tree_from_event` | - |
| kanban | event.booth.view.kanban | `event_booth.event_booth_view_kanban_from_event` | - |
| form | event.booth.view.form.quick_create | `event_booth.event_booth_view_form_quick_create` | - |
| search | event.booth.view.search | `event_booth.event_booth_view_search` | - |
| graph | event.booth.view.graph | `event_booth.event_booth_view_graph` | - |
| pivot | event.booth.view.pivot | `event_booth.event_booth_view_pivot` | - |



#### Filtros de búsqueda (event_booth.event_booth_view_search)

**Filtros:**
- **Available** (`[('state', '=', 'available')]`)
- **Unavailable** (`[('state', '=', 'unavailable')]`)


**Agrupar por:**
- group_by_state
- group_by_partner_id
- group_by_booth_category_id
- Event


### event.type.booth

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | event.type.booth.view.form.from.type | `event_booth.event_type_booth_view_form_from_type` | - |
| list | event.type.booth.view.list.from.type | `event_booth.event_type_booth_view_tree_from_type` | - |
| search | event.type.booth.view.search | `event_booth.event_type_booth_view_search` | - |



#### Filtros de búsqueda (event_booth.event_type_booth_view_search)


**Agrupar por:**
- Booth Type


### event.booth.category

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | event.booth.category.view.form | `event_booth.event_booth_category_view_form` | - |
| list | event.booth.category.view.list | `event_booth.event_booth_category_view_tree` | - |
| search | event.booth.category.view.search | `event_booth.event_booth_category_view_search` | - |



#### Filtros de búsqueda (event_booth.event_booth_category_view_search)

**Filtros:**
- **Archived** (`[('active', '=', False)]`)

