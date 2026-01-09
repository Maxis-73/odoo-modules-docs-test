# Módulo: Website

## Información General
- **Nombre técnico:** website
- **Versión:** 1.0
- **Categoría:** Website/Website
- **Dependencias:** digest, web, web_editor, html_editor, http_routing, portal, social_media, auth_signup, mail, google_recaptcha, utm


## Propósito
Enterprise website builder





## Modelos

### website


- Hereda de: Base



#### Campos
- **name** (Char) → Website Name
- **sequence** (Integer)
- **domain** (Char) → Website Domain
- **domain_punycode** (Char)
- **company_id** (Many2one) → res.company
- **language_ids** (Many2many) → res.lang
- **language_count** (Integer) → Number of languages
- **default_lang_id** (Many2one) → res.lang
- **auto_redirect_lang** (Boolean) → Autoredirect Language
- **cookies_bar** (Boolean) → Cookies Bar
- **configurator_done** (Boolean)
- **block_third_party_domains** (Boolean) → Block 3rd-party domains
- **custom_blocked_third_party_domains** (Text) → User list of blocked 3rd-party domains
- **blocked_third_party_domains** (Text) → List of blocked 3rd-party domains
- **logo** (Binary) → Website Logo
- **social_twitter** (Char) → X Account
- **social_facebook** (Char) → Facebook Account
- **social_github** (Char) → GitHub Account
- **social_linkedin** (Char) → LinkedIn Account
- **social_youtube** (Char) → Youtube Account
- **social_instagram** (Char) → Instagram Account
- **social_tiktok** (Char) → TikTok Account
- **social_default_image** (Binary)
- **has_social_default_image** (Boolean)
- **google_analytics_key** (Char) → Google Analytics Key
- **google_search_console** (Char)
- **google_maps_api_key** (Char) → Google Maps API Key
- **plausible_shared_key** (Char)
- **plausible_site** (Char)
- **user_id** (Many2one) → res.users
- **cdn_activated** (Boolean) → Content Delivery Network (CDN)
- **cdn_url** (Char) → CDN Base URL
- **cdn_filters** (Text) → CDN Filters
- **partner_id** (Many2one)
- **menu_id** (Many2one) → website.menu
- **homepage_url** (Char)
- **custom_code_head** (Html) → Custom `<head>` code
- **custom_code_footer** (Html) → Custom end of `<body>` code
- **robots_txt** (Html) → Robots.txt
- **favicon** (Binary)
- **theme_id** (Many2one) → ir.module.module
- **specific_user_account** (Boolean) → Specific User Account
- **auth_signup_uninvited** (Selection)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | website.form | `website.view_website_form` | - |
| list | website.list | `website.view_website_tree` | - |




### ir.actions.server


- Hereda de:

  - ir.actions.server




#### Campos
- **xml_id** (Char) → External ID
- **website_path** (Char) → Website Path
- **website_url** (Char) → Website Url
- **website_published** (Boolean) → Available on the Website





### res.lang


- Hereda de:

  - res.lang




- No agrega campos




### web_editor.assets


- Hereda de:

  - web_editor.assets




- No agrega campos




### website.configurator.feature


- Hereda de: Base



#### Campos
- **sequence** (Integer)
- **name** (Char)
- **description** (Char)
- **icon** (Char)
- **iap_page_code** (Char)
- **website_config_preselection** (Char)
- **page_view_id** (Many2one) → ir.ui.view
- **module_id** (Many2one) → ir.module.module
- **feature_url** (Char)
- **menu_sequence** (Integer)
- **menu_company** (Boolean)





### theme.ir.asset


- Hereda de: Base



#### Campos
- **key** (Char)
- **name** (Char)
- **bundle** (Char)
- **directive** (Selection)
- **path** (Char)
- **target** (Char)
- **active** (Boolean)
- **sequence** (Integer)
- **copy_ids** (One2many) → ir.asset





### theme.ir.ui.view


- Hereda de: Base



#### Campos
- **name** (Char)
- **key** (Char)
- **type** (Char)
- **priority** (Integer)
- **mode** (Selection)
- **active** (Boolean)
- **arch** (Text)
- **arch_fs** (Char)
- **inherit_id** (Reference)
- **copy_ids** (One2many) → ir.ui.view
- **customize_show** (Boolean)





### theme.ir.attachment


- Hereda de: Base



#### Campos
- **name** (Char)
- **key** (Char)
- **url** (Char)
- **copy_ids** (One2many) → ir.attachment





### theme.website.menu


- Hereda de: Base



#### Campos
- **name** (Char)
- **url** (Char)
- **page_id** (Many2one) → theme.website.page
- **new_window** (Boolean) → New Window
- **sequence** (Integer)
- **parent_id** (Many2one) → theme.website.menu
- **mega_menu_content** (Html)
- **mega_menu_classes** (Char)
- **use_main_menu_as_parent** (Boolean)
- **copy_ids** (One2many) → website.menu





### theme.website.page


- Hereda de: Base



#### Campos
- **url** (Char)
- **view_id** (Many2one) → theme.ir.ui.view
- **website_indexed** (Boolean) → Page Indexed
- **is_published** (Boolean)
- **is_new_page_template** (Boolean)
- **header_overlay** (Boolean)
- **header_color** (Char)
- **header_visible** (Boolean)
- **footer_visible** (Boolean)
- **copy_ids** (One2many) → website.page





### theme.utils


- Hereda de: Base



- No agrega campos




### ir.ui.view


- Hereda de:

  - ir.ui.view




#### Campos
- **theme_template_id** (Many2one) → theme.ir.ui.view





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | - | `website.view_view_tree_inherit_website` | base.view_view_tree |
| form | website.ir_ui_view.arch_only | `website.view_arch_only` | - |




### ir.asset


- Hereda de:

  - ir.asset




#### Campos
- **theme_template_id** (Many2one) → theme.ir.asset





### ir.attachment


- Hereda de:

  - ir.attachment




#### Campos
- **key** (Char)
- **theme_template_id** (Many2one) → theme.ir.attachment





### website.menu


- Hereda de:

  - website.menu




#### Campos
- **theme_template_id** (Many2one) → theme.website.menu





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | website.menu.form | `website.website_menus_form_view` | - |
| list | website.menu.list | `website.menu_tree` | - |
| search | website.menu.search | `website.menu_search` | - |



**Filtros de búsqueda (website.menu_search):**


*Agrupar por:*
- Name
- Url
- Website



### website.page


- Hereda de:

  - website.page




#### Campos
- **theme_template_id** (Many2one) → theme.website.page





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | website.page.form | `website.website_pages_form_view` | - |
| list | website.page.list | `website.website_pages_tree_view` | - |
| kanban | website.page.kanban | `website.website_pages_kanban_view` | - |
| search | website.page.view.search | `website.website_pages_view_search` | - |



**Filtros de búsqueda (website.website_pages_view_search):**

- **Published** (`[('website_published', '=', True)]`)
- **Not published** (`[('website_published', '=', False)]`)
- **Tracked** (`[('track', '=', True)]`)
- **Not tracked** (`[('track', '=', False)]`)



### ir.model.data


- Hereda de:

  - ir.model.data




- No agrega campos




### ir.ui.view


- Hereda de:


  - ir.ui.view

  - website.seo.metadata





#### Campos
- **website_id** (Many2one) → website
- **page_ids** (One2many) → website.page
- **controller_page_ids** (One2many) → website.controller.page
- **first_page_id** (Many2one) → website.page
- **track** (Boolean)
- **visibility** (Selection)
- **visibility_password** (Char)
- **visibility_password_display** (Char)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | - | `website.view_view_tree_inherit_website` | base.view_view_tree |
| form | website.ir_ui_view.arch_only | `website.view_arch_only` | - |




### website.menu


- Hereda de: Base



#### Campos
- **name** (Char) → Menu
- **url** (Char) → Url
- **page_id** (Many2one) → website.page
- **controller_page_id** (Many2one) → website.controller.page
- **new_window** (Boolean) → New Window
- **sequence** (Integer)
- **website_id** (Many2one) → website
- **parent_id** (Many2one) → website.menu
- **child_id** (One2many) → website.menu
- **parent_path** (Char)
- **is_visible** (Boolean)
- **group_ids** (Many2many) → res.groups
- **is_mega_menu** (Boolean)
- **mega_menu_content** (Html)
- **mega_menu_classes** (Char)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | website.menu.form | `website.website_menus_form_view` | - |
| list | website.menu.list | `website.menu_tree` | - |
| search | website.menu.search | `website.menu_search` | - |



**Filtros de búsqueda (website.menu_search):**


*Agrupar por:*
- Name
- Url
- Website



### website.page.properties.base


- Hereda de: Base



#### Campos
- **target_model_id** (Reference)
- **website_id** (Many2one) → website
- **menu_ids** (One2many) → website.menu
- **is_in_menu** (Boolean)
- **url** (Char)
- **is_homepage** (Boolean)
- **can_publish** (Boolean)
- **is_published** (Boolean)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | website.page.properties.base.form.view | `website.website_page_properties_base_view_form` | - |



**Botones (website.website_page_properties_base_view_form):**
- **Edit Menu** (action)



### website.page.properties


- Hereda de:


  - website.page.properties.base





#### Campos
- **target_model_id** (Many2one) → website.page
- **name** (Char)
- **url** (Char)
- **date_publish** (Datetime)
- **website_indexed** (Boolean)
- **visibility** (Selection)
- **visibility_password_display** (Char)
- **groups_id** (Many2many)
- **is_new_page_template** (Boolean)
- **old_url** (Char)
- **redirect_old_url** (Boolean)
- **redirect_type** (Selection)





### website.controller.page


- Hereda de:


  - website.published.multi.mixin

  - website.searchable.mixin





#### Campos
- **view_id** (Many2one) → ir.ui.view
- **record_view_id** (Many2one) → ir.ui.view
- **menu_ids** (One2many) → website.menu
- **website_id** (Many2one)
- **name** (Char)
- **name_slugified** (Char)
- **url_demo** (Char)
- **record_domain** (Char)
- **default_layout** (Selection)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | website.controller.page.form | `website.website_controller_pages_form_view` | - |
| list | website.controller.page.list | `website.website_controller_pages_tree_view` | - |
| kanban | website.controller.page.kanban | `website.website_controller_pages_kanban_view` | - |
| search | website.controller.page.search | `website.website_controller_pages_search_view` | - |



**Filtros de búsqueda (website.website_controller_pages_search_view):**


*Agrupar por:*
- Model
- Website



### ir.rule


- Hereda de:

  - ir.rule




- No agrega campos




### ir.binary


- Hereda de:

  - ir.binary




- No agrega campos




### base


- Hereda de:

  - base




- No agrega campos




### website.seo.metadata


- Hereda de: Base



#### Campos
- **is_seo_optimized** (Boolean) → SEO optimized
- **website_meta_title** (Char) → Website meta title
- **website_meta_description** (Text) → Website meta description
- **website_meta_keywords** (Char) → Website meta keywords
- **website_meta_og_img** (Char) → Website opengraph image
- **seo_name** (Char) → Seo name





### website.cover_properties.mixin


- Hereda de: Base



#### Campos
- **cover_properties** (Text) → Cover Properties





### website.multi.mixin


- Hereda de: Base



#### Campos
- **website_id** (Many2one) → website





### website.published.mixin


- Hereda de: Base



#### Campos
- **website_published** (Boolean) → Visible on current website
- **is_published** (Boolean) → Is Published
- **can_publish** (Boolean) → Can Publish
- **website_url** (Char) → Website URL





### website.published.multi.mixin


- Hereda de:


  - website.published.mixin

  - website.multi.mixin





#### Campos
- **website_published** (Boolean)





### website.searchable.mixin


- Hereda de: Base



- No agrega campos




### website


- Hereda de:

  - website




- No agrega campos




#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | website.form | `website.view_website_form` | - |
| list | website.list | `website.view_website_tree` | - |




### ir.model


- Hereda de:

  - ir.model




#### Campos
- **website_form_access** (Boolean) → Allowed to use in forms
- **website_form_default_field_id** (Many2one) → ir.model.fields
- **website_form_label** (Char) → Label for form action
- **website_form_key** (Char)





### ir.model.fields


- Hereda de:

  - ir.model.fields




#### Campos
- **website_form_blacklisted** (Boolean) → Blacklisted in web forms





### ir.asset


- Hereda de:

  - ir.asset




#### Campos
- **key** (Char)
- **website_id** (Many2one) → website





### website.snippet.filter


- Hereda de:


  - website.published.multi.mixin





#### Campos
- **name** (Char)
- **action_server_id** (Many2one) → ir.actions.server
- **field_names** (Char)
- **filter_id** (Many2one) → ir.filters
- **limit** (Integer)
- **website_id** (Many2one) → website
- **model_name** (Char)





### res.users


- Hereda de:

  - res.users




#### Campos
- **website_id** (Many2one) → website





### ir.attachment


- Hereda de:

  - ir.attachment




#### Campos
- **key** (Char)
- **website_id** (Many2one) → website





### res.config.settings


- Hereda de:

  - res.config.settings




#### Campos
- **website_id** (Many2one) → website
- **website_name** (Char) → Website Name
- **website_domain** (Char) → Website Domain
- **website_homepage_url** (Char)
- **website_company_id** (Many2one)
- **website_logo** (Binary)
- **language_ids** (Many2many)
- **website_language_count** (Integer)
- **website_default_lang_id** (Many2one)
- **website_default_lang_code** (Char) → Default language code
- **shared_user_account** (Boolean)
- **website_cookies_bar** (Boolean)
- **website_block_third_party_domains** (Boolean) → Block 3rd-party domains
- **google_analytics_key** (Char) → Google Analytics Key
- **google_search_console** (Char) → Google Search Console Key
- **plausible_shared_key** (Char) → Plausible auth Key
- **plausible_site** (Char) → Plausible Site (e.g. domain.com)
- **cdn_activated** (Boolean)
- **cdn_url** (Char)
- **cdn_filters** (Text)
- **auth_signup_uninvited** (Selection)
- **favicon** (Binary) → Favicon
- **social_default_image** (Binary) → Default Social Share Image
- **group_multi_website** (Boolean) → Multi-website
- **has_google_analytics** (Boolean) → Google Analytics
- **has_google_search_console** (Boolean) → Google Search Console
- **has_default_share_image** (Boolean) → Use a image by default for sharing
- **has_plausible_shared_key** (Boolean) → Plausible Analytics
- **module_website_livechat** (Boolean)
- **module_marketing_automation** (Boolean)





### website.route


- Hereda de: Base



#### Campos
- **path** (Char) → Route





### website.rewrite


- Hereda de: Base



#### Campos
- **name** (Char) → Name
- **website_id** (Many2one) → website
- **active** (Boolean)
- **url_from** (Char) → URL from
- **route_id** (Many2one) → website.route
- **url_to** (Char) → URL to
- **redirect_type** (Selection)
- **sequence** (Integer)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | - | `website.view_website_rewrite_form` | - |
| list | website.rewrite.list | `website.action_website_rewrite_tree` | - |
| search | website.rewrite.search | `website.view_rewrite_search` | - |



**Botones (website.view_website_rewrite_form):**
- **Refresh route's list** (object)


**Filtros de búsqueda (website.view_rewrite_search):**

- **404 Not Found** (`[('redirect_type', '=', '404')]`)
- **301 Moved permanently** (`[('redirect_type', '=', '301')]`)
- **302 Moved temporarily** (`[('redirect_type', '=', '302')]`)
- **308 Redirect / Rewrite** (`[('redirect_type', '=', '308')]`)
- **Archived** (`[('active', '=', False)]`)


*Agrupar por:*
- Redirection Type
- Created by



### ir.ui.menu


- Hereda de:

  - ir.ui.menu




- No agrega campos




### res.company


- Hereda de:

  - res.company




#### Campos
- **website_id** (Many2one) → website





### ir.http


- Hereda de:

  - ir.http




- No agrega campos




### website.page


- Hereda de:


  - website.published.multi.mixin

  - website.searchable.mixin





#### Campos
- **url** (Char) → Page URL
- **view_id** (Many2one) → ir.ui.view
- **website_indexed** (Boolean) → Is Indexed
- **date_publish** (Datetime) → Publishing Date
- **menu_ids** (One2many) → website.menu
- **is_in_menu** (Boolean)
- **is_homepage** (Boolean)
- **is_visible** (Boolean)
- **is_new_page_template** (Boolean)
- **header_overlay** (Boolean)
- **header_color** (Char)
- **header_text_color** (Char)
- **header_visible** (Boolean)
- **footer_visible** (Boolean)
- **website_id** (Many2one)
- **arch** (Text)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | website.page.form | `website.website_pages_form_view` | - |
| list | website.page.list | `website.website_pages_tree_view` | - |
| kanban | website.page.kanban | `website.website_pages_kanban_view` | - |
| search | website.page.view.search | `website.website_pages_view_search` | - |



**Filtros de búsqueda (website.website_pages_view_search):**

- **Published** (`[('website_published', '=', True)]`)
- **Not published** (`[('website_published', '=', False)]`)
- **Tracked** (`[('track', '=', True)]`)
- **Not tracked** (`[('track', '=', False)]`)



### ir.qweb.field.contact


- Hereda de:

  - ir.qweb.field.contact




- No agrega campos




### ir.qweb.field.html


- Hereda de:

  - ir.qweb.field.html




- No agrega campos




### ir.qweb


- Hereda de:

  - ir.qweb




- No agrega campos




### res.partner


- Hereda de:


  - res.partner

  - website.published.multi.mixin





#### Campos
- **visitor_ids** (One2many) → website.visitor





### ir.module.module


- Hereda de: Base



#### Campos
- **image_ids** (One2many) → ir.attachment
- **is_installed_on_current_website** (Boolean)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| kanban | Themes Kanban | `website.theme_view_kanban` | - |
| search | Themes Search | `website.theme_view_search` | - |
| form | website.form | `website.theme_view_form_preview` | - |



**Filtros de búsqueda (website.theme_view_search):**


*Agrupar por:*
- Author
- Category



### website.track


- Hereda de: Base



#### Campos
- **visitor_id** (Many2one) → website.visitor
- **page_id** (Many2one) → website.page
- **url** (Text) → Url
- **visit_datetime** (Datetime) → Visit Date





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | website.track.view.list | `website.website_visitor_page_view_tree` | - |
| graph | website.track.view.graph | `website.website_visitor_page_view_graph` | - |
| search | website.track.view.search | `website.website_visitor_page_view_search` | - |
| list | website.track.view.list | `website.website_visitor_track_view_tree` | - |
| graph | website.track.view.graph | `website.website_visitor_track_view_graph` | - |



**Filtros de búsqueda (website.website_visitor_page_view_search):**

- **Pages** (`[('page_id', '!=', False)]`)
- **Urls & Pages** (`[('url', '!=', False)]`)


*Agrupar por:*
- Visitor
- Page
- Url
- Date



### website.visitor


- Hereda de: Base



#### Campos
- **name** (Char) → Name
- **access_token** (Char)
- **website_id** (Many2one) → website
- **partner_id** (Many2one) → res.partner
- **partner_image** (Binary)
- **country_id** (Many2one) → res.country
- **country_flag** (Char)
- **lang_id** (Many2one) → res.lang
- **timezone** (Selection)
- **email** (Char)
- **mobile** (Char)
- **visit_count** (Integer) → # Visits
- **website_track_ids** (One2many) → website.track
- **visitor_page_count** (Integer) → Page Views
- **page_ids** (Many2many) → website.page
- **page_count** (Integer) → # Visited Pages
- **last_visited_page_id** (Many2one) → website.page
- **create_date** (Datetime) → First Connection
- **last_connection_datetime** (Datetime) → Last Connection
- **time_since_last_action** (Char) → Last action
- **is_connected** (Boolean) → Is connected?





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| kanban | website.visitor.view.kanban | `website.website_visitor_view_kanban` | - |
| form | website.visitor.view.form | `website.website_visitor_view_form` | - |
| list | website.visitor.view.list | `website.website_visitor_view_tree` | - |
| search | website.visitor.view.search | `website.website_visitor_view_search` | - |
| graph | website.visitor.view.graph | `website.website_visitor_view_graph` | - |



**Botones (website.website_visitor_view_form):**
- **Send Email** (object)
- **%(website.website_visitor_page_action)d** (action)


**Filtros de búsqueda (website.website_visitor_view_search):**

- **Last 7 Days** (`[('last_connection_datetime', '>', datetime.datetime.now() - datetime.timedelta(days=7))]`)
- **Unregistered** (`[('partner_id', '=', False)]`)
- **Contacts** (`[('partner_id', '!=', False)]`)
- **Connected** (`[('last_connection_datetime', '>', datetime.datetime.now() - datetime.timedelta(minutes=5))]`)


*Agrupar por:*
- Country
- Timezone
- Language
- # Visits
- Website
- First Connection
- Last Connection



### base.partner.merge.automatic.wizard


- Hereda de:

  - base.partner.merge.automatic.wizard




- No agrega campos









## Vistas Adicionales


### website.custom_blocked_third_party_domains

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | Block 3rd-party service domains | `website.view_edit_third_party_domains` | - |



**Botones (website.view_edit_third_party_domains):**
- **Save** (object)


### website.robots

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | Edit Robots.txt | `website.view_edit_robots` | - |



**Botones (website.view_edit_robots):**
- **Save** (object)



