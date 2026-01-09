# Módulo: eCommerce

## Información General
- **Nombre técnico:** website_sale
- **Versión:** 1.1
- **Categoría:** Website/Website
- **Dependencias:** website, sale, website_payment, website_mail, portal_rating, digest, delivery


## Propósito
Sell your products online





## Modelos

### website


- Hereda de:

  - website




#### Campos
- **enabled_portal_reorder_button** (Boolean)
- **salesperson_id** (Many2one) → res.users
- **salesteam_id** (Many2one) → crm.team
- **show_line_subtotals_tax_selection** (Selection)
- **add_to_cart_action** (Selection)
- **auth_signup_uninvited** (Selection)
- **account_on_checkout** (Selection)
- **cart_recovery_mail_template_id** (Many2one) → mail.template
- **contact_us_button_url** (Char)
- **cart_abandoned_delay** (Float)
- **send_abandoned_cart_email** (Boolean)
- **shop_ppg** (Integer)
- **shop_ppr** (Integer)
- **shop_gap** (Char)
- **shop_default_sort** (Selection)
- **shop_extra_field_ids** (One2many) → website.sale.extra.field
- **product_page_image_layout** (Selection)
- **product_page_image_width** (Selection)
- **product_page_image_spacing** (Selection)
- **ecommerce_access** (Selection)
- **product_page_grid_columns** (Integer)
- **prevent_zero_price_sale** (Boolean)
- **prevent_zero_price_sale_text** (Char)
- **fiscal_position_id** (Many2one) → account.fiscal.position
- **pricelist_id** (Many2one) → product.pricelist
- **currency_id** (Many2one) → res.currency
- **pricelist_ids** (One2many) → product.pricelist
- **all_pricelist_ids** (One2many) → product.pricelist





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | website_sale.website.form | `website_sale.view_website_sale_website_form` | website.view_website_form |




### product.pricelist.item


- Hereda de:

  - product.pricelist.item




- No agrega campos




### payment.token


- Hereda de:

  - payment.token




- No agrega campos




### delivery.carrier


- Hereda de:


  - delivery.carrier

  - website.published.multi.mixin





#### Campos
- **website_description** (Text)





### sale.order


- Hereda de:

  - sale.order




#### Campos
- **website_id** (Many2one) → website
- **cart_recovery_email_sent** (Boolean)
- **shop_warning** (Char)
- **website_order_line** (One2many) → sale.order.line
- **amount_delivery** (Monetary)
- **cart_quantity** (Integer)
- **only_services** (Boolean)
- **is_abandoned_cart** (Boolean)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| search | sale.order.ecommerce.abondand.view | `website_sale.view_sales_order_filter_ecommerce_abondand` | - |



**Filtros de búsqueda (website_sale.view_sales_order_filter_ecommerce_abondand):**

- **Creation Date**
- **Recovery Email to Send** (`[('cart_recovery_email_sent', '=', False)]`)
- **Recovery Email Sent** (`[('cart_recovery_email_sent', '=', True)]`)
- **Last Week** (`[('date_order','>', (context_today() - datetime.timedelta(days=7)).strftime('%Y-%m-%d'))]`)
- **Last Month** (`[('date_order','>', (context_today() - datetime.timedelta(days=30)).strftime('%Y-%m-%d'))]`)
- **Last Year** (`[('date_order','>', (context_today() - datetime.timedelta(days=365)).strftime('%Y-%m-%d'))]`)


*Agrupar por:*
- Order Date



### product.document


- Hereda de:

  - product.document




#### Campos
- **shown_on_product_page** (Boolean)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| search | product.document.search.sale | `website_sale.product_document_search` | sale.product_document_search |



**Filtros de búsqueda (website_sale.product_document_search):**

- **Show on Ecommerce** (`[('shown_on_product_page', '=', True)]`)



### product.tag


- Hereda de:


  - website.multi.mixin

  - product.tag





#### Campos
- **visible_on_ecommerce** (Boolean)
- **image** (Image)





### website.menu


- Hereda de:

  - website.menu




- No agrega campos




### product.product


- Hereda de:

  - product.product




#### Campos
- **variant_ribbon_id** (Many2one) → product.ribbon
- **website_id** (Many2one)
- **product_variant_image_ids** (One2many) → product.image
- **base_unit_count** (Float)
- **base_unit_id** (Many2one) → website.base.unit
- **base_unit_price** (Monetary)
- **base_unit_name** (Char)
- **website_url** (Char)





### product.ribbon


- Hereda de: Base



#### Campos
- **name** (Char)
- **bg_color** (Char)
- **text_color** (Char)
- **position** (Selection)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | product.ribbon.form.view | `website_sale.product_ribbon_form_view` | - |
| list | product.ribbon.list | `website_sale.product_ribbon_view_tree` | - |




### sale.order.line


- Hereda de:

  - sale.order.line




#### Campos
- **name_short** (Char)
- **shop_warning** (Char)





### product.template


- Hereda de:


  - rating.mixin

  - product.template

  - website.seo.metadata

  - website.published.multi.mixin

  - website.searchable.mixin





#### Campos
- **website_description** (Html)
- **description_ecommerce** (Html)
- **alternative_product_ids** (Many2many) → product.template
- **accessory_product_ids** (Many2many) → product.product
- **website_size_x** (Integer)
- **website_size_y** (Integer)
- **website_ribbon_id** (Many2one) → product.ribbon
- **website_sequence** (Integer)
- **public_categ_ids** (Many2many) → product.public.category
- **product_template_image_ids** (One2many) → product.image
- **base_unit_count** (Float)
- **base_unit_id** (Many2one) → website.base.unit
- **base_unit_price** (Monetary)
- **base_unit_name** (Char)
- **compare_list_price** (Monetary)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | product.template.view.list.website_sale | `website_sale.product_template_view_tree_website_sale` | website_sale.product_template_view_tree |
| kanban | product.template.view.kanban.website_sale | `website_sale.product_template_view_kanban_website_sale` | product.product_template_kanban_view |
| kanban | Product Pages Kanban | `website_sale.product_pages_kanban_view` | product_template_view_kanban_website_sale |




### website.track


- Hereda de:

  - website.track




#### Campos
- **product_id** (Many2one) → product.product





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | website.track.view.list | `website_sale.website_sale_visitor_page_view_tree` | - |
| graph | website.track.view.graph | `website_sale.website_sale_visitor_page_view_graph` | - |




### digest.digest


- Hereda de:

  - digest.digest




#### Campos
- **kpi_website_sale_total** (Boolean)
- **kpi_website_sale_total_value** (Monetary)





### account.move


- Hereda de:

  - account.move




#### Campos
- **website_id** (Many2one) → website





### website.sale.extra.field


- Hereda de: Base



#### Campos
- **website_id** (Many2one) → website
- **sequence** (Integer)
- **field_id** (Many2one) → ir.model.fields
- **label** (Char)
- **name** (Char)





### product.template.attribute.line


- Hereda de:

  - product.template.attribute.line




- No agrega campos




### website.snippet.filter


- Hereda de:

  - website.snippet.filter




#### Campos
- **product_cross_selling** (Boolean)





### product.attribute


- Hereda de:

  - product.attribute




#### Campos
- **visibility** (Selection)





### res.config.settings


- Hereda de:

  - res.config.settings




#### Campos
- **group_delivery_invoice_address** (Boolean)
- **group_show_uom_price** (Boolean)
- **group_product_price_comparison** (Boolean)
- **module_account** (Boolean) → Invoicing
- **module_delivery_mondialrelay** (Boolean) → Mondial Relay Connector
- **module_website_sale_autocomplete** (Boolean) → Address Autocomplete
- **module_website_sale_comparison** (Boolean) → Product Comparison Tool
- **module_website_sale_collect** (Boolean) → Click & Collect
- **module_website_sale_wishlist** (Boolean) → Wishlists
- **add_to_cart_action** (Selection)
- **cart_recovery_mail_template** (Many2one)
- **cart_abandoned_delay** (Float)
- **send_abandoned_cart_email** (Boolean)
- **salesperson_id** (Many2one)
- **salesteam_id** (Many2one)
- **website_sale_prevent_zero_price_sale** (Boolean)
- **website_sale_contact_us_button_url** (Char)
- **website_sale_enabled_portal_reorder_button** (Boolean)
- **show_line_subtotals_tax_selection** (Selection)
- **account_on_checkout** (Selection)
- **ecommerce_access** (Selection)
- **enabled_extra_checkout_step** (Boolean)
- **enabled_buy_now_button** (Boolean)





### website.base.unit


- Hereda de: Base



#### Campos
- **name** (Char)





### crm.team


- Hereda de:

  - crm.team




#### Campos
- **website_ids** (One2many) → website
- **abandoned_carts_amount** (Integer)
- **abandoned_carts_count** (Integer)





### product.pricelist


- Hereda de:

  - product.pricelist




#### Campos
- **website_id** (Many2one) → website
- **code** (Char)
- **selectable** (Boolean)





### res.company


- Hereda de:

  - res.company




- No agrega campos




### ir.http


- Hereda de:

  - ir.http




- No agrega campos




### res.partner


- Hereda de:

  - res.partner




#### Campos
- **last_website_so_id** (Many2one) → sale.order





### product.template.attribute.value


- Hereda de:

  - product.template.attribute.value




- No agrega campos




### product.public.category


- Hereda de:


  - website.seo.metadata

  - website.multi.mixin

  - website.searchable.mixin

  - image.mixin





#### Campos
- **name** (Char)
- **sequence** (Integer)
- **parent_id** (Many2one) → product.public.category
- **child_id** (One2many) → product.public.category
- **parent_path** (Char)
- **parents_and_self** (Many2many) → product.public.category
- **product_tmpl_ids** (Many2many) → product.template
- **website_description** (Html)
- **website_footer** (Html)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | product.public.category.form | `website_sale.product_public_category_form_view` | - |
| list | product.public.category.list | `website_sale.product_public_category_tree_view` | - |




### website.visitor


- Hereda de:

  - website.visitor




#### Campos
- **visitor_product_count** (Integer)
- **product_ids** (Many2many) → product.product
- **product_count** (Integer)





### product.image


- Hereda de:


  - image.mixin





#### Campos
- **name** (Char)
- **sequence** (Integer)
- **image_1920** (Image)
- **product_tmpl_id** (Many2one) → product.template
- **product_variant_id** (Many2one) → product.product
- **video_url** (Char)
- **embed_code** (Html)
- **can_image_1024_be_zoomed** (Boolean)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | product.image.view.form | `website_sale.view_product_image_form` | - |
| kanban | product.image.view.kanban | `website_sale.product_image_view_kanban` | - |









## Vistas Adicionales


### sale.report

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| search | sale.report.search | `website_sale.sale_report_view_search_website` | - |
| pivot | sale.report.view.pivot.website | `website_sale.sale_report_view_pivot_website` | - |
| graph | sale.report.view.graph.website | `website_sale.sale_report_view_graph_website` | - |



**Filtros de búsqueda (website_sale.sale_report_view_search_website):**

- **Confirmed Orders** (`[('state', '=', 'sale')]`)
- **filter_date**
- **Last Week** (`[('date','>=', (context_today() - datetime.timedelta(days=7)).strftime('%Y-%m-%d'))]`)
- **Last Month** (`[('date','>=', (context_today() - datetime.timedelta(days=30)).strftime('%Y-%m-%d'))]`)
- **Last Year** (`[('date','>=', (context_today() - datetime.timedelta(days=365)).strftime('%Y-%m-%d'))]`)


*Agrupar por:*
- Website
- Product
- Product Category
- Customer
- Customer Country
- Status
- Order Date



