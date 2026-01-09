# Módulo: Coupons & Loyalty

## Información General
- **Nombre técnico:** loyalty
- **Versión:** 1.0
- **Categoría:** Sales
- **Dependencias:** product, portal, account


## Propósito
Use discounts, gift card, eWallets and loyalty programs in different sales channels





## Modelos

### loyalty.card


- Hereda de:


  - mail.thread





- Campos:

  - **program_id** (Many2one) → loyalty.program


  - **program_type** (Selection)


  - **company_id** (Many2one)


  - **currency_id** (Many2one)


  - **partner_id** (Many2one) → res.partner


  - **points** (Float)


  - **point_name** (Char)


  - **points_display** (Char)


  - **code** (Char)


  - **expiration_date** (Date)


  - **use_count** (Integer)


  - **active** (Boolean)


  - **history_ids** (One2many) → loyalty.history





### loyalty.program


- Hereda de: Base



- Campos:

  - **name** (Char) → Program Name


  - **active** (Boolean)


  - **sequence** (Integer)


  - **company_id** (Many2one) → res.company


  - **currency_id** (Many2one) → res.currency


  - **currency_symbol** (Char)


  - **pricelist_ids** (Many2many) → product.pricelist


  - **total_order_count** (Integer) → Total Order Count


  - **rule_ids** (One2many) → loyalty.rule


  - **reward_ids** (One2many) → loyalty.reward


  - **communication_plan_ids** (One2many) → loyalty.mail


  - **mail_template_id** (Many2one) → mail.template


  - **trigger_product_ids** (Many2many)


  - **coupon_ids** (One2many) → loyalty.card


  - **coupon_count** (Integer)


  - **coupon_count_display** (Char)


  - **program_type** (Selection)


  - **date_from** (Date)


  - **date_to** (Date)


  - **limit_usage** (Boolean)


  - **max_usage** (Integer)


  - **applies_on** (Selection)


  - **trigger** (Selection)


  - **portal_visible** (Boolean)


  - **portal_point_name** (Char)


  - **is_nominative** (Boolean)


  - **is_payment_program** (Boolean)


  - **payment_program_discount_product_id** (Many2one) → product.product


  - **available_on** (Boolean) → Available On





### product.product


- Hereda de:

  - product.product




- No agrega campos



### product.template


- Hereda de:

  - product.template




- No agrega campos



### loyalty.history


- Hereda de: Base



- Campos:

  - **card_id** (Many2one) → loyalty.card


  - **company_id** (Many2one)


  - **description** (Text)


  - **issued** (Float)


  - **used** (Float)


  - **order_model** (Char)


  - **order_id** (Many2oneReference)





### loyalty.mail


- Hereda de: Base



- Campos:

  - **active** (Boolean)


  - **program_id** (Many2one) → loyalty.program


  - **trigger** (Selection)


  - **points** (Float)


  - **mail_template_id** (Many2one) → mail.template





### loyalty.rule


- Hereda de: Base



- Campos:

  - **active** (Boolean)


  - **program_id** (Many2one) → loyalty.program


  - **program_type** (Selection)


  - **company_id** (Many2one)


  - **currency_id** (Many2one)


  - **user_has_debug** (Boolean)


  - **product_domain** (Char)


  - **product_ids** (Many2many) → product.product


  - **product_category_id** (Many2one) → product.category


  - **product_tag_id** (Many2one) → product.tag


  - **reward_point_amount** (Float)


  - **reward_point_split** (Boolean)


  - **reward_point_name** (Char)


  - **reward_point_mode** (Selection)


  - **minimum_qty** (Integer) → Minimum Quantity


  - **minimum_amount** (Monetary) → Minimum Purchase


  - **minimum_amount_tax_mode** (Selection)


  - **mode** (Selection)


  - **code** (Char)





### product.pricelist


- Hereda de:

  - product.pricelist




- No agrega campos



### loyalty.reward


- Hereda de: Base



- Campos:

  - **active** (Boolean)


  - **program_id** (Many2one) → loyalty.program


  - **program_type** (Selection)


  - **company_id** (Many2one)


  - **currency_id** (Many2one)


  - **description** (Char)


  - **reward_type** (Selection)


  - **user_has_debug** (Boolean)


  - **discount** (Float) → Discount


  - **discount_mode** (Selection)


  - **discount_applicability** (Selection)


  - **discount_product_domain** (Char)


  - **discount_product_ids** (Many2many) → product.product


  - **discount_product_category_id** (Many2one) → product.category


  - **discount_product_tag_id** (Many2one) → product.tag


  - **all_discount_product_ids** (Many2many) → product.product


  - **reward_product_domain** (Char)


  - **discount_max_amount** (Monetary) → Max Discount


  - **discount_line_product_id** (Many2one) → product.product


  - **is_global_discount** (Boolean)


  - **tax_ids** (Many2many) → account.tax


  - **reward_product_id** (Many2one) → product.product


  - **reward_product_tag_id** (Many2one) → product.tag


  - **multi_product** (Boolean)


  - **reward_product_ids** (Many2many) → product.product


  - **reward_product_qty** (Integer)


  - **reward_product_uom_id** (Many2one) → uom.uom


  - **required_points** (Float) → Points needed


  - **point_name** (Char)


  - **clear_wallet** (Boolean)





### res.partner


- Hereda de:

  - res.partner




- Campos:

  - **loyalty_card_count** (Integer)








## Vistas


### loyalty.mail

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | loyalty.mail.view.list | `loyalty.loyalty_mail_view_tree` | - |



### loyalty.program

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | loyalty.program.view.form | `loyalty.loyalty_program_view_form` | - |
| list | loyalty.program.view.list | `loyalty.loyalty_program_view_tree` | - |
| search | loyalty.program.view.search | `loyalty.loyalty_program_view_search` | - |
| form | loyalty.program.gift.ewallet.view.form | `loyalty.loyalty_program_gift_ewallet_view_form` | loyalty_program_view_form |



#### Botones (loyalty.loyalty_program_view_form)
- **Generate Coupons** (action)
- **Generate Gift Cards** (action)
- **Generate eWallet** (action)
- **action_open_loyalty_cards** (object)


#### Filtros de búsqueda (loyalty.loyalty_program_view_search)

**Filtros:**
- **Archived** (`[('active', '=', False)]`)


### loyalty.history

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | loyalty.history.view.form | `loyalty.loyalty_history_form` | - |



### loyalty.rule

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | loyalty.rule.view.form | `loyalty.loyalty_rule_view_form` | - |
| kanban | loyalty.rule.view.kanban | `loyalty.loyalty_rule_view_kanban` | - |



### loyalty.card

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | loyalty.card.view.form | `loyalty.loyalty_card_view_form` | - |
| list | loyalty.card.view.list | `loyalty.loyalty_card_view_tree` | - |
| search | loyalty.card.view.search | `loyalty.loyalty_card_view_search` | - |



#### Botones (loyalty.loyalty_card_view_form)
- **action_loyalty_update_balance** (object)


#### Filtros de búsqueda (loyalty.loyalty_card_view_search)

**Filtros:**
- **Active** (`[                         '&', ('active', '=', True),                         '&', ('program_id.active', '=', True),                         '|', ('expiration_date', '>=', context_today().strftime('%Y-%m-%d 00:00:00')), ('expiration_date', '=', False)                     ]`)
- **Inactive** (`[                         '|', ('active', '=', False),                         '|', ('program_id.active', '=', False), ('expiration_date', '<', context_today().strftime('%Y-%m-%d 23:59:59'))                     ]`)


### loyalty.reward

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | loyalty.reward.view.form | `loyalty.loyalty_reward_view_form` | - |
| kanban | loyalty.reward.view.kanban | `loyalty.loyalty_reward_view_kanban` | - |



### loyalty.generate.wizard

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | loyalty.generate.wizard.view.form | `loyalty.loyalty_generate_wizard_view_form` | - |



#### Botones (loyalty.loyalty_generate_wizard_view_form)
- **generate_coupons** (object)


### loyalty.card.update.balance

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | loyalty.card.update.balance.view.form | `loyalty.loyalty_card_update_balance_form` | - |



#### Botones (loyalty.loyalty_card_update_balance_form)
- **action_update_card_point** (object)

