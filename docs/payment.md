# Módulo: Payment Engine

## Información General
- **Nombre técnico:** payment
- **Versión:** 2.0
- **Categoría:** Hidden
- **Dependencias:** onboarding, portal


## Propósito
The payment engine used by payment provider modules.





## Modelos

### res.country


- Hereda de:

  - res.country




- Campos:

  - **is_stripe_supported_country** (Boolean)





### payment.token


- Hereda de: Base



- Campos:

  - **provider_id** (Many2one) → payment.provider


  - **provider_code** (Selection)


  - **company_id** (Many2one)


  - **payment_method_id** (Many2one) → payment.method


  - **payment_method_code** (Char)


  - **payment_details** (Char)


  - **partner_id** (Many2one) → res.partner


  - **provider_ref** (Char)


  - **transaction_ids** (One2many) → payment.transaction


  - **active** (Boolean)





### payment.transaction


- Hereda de: Base



- Campos:

  - **provider_id** (Many2one) → payment.provider


  - **provider_code** (Selection)


  - **company_id** (Many2one)


  - **payment_method_id** (Many2one) → payment.method


  - **payment_method_code** (Char)


  - **reference** (Char)


  - **provider_reference** (Char)


  - **amount** (Monetary)


  - **currency_id** (Many2one) → res.currency


  - **token_id** (Many2one) → payment.token


  - **state** (Selection)


  - **state_message** (Text)


  - **last_state_change** (Datetime)


  - **operation** (Selection)


  - **source_transaction_id** (Many2one) → payment.transaction


  - **child_transaction_ids** (One2many) → payment.transaction


  - **refunds_count** (Integer)


  - **is_post_processed** (Boolean)


  - **tokenize** (Boolean)


  - **landing_route** (Char)


  - **partner_id** (Many2one) → res.partner


  - **partner_name** (Char)


  - **partner_lang** (Selection)


  - **partner_email** (Char)


  - **partner_address** (Char)


  - **partner_zip** (Char)


  - **partner_city** (Char)


  - **partner_state_id** (Many2one) → res.country.state


  - **partner_country_id** (Many2one) → res.country


  - **partner_phone** (Char)





### payment.method


- Hereda de: Base



- Campos:

  - **name** (Char)


  - **code** (Char)


  - **sequence** (Integer)


  - **primary_payment_method_id** (Many2one) → payment.method


  - **brand_ids** (One2many) → payment.method


  - **is_primary** (Boolean)


  - **provider_ids** (Many2many) → payment.provider


  - **active** (Boolean)


  - **image** (Image)


  - **image_payment_form** (Image)


  - **support_tokenization** (Boolean)


  - **support_express_checkout** (Boolean)


  - **support_refund** (Selection)


  - **supported_country_ids** (Many2many) → res.country


  - **supported_currency_ids** (Many2many) → res.currency





### payment.provider


- Hereda de: Base



- Campos:

  - **name** (Char)


  - **sequence** (Integer)


  - **code** (Selection)


  - **state** (Selection)


  - **is_published** (Boolean)


  - **company_id** (Many2one) → res.company


  - **main_currency_id** (Many2one)


  - **payment_method_ids** (Many2many) → payment.method


  - **allow_tokenization** (Boolean)


  - **capture_manually** (Boolean)


  - **allow_express_checkout** (Boolean)


  - **redirect_form_view_id** (Many2one) → ir.ui.view


  - **inline_form_view_id** (Many2one) → ir.ui.view


  - **token_inline_form_view_id** (Many2one) → ir.ui.view


  - **express_checkout_form_view_id** (Many2one) → ir.ui.view


  - **available_country_ids** (Many2many) → res.country


  - **available_currency_ids** (Many2many) → res.currency


  - **maximum_amount** (Monetary)


  - **pre_msg** (Html)


  - **pending_msg** (Html)


  - **auth_msg** (Html)


  - **done_msg** (Html)


  - **cancel_msg** (Html)


  - **support_tokenization** (Boolean)


  - **support_manual_capture** (Selection)


  - **support_express_checkout** (Boolean)


  - **support_refund** (Selection)


  - **image_128** (Image)


  - **color** (Integer)


  - **module_id** (Many2one) → ir.module.module


  - **module_state** (Selection)


  - **module_to_buy** (Boolean)





### onboarding.onboarding.step


- Hereda de:

  - onboarding.onboarding.step




- No agrega campos



### res.company


- Hereda de:

  - res.company




- Campos:

  - **payment_onboarding_payment_method** (Selection)





### ir.http


- Hereda de:

  - ir.http




- No agrega campos



### res.partner


- Hereda de:

  - res.partner




- Campos:

  - **payment_token_ids** (One2many) → payment.token


  - **payment_token_count** (Integer)








## Vistas


### payment.transaction

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | payment.transaction.form | `payment.payment_transaction_form` | - |
| list | payment.transaction.list | `payment.payment_transaction_list` | - |
| kanban | payment.transaction.kanban | `payment.payment_transaction_kanban` | - |
| search | payment.transaction.search | `payment.payment_transaction_search` | - |



#### Botones (payment.payment_transaction_form)
- **Capture Transaction** (object)
- **Void Transaction** (object)
- **action_view_refunds** (object)


#### Filtros de búsqueda (payment.payment_transaction_search)


**Agrupar por:**
- Provider
- Partner
- Status
- Company


### payment.provider

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | payment.provider.form | `payment.payment_provider_form` | - |
| list | payment.provider.list | `payment.payment_provider_list` | - |
| kanban | payment.provider.kanban | `payment.payment_provider_kanban` | - |
| search | payment.provider.search | `payment.payment_provider_search` | - |



#### Botones (payment.payment_provider_form)
- **action_toggle_is_published** (object)
- **action_toggle_is_published** (object)
- **Install** (object)


#### Filtros de búsqueda (payment.payment_provider_search)

**Filtros:**
- **Installed** (`[('module_state', '=', 'installed')]`)


**Agrupar por:**
- Provider
- State
- Company


### payment.token

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | payment.token.form | `payment.payment_token_form` | - |
| list | payment.token.list | `payment.payment_token_list` | - |
| search | payment.token.search | `payment.payment_token_search` | - |



#### Botones (payment.payment_token_form)
- **Payments** (action)


#### Filtros de búsqueda (payment.payment_token_search)

**Filtros:**
- **Archived** (`[('active', '=', False)]`)


**Agrupar por:**
- Provider
- Partner
- Company


### payment.method

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | payment.method.form | `payment.payment_method_form` | - |
| list | payment.method.list | `payment.payment_method_tree` | - |
| kanban | payment.method.kanban | `payment.payment_method_kanban` | - |
| search | payment.method.search | `payment.payment_method_search` | - |



#### Filtros de búsqueda (payment.payment_method_search)

**Filtros:**
- **Available methods** (`[('provider_ids.state', '!=', 'disabled')]`)

