# Módulo: Link Tracker

## Información General
- **Nombre técnico:** link_tracker
- **Versión:** 1.1
- **Categoría:** Marketing
- **Dependencias:** utm, mail




## Descripción

Shorten URLs and use them to track clicks and UTMs




## Modelos

### ['utm.campaign']


- Hereda de:


  - utm.campaign





- Campos:

  - **click_count** (Integer)





### mail.render.mixin


- Hereda de:

  - mail.render.mixin




- No agrega campos



### link.tracker


- Hereda de:


  - utm.mixin





- Campos:

  - **url** (Char)


  - **absolute_url** (Char) → Absolute URL


  - **short_url** (Char)


  - **redirected_url** (Char)


  - **short_url_host** (Char)


  - **title** (Char)


  - **label** (Char)


  - **link_code_ids** (One2many) → link.tracker.code


  - **code** (Char)


  - **link_click_ids** (One2many) → link.tracker.click


  - **count** (Integer)


  - **campaign_id** (Many2one)


  - **medium_id** (Many2one)


  - **source_id** (Many2one)





### link.tracker.code


- Hereda de: Base



- Campos:

  - **code** (Char)


  - **link_id** (Many2one) → link.tracker





### link.tracker.click


- Hereda de: Base



- Campos:

  - **campaign_id** (Many2one) → utm.campaign


  - **link_id** (Many2one) → link.tracker


  - **ip** (Char)


  - **country_id** (Many2one) → res.country








## Vistas


### link.tracker

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| search | link.tracker.view.search | `link_tracker.link_tracker_view_search` | - |
| form | link.tracker.view.form | `link_tracker.link_tracker_view_form` | - |
| list | link.tracker.view.list | `link_tracker.link_tracker_view_tree` | - |
| graph | link.tracker.view.graph | `link_tracker.link_tracker_view_graph` | - |



#### Filtros de búsqueda (link_tracker.link_tracker_view_search)


**Agrupar por:**
- Campaign
- Medium
- Source


#### Botones (link_tracker.link_tracker_view_form)
- **Visit Page** (object)
- **action_view_statistics** (object)


### link.tracker.click

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| search | link.tracker.click.view.search | `link_tracker.link_tracker_click_view_search` | - |
| form | link.tracker.click.view.form | `link_tracker.link_tracker_click_view_form` | - |
| list | link.tracker.click.view.list | `link_tracker.link_tracker_click_view_tree` | - |
| graph | link.tracker.click.view.graph | `link_tracker.link_tracker_click_view_graph` | - |



#### Filtros de búsqueda (link_tracker.link_tracker_click_view_search)


**Agrupar por:**
- Link
- Country

