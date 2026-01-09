# Módulo: Products & Pricelists

## Información General
- **Nombre técnico:** product
- **Versión:** 1.2
- **Categoría:** Sales/Sales
- **Dependencias:** base, mail, uom




## Descripción

This is the base module for managing products and pricelists in Odoo.

Products support variants, different pricing methods, vendors information,
make to stock/order, different units of measure, packaging and properties.

Pricelists support:
-------------------
    * Multiple-level of discount (by product, category, quantities)
    * Compute price based on different criteria:
        * Other pricelist
        * Cost price
        * List price
        * Vendor price

Pricelists preferences by product and/or partners.

Print product labels with barcode.
    



## Modelos

### uom.uom


- Hereda de:

  - uom.uom




- No agrega campos



### res.currency


- Hereda de:

  - res.currency




- No agrega campos



### product.pricelist.item


- Hereda de: Base



- Campos:

  - **pricelist_id** (Many2one) → product.pricelist


  - **company_id** (Many2one)


  - **currency_id** (Many2one)


  - **date_start** (Datetime)


  - **date_end** (Datetime)


  - **min_quantity** (Float)


  - **applied_on** (Selection)


  - **display_applied_on** (Selection)


  - **categ_id** (Many2one) → product.category


  - **product_tmpl_id** (Many2one) → product.template


  - **product_id** (Many2one) → product.product


  - **product_uom** (Char)


  - **product_variant_count** (Integer)


  - **base** (Selection)


  - **base_pricelist_id** (Many2one) → product.pricelist


  - **compute_price** (Selection)


  - **fixed_price** (Float)


  - **percent_price** (Float)


  - **price_discount** (Float)


  - **price_round** (Float)


  - **price_surcharge** (Float)


  - **price_markup** (Float)


  - **price_min_margin** (Float)


  - **price_max_margin** (Float)


  - **name** (Char)


  - **price** (Char)


  - **rule_tip** (Char)





### product.combo


- Hereda de: Base



- Campos:

  - **name** (Char)


  - **sequence** (Integer)


  - **company_id** (Many2one) → res.company


  - **combo_item_ids** (One2many) → product.combo.item


  - **combo_item_count** (Integer)


  - **currency_id** (Many2one) → res.currency


  - **base_price** (Float)





### product.packaging


- Hereda de: Base



- Campos:

  - **name** (Char) → Product Packaging


  - **sequence** (Integer) → Sequence


  - **product_id** (Many2one) → product.product


  - **qty** (Float) → Contained Quantity


  - **barcode** (Char) → Barcode


  - **product_uom_id** (Many2one) → uom.uom


  - **company_id** (Many2one) → res.company





### product.document


- Hereda de: Base



- Campos:

  - **ir_attachment_id** (Many2one) → ir.attachment


  - **active** (Boolean)


  - **sequence** (Integer)





### product.tag


- Hereda de: Base



- Campos:

  - **name** (Char)


  - **sequence** (Integer)


  - **color** (Char)


  - **product_template_ids** (Many2many) → product.template


  - **product_product_ids** (Many2many) → product.product


  - **product_ids** (Many2many) → product.product





### product.product


- Hereda de:


  - mail.thread

  - mail.activity.mixin





- Campos:

  - **price_extra** (Float) → Variant Price Extra


  - **lst_price** (Float) → Sales Price


  - **default_code** (Char) → Internal Reference


  - **code** (Char) → Reference


  - **partner_ref** (Char) → Customer Ref


  - **active** (Boolean) → Active


  - **product_tmpl_id** (Many2one) → product.template


  - **barcode** (Char) → Barcode


  - **product_template_attribute_value_ids** (Many2many) → product.template.attribute.value


  - **product_template_variant_value_ids** (Many2many) → product.template.attribute.value


  - **combination_indices** (Char)


  - **is_product_variant** (Boolean)


  - **standard_price** (Float) → Cost


  - **volume** (Float) → Volume


  - **weight** (Float) → Weight


  - **pricelist_item_count** (Integer) → Number of price rules


  - **product_document_ids** (One2many) → product.document


  - **product_document_count** (Integer)


  - **packaging_ids** (One2many) → product.packaging


  - **additional_product_tag_ids** (Many2many) → product.tag


  - **all_product_tag_ids** (Many2many) → product.tag


  - **image_variant_1920** (Image) → Variant Image


  - **image_variant_1024** (Image) → Variant Image 1024


  - **image_variant_512** (Image) → Variant Image 512


  - **image_variant_256** (Image) → Variant Image 256


  - **image_variant_128** (Image) → Variant Image 128


  - **can_image_variant_1024_be_zoomed** (Boolean) → Can Variant Image 1024 be zoomed


  - **image_1920** (Image) → Image


  - **image_1024** (Image) → Image 1024


  - **image_512** (Image) → Image 512


  - **image_256** (Image) → Image 256


  - **image_128** (Image) → Image 128


  - **can_image_1024_be_zoomed** (Boolean) → Can Image 1024 be zoomed


  - **write_date** (Datetime)





### product.template


- Hereda de:


  - mail.thread

  - mail.activity.mixin

  - image.mixin





- Campos:

  - **name** (Char) → Name


  - **sequence** (Integer) → Sequence


  - **description** (Html) → Description


  - **description_purchase** (Text) → Purchase Description


  - **description_sale** (Text) → Sales Description


  - **type** (Selection)


  - **combo_ids** (Many2many) → product.combo


  - **service_tracking** (Selection)


  - **categ_id** (Many2one) → product.category


  - **currency_id** (Many2one) → res.currency


  - **cost_currency_id** (Many2one) → res.currency


  - **list_price** (Float) → Sales Price


  - **standard_price** (Float) → Cost


  - **volume** (Float) → Volume


  - **volume_uom_name** (Char)


  - **weight** (Float) → Weight


  - **weight_uom_name** (Char)


  - **sale_ok** (Boolean) → Sales


  - **purchase_ok** (Boolean) → Purchase


  - **uom_id** (Many2one) → uom.uom


  - **uom_name** (Char)


  - **uom_category_id** (Many2one) → uom.category


  - **uom_po_id** (Many2one) → uom.uom


  - **company_id** (Many2one) → res.company


  - **packaging_ids** (One2many) → product.packaging


  - **seller_ids** (One2many) → product.supplierinfo


  - **variant_seller_ids** (One2many) → product.supplierinfo


  - **active** (Boolean) → Active


  - **color** (Integer) → Color Index


  - **is_product_variant** (Boolean)


  - **attribute_line_ids** (One2many) → product.template.attribute.line


  - **valid_product_template_attribute_line_ids** (Many2many) → product.template.attribute.line


  - **product_variant_ids** (One2many) → product.product


  - **product_variant_id** (Many2one) → product.product


  - **product_variant_count** (Integer) → # Product Variants


  - **barcode** (Char) → Barcode


  - **default_code** (Char) → Internal Reference


  - **pricelist_item_count** (Integer) → Number of price rules


  - **product_document_ids** (One2many) → product.document


  - **product_document_count** (Integer)


  - **can_image_1024_be_zoomed** (Boolean) → Can Image 1024 be zoomed


  - **has_configurable_attributes** (Boolean) → Is a configurable product


  - **product_tooltip** (Char)


  - **is_favorite** (Boolean)


  - **product_tag_ids** (Many2many) → product.tag


  - **product_properties** (Properties) → Properties





### product.attribute.value


- Hereda de: Base



- Campos:

  - **name** (Char)


  - **sequence** (Integer)


  - **attribute_id** (Many2one) → product.attribute


  - **pav_attribute_line_ids** (Many2many) → product.template.attribute.line


  - **default_extra_price** (Float)


  - **is_custom** (Boolean)


  - **html_color** (Char)


  - **display_type** (Selection)


  - **color** (Integer)


  - **image** (Image)


  - **active** (Boolean)


  - **is_used_on_products** (Boolean)


  - **default_extra_price_changed** (Boolean)





### product.combo.item


- Hereda de: Base



- Campos:

  - **company_id** (Many2one)


  - **combo_id** (Many2one) → product.combo


  - **product_id** (Many2one) → product.product


  - **currency_id** (Many2one) → res.currency


  - **lst_price** (Float)


  - **extra_price** (Float)





### product.catalog.mixin


- Hereda de: Base



- No agrega campos



### product.template.attribute.exclusion


- Hereda de: Base



- Campos:

  - **product_template_attribute_value_id** (Many2one) → product.template.attribute.value


  - **product_tmpl_id** (Many2one) → product.template


  - **value_ids** (Many2many) → product.template.attribute.value





### product.category


- Hereda de:


  - mail.thread





- Campos:

  - **name** (Char) → Name


  - **complete_name** (Char) → Complete Name


  - **parent_id** (Many2one) → product.category


  - **parent_path** (Char)


  - **child_id** (One2many) → product.category


  - **product_count** (Integer) → # Products


  - **product_properties_definition** (PropertiesDefinition) → Product Properties





### product.template.attribute.line


- Hereda de: Base



- Campos:

  - **active** (Boolean)


  - **product_tmpl_id** (Many2one) → product.template


  - **sequence** (Integer) → Sequence


  - **attribute_id** (Many2one) → product.attribute


  - **value_ids** (Many2many) → product.attribute.value


  - **value_count** (Integer)


  - **product_template_value_ids** (One2many) → product.template.attribute.value





### product.attribute.custom.value


- Hereda de: Base



- Campos:

  - **name** (Char)


  - **custom_product_template_attribute_value_id** (Many2one) → product.template.attribute.value


  - **custom_value** (Char)





### product.attribute


- Hereda de: Base



- Campos:

  - **name** (Char)


  - **active** (Boolean)


  - **create_variant** (Selection)


  - **display_type** (Selection)


  - **sequence** (Integer)


  - **value_ids** (One2many) → product.attribute.value


  - **template_value_ids** (One2many) → product.template.attribute.value


  - **attribute_line_ids** (One2many) → product.template.attribute.line


  - **product_tmpl_ids** (Many2many) → product.template


  - **number_related_products** (Integer)





### ir.attachment


- Hereda de:

  - ir.attachment




- No agrega campos



### res.config.settings


- Hereda de:

  - res.config.settings




- Campos:

  - **group_uom** (Boolean) → Units of Measure


  - **group_product_variant** (Boolean) → Variants


  - **module_loyalty** (Boolean) → Promotions, Coupons, Gift Card & Loyalty Program


  - **group_stock_packaging** (Boolean) → Product Packagings


  - **group_product_pricelist** (Boolean) → Pricelists


  - **product_weight_in_lbs** (Selection)


  - **product_volume_volume_in_cubic_feet** (Selection)





### product.supplierinfo


- Hereda de: Base



- Campos:

  - **partner_id** (Many2one) → res.partner


  - **product_name** (Char) → Vendor Product Name


  - **product_code** (Char) → Vendor Product Code


  - **sequence** (Integer) → Sequence


  - **product_uom** (Many2one) → uom.uom


  - **min_qty** (Float) → Quantity


  - **price** (Float) → Price


  - **price_discounted** (Float) → Discounted Price


  - **company_id** (Many2one) → res.company


  - **currency_id** (Many2one) → res.currency


  - **date_start** (Date) → Start Date


  - **date_end** (Date) → End Date


  - **product_id** (Many2one) → product.product


  - **product_tmpl_id** (Many2one) → product.template


  - **product_variant_count** (Integer) → Variant Count


  - **delay** (Integer) → Delivery Lead Time


  - **discount** (Float)





### product.pricelist


- Hereda de:


  - mail.thread

  - mail.activity.mixin





- Campos:

  - **name** (Char)


  - **active** (Boolean)


  - **sequence** (Integer)


  - **currency_id** (Many2one) → res.currency


  - **company_id** (Many2one) → res.company


  - **country_group_ids** (Many2many) → res.country.group


  - **item_ids** (One2many) → product.pricelist.item





### res.company


- Hereda de:

  - res.company




- No agrega campos



### res.country.group


- Hereda de:

  - res.country.group




- Campos:

  - **pricelist_ids** (Many2many) → product.pricelist





### res.partner


- Hereda de:

  - res.partner




- Campos:

  - **property_product_pricelist** (Many2one) → product.pricelist


  - **specific_property_product_pricelist** (Many2one) → product.pricelist





### product.template.attribute.value


- Hereda de: Base



- Campos:

  - **ptav_active** (Boolean)


  - **name** (Char)


  - **product_attribute_value_id** (Many2one) → product.attribute.value


  - **attribute_line_id** (Many2one) → product.template.attribute.line


  - **price_extra** (Float)


  - **currency_id** (Many2one)


  - **exclude_for** (One2many) → product.template.attribute.exclusion


  - **product_tmpl_id** (Many2one)


  - **attribute_id** (Many2one)


  - **ptav_product_variant_ids** (Many2many) → product.product


  - **html_color** (Char)


  - **is_custom** (Boolean)


  - **display_type** (Selection)


  - **color** (Integer)


  - **image** (Image)





### decimal.precision


- Hereda de:

  - decimal.precision




- No agrega campos






## Vistas


### product.template

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | product.template.common.form | `product.product_template_form_view` | - |
| search | product.template.search | `product.product_template_search_view` | - |
| list | product.template.view.list.tag | `product.product_template_view_tree_tag` | - |
| list | product.template.product.list | `product.product_template_tree_view` | - |
| list | product.template.product.form | `product.product_template_only_form_view` | product.product_template_form_view |
| kanban | Product.template.product.kanban | `product.product_template_kanban_view` | - |
| activity | product.template.activity | `product.product_template_view_activity` | - |



#### Botones (product.product_template_form_view)
- **Print Labels** (object)
- **open_pricelist_rules** (object) - Grupos: `product.group_product_pricelist`
- **action_open_documents** (object)


#### Filtros de búsqueda (product.product_template_search_view)

**Filtros:**
- **Services** (`[('type','=','service')]`)
- **Goods** (`[('type', '=', 'consu')]`)
- **Combo** (`[('type', '=', 'combo')]`)
- **Sales** (`[('sale_ok','=',True)]`)
- **Purchase** (`[('purchase_ok', '=', True)]`)
- **Late Activities** (`[('my_activity_date_deadline', '<', context_today().strftime('%Y-%m-%d'))]`)
- **Today Activities** (`[('my_activity_date_deadline', '=', context_today().strftime('%Y-%m-%d'))]`)
- **Future Activities** (`[('my_activity_date_deadline', '>', context_today().strftime('%Y-%m-%d'))                     ]`)
- **Favorites** (`[('is_favorite', '=', True)]`)
- **Warnings** (`[('activity_exception_decoration', '!=', False)]`)
- **Archived** (`[('active','=',False)]`)


**Agrupar por:**
- Product Type
- Product Category


### product.product

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | product.product.view.form.easy | `product.product_variant_easy_edit_view` | - |
| list | product.product.list | `product.product_product_tree_view` | - |
| list | product.product.view.list.tag | `product.product_product_view_tree_tag` | - |
| form | product.product.form | `product.product_normal_form_view` | product.product_template_form_view |
| form | product.product.view.form.normalized | `product.product_product_view_form_normalized` | - |
| kanban | Product Kanban | `product.product_kanban_view` | - |
| activity | product.product.activity | `product.product_product_view_activity` | - |
| kanban | product.view.kanban.catalog | `product.product_view_kanban_catalog` | - |
| search | product.view.search.catalog | `product.product_view_search_catalog` | - |



#### Botones (product.product_variant_easy_edit_view)
- **Print Labels** (object)
- **the product template.** (object)


#### Filtros de búsqueda (product.product_view_search_catalog)

**Filtros:**
- **Favorites** (`[('is_favorite', '=', True)]`)
- **Services** (`[('type', '=', 'service')]`)
- **Goods** (`[('type', '=', 'consu')]`)


**Agrupar por:**
- Product Type
- Product Category


### product.supplierinfo

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | product.supplierinfo.form.view | `product.product_supplierinfo_form_view` | - |
| search | product.supplierinfo.search.view | `product.product_supplierinfo_search_view` | - |
| kanban | product.supplierinfo.kanban | `product.product_supplierinfo_view_kanban` | - |
| list | product.supplierinfo.list.view | `product.product_supplierinfo_tree_view` | - |



#### Filtros de búsqueda (product.product_supplierinfo_search_view)

**Filtros:**
- **Active Products** (`['|', ('product_tmpl_id.active', '=', True),('product_id.active', '=', True)]`)
- **Active** (`['|', ('date_end', '=', False), ('date_end', '>=',  (context_today() - datetime.timedelta(days=1)).strftime('%Y-%m-%d'))]`)
- **Archived** (`[('date_end', '<',  (context_today() - datetime.timedelta(days=1)).strftime('%Y-%m-%d'))]`)


**Agrupar por:**
- Product
- Vendor


### product.category

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | product.category.form | `product.product_category_form_view` | - |
| list | product.category.list | `product.product_category_list_view` | - |
| search | product.category.search | `product.product_category_search_view` | - |



#### Botones (product.product_category_form_view)
- **%(product_template_action_all)d** (action)


### product.tag

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | product.tag.form | `product.product_tag_form_view` | - |
| list | product.tag.list | `product.product_tag_tree_view` | - |



### product.template.attribute.line

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | product.template.attribute.line.view.list | `product.product_template_attribute_line_view_tree` | - |
| form | product.template.attribute.line.form | `product.product_template_attribute_line_form` | - |



### product.attribute.value

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | product.attribute.value.list | `product.product_attribute_value_list` | - |



### product.document

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | product.document.form | `product.product_document_form` | - |
| kanban | product.document.kanban | `product.product_document_kanban` | - |
| list | product.document.list | `product.product_document_list` | - |
| search | product.document.search | `product.product_document_search` | - |



#### Filtros de búsqueda (product.product_document_search)

**Filtros:**
- **Archived** (`[('active', '=', False)]`)
- **Documents of this variant** (`[('res_model', '=', 'product.product'), ('res_id', '=', context.get('default_res_id'))]`)
- **All** (`['|', ('active', '=', True), ('active', '=', False)]`)


### product.combo

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | product.combo.form | `product.product_combo_view_form` | - |
| list | product.combo.list | `product.product_combo_view_tree` | - |



### product.packaging

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | product.packaging.list.view | `product.product_packaging_tree_view` | - |
| search | product.packaging.search | `product.product_packaging_search_view` | - |
| form | product.packaging.form.view | `product.product_packaging_form_view` | - |



### product.pricelist

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| search | product.pricelist.search | `product.product_pricelist_view_search` | - |
| list | product.pricelist.list | `product.product_pricelist_view_tree` | - |
| kanban | product.pricelist.kanban | `product.product_pricelist_view_kanban` | - |
| form | product.pricelist.form | `product.product_pricelist_view` | - |



#### Filtros de búsqueda (product.product_pricelist_view_search)

**Filtros:**
- **Archived** (`[('active','=',False)]`)


#### Botones (product.product_pricelist_view)
- **Print** (object)


### product.attribute

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | product.attribute.list | `product.attribute_tree_view` | - |
| form | product.attribute.form | `product.product_attribute_view_form` | - |
| search | product.attribute.view.search | `product.product_attribute_search` | - |



#### Botones (product.product_attribute_view_form)
- **action_open_product_template_attribute_lines** (object)
- **Add to products** (object)
- **Update extra prices** (object)


#### Filtros de búsqueda (product.product_attribute_search)

**Filtros:**
- **Inactive** (`[('active', '=', False)]`)


### product.template.attribute.value

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | product.template.attribute.value.view.list | `product.product_template_attribute_value_view_tree` | - |
| form | product.template.attribute.value.view.form. | `product.product_template_attribute_value_view_form` | - |
| search | - | `product.product_template_attribute_value_view_search` | - |



#### Filtros de búsqueda (product.product_template_attribute_value_view_search)

**Filtros:**
- **Active** (`[('ptav_active', '=', True)]`)
- **Inactive** (`[('ptav_active', '=', False)]`)


### product.pricelist.item

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| search | product.pricelist.item.search | `product.product_pricelist_item_view_search` | - |
| list | product.pricelist.item.list | `product.product_pricelist_item_tree_view` | - |
| list | product.pricelist.item.list | `product.product_pricelist_item_tree_view_from_product` | - |
| form | product.pricelist.item.form | `product.product_pricelist_item_form_view` | - |



#### Filtros de búsqueda (product.product_pricelist_item_view_search)

**Filtros:**
- **Product Rule** (`[('applied_on', '=', '1_product')]`)
- **Variant Rule** (`[('applied_on', '=', '0_product_variant')]`)
- **Active** (`[('pricelist_id.active', '=', True)]`)


**Agrupar por:**
- Product
- Variant
- Pricelist


### update.product.attribute.value

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | update.product.attribute.value.form | `product.update_product_attribute_value_form` | - |



#### Botones (product.update_product_attribute_value_form)
- **Confirm** (object)


### product.label.layout

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | product.label.layout.form | `product.product_label_layout_form` | - |



#### Botones (product.product_label_layout_form)
- **Confirm** (object)

