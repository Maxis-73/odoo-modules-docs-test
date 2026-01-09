# Módulo: Marketing Card

## Información General
- **Nombre técnico:** marketing_card
- **Versión:** 1.1
- **Categoría:** Marketing/Social Marketing
- **Dependencias:** link_tracker, mass_mailing, website


## Propósito
Generate dynamic shareable cards





## Modelos

### card.campaign


- Hereda de:


  - mail.activity.mixin

  - mail.render.mixin

  - mail.thread





- Campos:

  - **name** (Char)


  - **active** (Boolean)


  - **body_html** (Html)


  - **card_count** (Integer)


  - **card_click_count** (Integer)


  - **card_share_count** (Integer)


  - **mailing_ids** (One2many) → mailing.mailing


  - **mailing_count** (Integer)


  - **card_ids** (One2many) → card.card


  - **card_template_id** (Many2one) → card.template


  - **image_preview** (Image)


  - **link_tracker_id** (Many2one) → link.tracker


  - **res_model** (Selection)


  - **post_suggestion** (Text)


  - **preview_record_ref** (Reference)


  - **tag_ids** (Many2many) → card.campaign.tag


  - **target_url** (Char)


  - **target_url_click_count** (Integer)


  - **user_id** (Many2one) → res.users


  - **reward_message** (Html)


  - **reward_target_url** (Char)


  - **request_title** (Char) → Request


  - **request_description** (Text) → Request Description


  - **content_background** (Image) → Background


  - **content_button** (Char) → Button


  - **content_header** (Char) → Header


  - **content_header_dyn** (Boolean) → Is Dynamic Header


  - **content_header_path** (Char) → Header Path


  - **content_header_color** (Char) → Header Color


  - **content_sub_header** (Char) → Sub-Header


  - **content_sub_header_dyn** (Boolean) → Is Dynamic Sub-Header


  - **content_sub_header_path** (Char) → Sub-Header Path


  - **content_sub_header_color** (Char) → Sub Header Color


  - **content_section** (Char) → Section


  - **content_section_dyn** (Boolean) → Is Dynamic Section


  - **content_section_path** (Char) → Section Path


  - **content_sub_section1** (Char) → Sub-Section 1


  - **content_sub_section1_dyn** (Boolean) → Is Dynamic Sub-Section 1


  - **content_sub_section1_path** (Char) → Sub-Section 1 Path


  - **content_sub_section2** (Char) → Sub-Section 2


  - **content_sub_section2_dyn** (Boolean) → Is Dynamic Sub-Section 2


  - **content_sub_section2_path** (Char) → Sub-Section 2 Path


  - **content_image1_path** (Char) → Dynamic Image 1


  - **content_image2_path** (Char) → Dynamic Image 2





### card.template


- Hereda de: Base



- Campos:

  - **name** (Char)


  - **default_background** (Image)


  - **body** (Html)


  - **primary_color** (Char)


  - **secondary_color** (Char)


  - **primary_text_color** (Char)


  - **secondary_text_color** (Char)





### card.campaign.tag


- Hereda de: Base



- Campos:

  - **name** (Char)


  - **color** (Integer)





### ir.model


- Hereda de:

  - ir.model




- No agrega campos



### utm.source


- Hereda de:

  - utm.source




- No agrega campos



### mailing.mailing


- Hereda de:

  - mailing.mailing




- Campos:

  - **mailing_model_id** (Many2one)


  - **card_requires_sync_count** (Integer)


  - **card_campaign_id** (Many2one) → card.campaign





### card.card


- Hereda de: Base



- Campos:

  - **active** (Boolean) → Active


  - **campaign_id** (Many2one) → card.campaign


  - **res_model** (Selection)


  - **res_id** (Many2oneReference) → Record ID


  - **image** (Image)


  - **requires_sync** (Boolean)


  - **share_status** (Selection)








## Vistas


### card.campaign

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | card.campaign.view.form | `marketing_card.card_campaign_view_form` | - |
| kanban | card.campaign.view.kanban | `marketing_card.card_campaign_view_kanban` | - |
| list | card.campaign.view.list | `marketing_card.card_campaign_view_tree` | - |
| search | card.campaign.view.search | `marketing_card.card_campaign_view_search` | - |



#### Botones (marketing_card.card_campaign_view_form)
- **action_share** (object)
- **action_preview** (object)
- **action_view_mailings** (object)
- **action_view_cards** (object)
- **action_view_cards_clicked** (object)
- **action_view_cards_shared** (object)


#### Filtros de búsqueda (marketing_card.card_campaign_view_search)

**Filtros:**
- **My Campaigns** (`[('user_id', '=', uid)]`)
- **Archived** (`[('active', '=', False)]`)


**Agrupar por:**
- Responsible
- Tags


### card.card

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | card.card.view.list | `marketing_card.card_card_view_list` | - |
| search | card.card.view.search | `marketing_card.card_card_view_search` | - |



#### Filtros de búsqueda (marketing_card.card_card_view_search)

**Filtros:**
- **Shared** (`[('share_status', '=', 'shared')]`)
- **Visited** (`[('share_status', '=', 'visited')]`)


**Agrupar por:**
- Campaign


### card.template

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | card.template.view.form | `marketing_card.card_template_view_form` | - |


