# Módulo: UTM Trackers

## Información General
- **Nombre técnico:** utm
- **Versión:** 1.1
- **Categoría:** Hidden
- **Dependencias:** base, web




## Descripción

Enable management of UTM trackers: campaign, medium, source.




## Modelos

### utm.tag


- Hereda de: Base



#### Campos
- **name** (Char)
- **color** (Integer)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | utm.tag.view.list | `utm.utm_tag_view_tree` | - |




### utm.campaign


- Hereda de: Base



#### Campos
- **active** (Boolean) → Active
- **name** (Char)
- **title** (Char)
- **user_id** (Many2one) → res.users
- **stage_id** (Many2one) → utm.stage
- **tag_ids** (Many2many) → utm.tag
- **is_auto_campaign** (Boolean)
- **color** (Integer)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| search | utm.campaign.view.search | `utm.view_utm_campaign_view_search` | - |
| form | utm.campaign.view.form | `utm.utm_campaign_view_form` | - |
| list | utm.campaign.view.list | `utm.utm_campaign_view_tree` | - |
| form | utm.campaign.view.form.quick.create | `utm.utm_campaign_view_form_quick_create` | - |
| kanban | utm.campaign.view.kanban | `utm.utm_campaign_view_kanban` | - |



**Filtros de búsqueda (utm.view_utm_campaign_view_search):**

- **My Campaigns** (`[('user_id', '=', uid)]`)
- **Archived** (`[('active', '=', False)]`)


*Agrupar por:*
- Stage
- Responsible
- Tags



### utm.medium


- Hereda de: Base



#### Campos
- **name** (Char)
- **active** (Boolean)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | utm.medium.view.list | `utm.utm_medium_view_tree` | - |
| form | utm.medium.view.form | `utm.utm_medium_view_form` | - |
| search | utm.medium.view.search | `utm.utm_medium_view_search` | - |



**Filtros de búsqueda (utm.utm_medium_view_search):**

- **Archived** (`[('active', '=', False)]`)



### utm.source


- Hereda de: Base



#### Campos
- **name** (Char)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | utm.source.view.list | `utm.utm_source_view_tree` | - |
| form | utm.source.view.form | `utm.utm_source_view_form` | - |




### utm.source.mixin


- Hereda de: Base



#### Campos
- **name** (Char) → Name
- **source_id** (Many2one) → utm.source





### utm.mixin


- Hereda de: Base



#### Campos
- **campaign_id** (Many2one) → utm.campaign
- **source_id** (Many2one) → utm.source
- **medium_id** (Many2one) → utm.medium





### utm.stage


- Hereda de: Base



#### Campos
- **name** (Char)
- **sequence** (Integer)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| search | utm.stage.view.search | `utm.utm_stage_view_search` | - |
| list | utm.stage.view.list | `utm.utm_stage_view_tree` | - |
| form | utm.stage.view.form | `utm.utm_stage_view_form` | - |




### ir.http


- Hereda de:

  - ir.http




- No agrega campos









