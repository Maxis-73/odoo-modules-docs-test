# Módulo: Invoicing

## Información General
- **Nombre técnico:** account
- **Versión:** 1.3
- **Categoría:** Accounting/Accounting
- **Dependencias:** base_setup, onboarding, product, analytic, portal, digest


## Propósito
Invoices, Payments, Follow-ups & Bank Synchronization



## Descripción

Invoicing & Payments
====================
The specific and easy-to-use Invoicing system in Odoo allows you to keep track of your accounting, even when you are not an accountant. It provides an easy way to follow up on your vendors and customers.

You could use this simplified accounting in case you work with an (external) account to keep your books, and you still want to keep track of payments. This module also offers you an easy method of registering payments, without having to encode complete abstracts of account.
    



## Modelos

### account.partial.reconcile


- Hereda de: Base



#### Campos
- **debit_move_id** (Many2one) → account.move.line
- **credit_move_id** (Many2one) → account.move.line
- **full_reconcile_id** (Many2one) → account.full.reconcile
- **exchange_move_id** (Many2one) → account.move
- **company_currency_id** (Many2one) → res.currency
- **debit_currency_id** (Many2one) → res.currency
- **credit_currency_id** (Many2one) → res.currency
- **amount** (Monetary)
- **debit_amount_currency** (Monetary)
- **credit_amount_currency** (Monetary)
- **company_id** (Many2one) → res.company
- **max_date** (Date)





### uom.uom


- Hereda de:

  - uom.uom




#### Campos
- **fiscal_country_codes** (Char)





### res.currency


- Hereda de:

  - res.currency




#### Campos
- **display_rounding_warning** (Boolean)
- **fiscal_country_codes** (Char)





### account.move.send


- Hereda de: Base



- No agrega campos




### res.partner.bank


- Hereda de:


  - res.partner.bank

  - mail.thread

  - mail.activity.mixin





#### Campos
- **journal_id** (One2many) → account.journal
- **has_iban_warning** (Boolean)
- **partner_country_name** (Char)
- **has_money_transfer_warning** (Boolean)
- **money_transfer_service** (Char)
- **partner_supplier_rank** (Integer)
- **partner_customer_rank** (Integer)
- **related_moves** (One2many) → account.move
- **bank_id** (Many2one)
- **active** (Boolean)
- **acc_number** (Char)
- **acc_holder_name** (Char)
- **partner_id** (Many2one)
- **user_has_group_validate_bank_account** (Boolean)
- **allow_out_payment** (Boolean)
- **currency_id** (Many2one)
- **lock_trust_fields** (Boolean)
- **duplicate_bank_partner_ids** (Many2many) → res.partner





### res.company


- Hereda de:


  - res.company

  - mail.thread





#### Campos
- **fiscalyear_last_day** (Integer)
- **fiscalyear_last_month** (Selection)
- **fiscalyear_lock_date** (Date)
- **tax_lock_date** (Date)
- **sale_lock_date** (Date)
- **purchase_lock_date** (Date)
- **hard_lock_date** (Date)
- **user_fiscalyear_lock_date** (Date)
- **user_tax_lock_date** (Date)
- **user_sale_lock_date** (Date)
- **user_purchase_lock_date** (Date)
- **user_hard_lock_date** (Date)
- **transfer_account_id** (Many2one) → account.account
- **expects_chart_of_accounts** (Boolean)
- **chart_template** (Selection)
- **bank_account_code_prefix** (Char)
- **cash_account_code_prefix** (Char)
- **default_cash_difference_income_account_id** (Many2one) → account.account
- **default_cash_difference_expense_account_id** (Many2one) → account.account
- **account_journal_suspense_account_id** (Many2one) → account.account
- **account_journal_early_pay_discount_gain_account_id** (Many2one) → account.account
- **account_journal_early_pay_discount_loss_account_id** (Many2one) → account.account
- **transfer_account_code_prefix** (Char)
- **account_sale_tax_id** (Many2one) → account.tax
- **account_purchase_tax_id** (Many2one) → account.tax
- **tax_calculation_rounding_method** (Selection)
- **currency_exchange_journal_id** (Many2one) → account.journal
- **income_currency_exchange_account_id** (Many2one) → account.account
- **expense_currency_exchange_account_id** (Many2one) → account.account
- **anglo_saxon_accounting** (Boolean)
- **bank_journal_ids** (One2many) → account.journal
- **incoterm_id** (Many2one) → account.incoterms
- **qr_code** (Boolean)
- **display_invoice_amount_total_words** (Boolean)
- **display_invoice_tax_company_currency** (Boolean)
- **account_use_credit_limit** (Boolean)
- **batch_payment_sequence_id** (Many2one) → ir.sequence
- **account_opening_move_id** (Many2one) → account.move
- **account_opening_journal_id** (Many2one) → account.journal
- **account_opening_date** (Date)
- **invoice_terms** (Html)
- **terms_type** (Selection)
- **invoice_terms_html** (Html)
- **account_default_pos_receivable_account_id** (Many2one) → account.account
- **expense_accrual_account_id** (Many2one) → account.account
- **revenue_accrual_account_id** (Many2one) → account.account
- **automatic_entry_default_journal_id** (Many2one) → account.journal
- **account_fiscal_country_id** (Many2one) → res.country
- **account_enabled_tax_country_ids** (Many2many) → res.country
- **tax_exigibility** (Boolean)
- **tax_cash_basis_journal_id** (Many2one) → account.journal
- **account_cash_basis_base_account_id** (Many2one) → account.account
- **account_storno** (Boolean)
- **fiscal_position_ids** (One2many) → account.fiscal.position
- **multi_vat_foreign_country_ids** (Many2many) → res.country
- **quick_edit_mode** (Selection)
- **account_discount_income_allocation_id** (Many2one) → account.account
- **account_discount_expense_allocation_id** (Many2one) → account.account
- **check_account_audit_trail** (Boolean)
- **autopost_bills** (Boolean)
- **account_price_include** (Selection)
- **company_vat_placeholder** (Char)
- **company_registry_placeholder** (Char)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | res.company.view.form.terms | `account.res_company_view_form_terms` | - |
| form | res.company.form.view.onboarding | `account.res_company_form_view_onboarding` | - |
| form | res.company.form.view.onboarding.sale.tax | `account.res_company_form_view_onboarding_sale_tax` | - |



**Botones (account.res_company_form_view_onboarding):**
- **Save** (object)


**Botones (account.res_company_form_view_onboarding_sale_tax):**
- **Apply** (object)



### account.bank.statement


- Hereda de: Base



#### Campos
- **name** (Char)
- **reference** (Char)
- **date** (Date)
- **first_line_index** (Char) → account.bank.statement.line
- **balance_start** (Monetary)
- **balance_end** (Monetary)
- **balance_end_real** (Monetary)
- **company_id** (Many2one) → res.company
- **currency_id** (Many2one) → res.currency
- **journal_id** (Many2one) → account.journal
- **line_ids** (One2many) → account.bank.statement.line
- **is_complete** (Boolean)
- **is_valid** (Boolean)
- **problem_description** (Text)
- **attachment_ids** (Many2many) → ir.attachment





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | account.bank.statement.list | `account.view_bank_statement_tree` | - |
| search | account.bank.statement.search | `account.view_bank_statement_search` | - |
| pivot | account.bank.statement.pivot | `account.account_bank_statement_pivot` | - |
| graph | account.bank.statement.graph | `account.account_bank_statement_graph` | - |



**Filtros de búsqueda (account.view_bank_statement_search):**

- **Empty** (`[('line_ids','=',False)]`)
- **Invalid** (`['|', ('is_valid', '=', False),('is_complete', '=', False)]`)
- **filter_date**


*Agrupar por:*
- Journal
- Date



### account.full.reconcile


- Hereda de: Base



#### Campos
- **partial_reconcile_ids** (One2many) → account.partial.reconcile
- **reconciled_line_ids** (One2many) → account.move.line
- **exchange_move_id** (Many2one) → account.move





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | account.full.reconcile.form | `account.view_full_reconcile_form` | - |




### ir.module.module


- Hereda de:

  - ir.module.module




#### Campos
- **account_templates** (Binary)





### account.analytic.line


- Hereda de:

  - account.analytic.line




#### Campos
- **product_id** (Many2one) → product.product
- **general_account_id** (Many2one) → account.account
- **journal_id** (Many2one) → account.journal
- **partner_id** (Many2one)
- **move_line_id** (Many2one) → account.move.line
- **code** (Char)
- **ref** (Char)
- **category** (Selection)





### account.incoterms


- Hereda de: Base



#### Campos
- **name** (Char) → Name
- **code** (Char) → Code
- **active** (Boolean) → Active





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | account.incoterms.list | `account.view_incoterms_tree` | - |
| form | account.incoterms.form | `account.account_incoterms_form` | - |
| search | account.incoterms.search | `account.account_incoterms_view_search` | - |



**Filtros de búsqueda (account.account_incoterms_view_search):**

- **Archived** (`[('active', '=', False)]`)



### kpi.provider


- Hereda de:

  - kpi.provider




- No agrega campos




### account.report


- Hereda de: Base



#### Campos
- **name** (Char)
- **sequence** (Integer)
- **active** (Boolean)
- **line_ids** (One2many) → account.report.line
- **column_ids** (One2many) → account.report.column
- **root_report_id** (Many2one) → account.report
- **variant_report_ids** (One2many) → account.report
- **section_report_ids** (Many2many) → account.report
- **section_main_report_ids** (Many2many) → account.report
- **use_sections** (Boolean)
- **chart_template** (Selection)
- **country_id** (Many2one) → res.country
- **only_tax_exigible** (Boolean)
- **availability_condition** (Selection)
- **load_more_limit** (Integer)
- **search_bar** (Boolean)
- **prefix_groups_threshold** (Integer)
- **integer_rounding** (Selection)
- **default_opening_date_filter** (Selection)
- **currency_translation** (Selection)
- **filter_multi_company** (Selection)
- **filter_date_range** (Boolean)
- **filter_show_draft** (Boolean)
- **filter_unreconciled** (Boolean)
- **filter_unfold_all** (Boolean)
- **filter_hide_0_lines** (Selection)
- **filter_period_comparison** (Boolean)
- **filter_growth_comparison** (Boolean)
- **filter_journals** (Boolean)
- **filter_analytic** (Boolean)
- **filter_hierarchy** (Selection)
- **filter_account_type** (Selection)
- **filter_partner** (Boolean)
- **filter_fiscal_position** (Boolean)
- **filter_aml_ir_filters** (Boolean)
- **filter_budgets** (Boolean)





### account.report.line


- Hereda de: Base



#### Campos
- **name** (Char)
- **expression_ids** (One2many) → account.report.expression
- **report_id** (Many2one) → account.report
- **hierarchy_level** (Integer)
- **parent_id** (Many2one) → account.report.line
- **children_ids** (One2many) → account.report.line
- **groupby** (Char)
- **user_groupby** (Char)
- **sequence** (Integer)
- **code** (Char)
- **foldable** (Boolean)
- **print_on_new_page** (Boolean) → Print On New Page
- **action_id** (Many2one) → ir.actions.actions
- **hide_if_zero** (Boolean)
- **domain_formula** (Char)
- **account_codes_formula** (Char)
- **aggregation_formula** (Char)
- **external_formula** (Char)
- **horizontal_split_side** (Selection)
- **tax_tags_formula** (Char)





### account.report.expression


- Hereda de: Base



#### Campos
- **report_line_id** (Many2one) → account.report.line
- **report_line_name** (Char)
- **label** (Char)
- **engine** (Selection)
- **formula** (Char)
- **subformula** (Char)
- **date_scope** (Selection)
- **figure_type** (Selection)
- **green_on_positive** (Boolean)
- **blank_if_zero** (Boolean)
- **auditable** (Boolean)
- **carryover_target** (Char)





### account.report.column


- Hereda de: Base



#### Campos
- **name** (Char)
- **expression_label** (Char)
- **sequence** (Integer)
- **report_id** (Many2one) → account.report
- **sortable** (Boolean)
- **figure_type** (Selection)
- **blank_if_zero** (Boolean)
- **custom_audit_action_id** (Many2one) → ir.actions.act_window





### account.report.external.value


- Hereda de: Base



#### Campos
- **name** (Char)
- **value** (Float)
- **text_value** (Char)
- **date** (Date)
- **target_report_expression_id** (Many2one) → account.report.expression
- **target_report_line_id** (Many2one)
- **target_report_expression_label** (Char)
- **report_country_id** (Many2one)
- **company_id** (Many2one) → res.company
- **foreign_vat_fiscal_position_id** (Many2one) → account.fiscal.position
- **carryover_origin_expression_label** (Char)
- **carryover_origin_report_line_id** (Many2one) → account.report.line





### account.payment


- Hereda de:


  - mail.thread.main.attachment

  - mail.activity.mixin





#### Campos
- **name** (Char)
- **date** (Date)
- **move_id** (Many2one) → account.move
- **journal_id** (Many2one) → account.journal
- **company_id** (Many2one) → res.company
- **state** (Selection)
- **is_reconciled** (Boolean)
- **is_matched** (Boolean)
- **is_sent** (Boolean)
- **available_partner_bank_ids** (Many2many) → res.partner.bank
- **partner_bank_id** (Many2one) → res.partner.bank
- **qr_code** (Html)
- **paired_internal_transfer_payment_id** (Many2one) → account.payment
- **payment_method_line_id** (Many2one) → account.payment.method.line
- **available_payment_method_line_ids** (Many2many) → account.payment.method.line
- **payment_method_id** (Many2one)
- **available_journal_ids** (Many2many) → account.journal
- **amount** (Monetary)
- **payment_type** (Selection)
- **partner_type** (Selection)
- **memo** (Char)
- **payment_reference** (Char)
- **currency_id** (Many2one) → res.currency
- **company_currency_id** (Many2one)
- **partner_id** (Many2one) → res.partner
- **outstanding_account_id** (Many2one) → account.account
- **destination_account_id** (Many2one) → account.account
- **invoice_ids** (Many2many) → account.move
- **reconciled_invoice_ids** (Many2many) → account.move
- **reconciled_invoices_count** (Integer)
- **reconciled_invoices_type** (Selection)
- **reconciled_bill_ids** (Many2many) → account.move
- **reconciled_bills_count** (Integer)
- **reconciled_statement_line_ids** (Many2many) → account.bank.statement.line
- **reconciled_statement_lines_count** (Integer)
- **payment_method_code** (Char)
- **payment_receipt_title** (Char)
- **need_cancel_request** (Boolean)
- **show_partner_bank_account** (Boolean)
- **require_partner_bank_account** (Boolean)
- **country_code** (Char)
- **amount_signed** (Monetary)
- **amount_company_currency_signed** (Monetary)
- **duplicate_payment_ids** (Many2many) → account.payment
- **attachment_ids** (One2many) → ir.attachment





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | account.payment.list | `account.view_account_payment_tree` | - |
| kanban | account.payment.kanban | `account.view_account_payment_kanban` | - |
| search | account.payment.search | `account.view_account_payment_search` | - |
| form | account.payment.form | `account.view_account_payment_form` | - |
| graph | account.payment.graph | `account.view_account_payment_graph` | - |



**Filtros de búsqueda (account.view_account_payment_search):**

- **Customer Payments** (`[('partner_type', '=', 'customer')]`)
- **Vendor Payments** (`[('partner_type', '=', 'supplier')]`)
- **Draft** (`[('state', '=', 'draft')]`)
- **In Process** (`[('state', '=', 'in_process')]`)
- **Sent** (`[('is_sent', '=', 'True')]`)
- **Not Sent** (`[('is_sent', '=', 'False')]`)
- **No Bank Matching** (`[('is_matched', '=', False)]`)
- **Reconciled** (`[('is_reconciled', '=', True)]`)
- **Payment Date**
- **Late Activities** (`[('my_activity_date_deadline', '<', context_today().strftime('%Y-%m-%d'))]`)
- **Today Activities** (`[('my_activity_date_deadline', '=', context_today().strftime('%Y-%m-%d'))]`)
- **Future Activities** (`[('my_activity_date_deadline', '>', context_today().strftime('%Y-%m-%d'))]`)


*Agrupar por:*
- Partner
- Journal
- Payment Method Line
- Status
- Payment Date
- Currency
- Company


**Botones (account.view_account_payment_form):**
- **Confirm** (object)
- **Validate** (object)
- **Reject** (object)
- **Reset To Draft** (object) - Grupos: `account.group_account_invoice`
- **Cancel** (object)
- **Request Cancel** (object) - Grupos: `account.group_account_invoice`
- **Mark as Sent** (object)
- **Unmark as Sent** (object)
- **button_open_invoices** (object)
- **button_open_bills** (object)
- **button_open_statement_lines** (object)
- **button_open_journal_entry** (object) - Grupos: `account.group_account_user,account.group_account_readonly`



### account.move


- Hereda de:


  - account.move





#### Campos
- **payment_ids** (One2many) → account.payment





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | account.move.list | `account.view_move_tree` | - |
| list | account.invoice.list | `account.view_invoice_tree` | - |
| kanban | account.move.kanban | `account.view_account_move_kanban` | - |
| form | account.move.form | `account.view_move_form` | - |
| activity | account.move.view.activity | `account.account_move_view_activity` | - |
| search | account.move.select | `account.view_account_move_filter` | - |
| search | account.invoice.select | `account.view_account_invoice_filter` | - |



**Botones (account.view_move_form):**
- **Post** (object) - Grupos: `account.group_account_invoice`
- **Confirm** (object) - Grupos: `account.group_account_invoice`
- **Send** (object)
- **Send** (object)
- **Print** (object)
- **Print** (object)
- **Pay** (object) - Grupos: `account.group_account_invoice`
- **Pay** (object) - Grupos: `account.group_account_invoice`
- **Preview** (object)
- **Reverse Entry** (action) - Grupos: `account.group_account_invoice`
- **Credit Note** (object) - Grupos: `account.group_account_invoice`
- **Cancel Entry** (object) - Grupos: `account.group_account_invoice`
- **Cancel** (object) - Grupos: `account.group_account_invoice`
- **Reset to Draft** (object) - Grupos: `account.group_account_invoice`
- **Lock** (object) - Grupos: `account.group_account_invoice`
- **Request Cancel** (object) - Grupos: `account.group_account_invoice`
- **Set as Checked** (object) - Grupos: `account.group_account_invoice`
- **action_activate_currency** (object)
- **action_activate_currency** (object)
- **action_open_business_doc** (object)
- **open_payments** (object)
- **open_reconcile_view** (object)
- **open_created_caba_entries** (object)
- **Update Taxes and Accounts** (object)
- **refresh_invoice_currency_rate** (object)
- **Catalog** (object)
- **Cut-Off** (object)


**Filtros de búsqueda (account.view_account_move_filter):**

- **Unposted** (`[('state', '=', 'draft')]`)
- **Posted** (`[('state', '=', 'posted')]`)
- **Not Secured** (`[('secured', '=', False), ('state', '=', 'posted')]`)
- **Reversed** (`[('payment_state', '=', 'reversed')]`)
- **To Check** (`[('checked', '=', False), ('state', '!=', 'draft')]`)
- **Sales** (`[('journal_id.type', '=', 'sale')]`)
- **Purchases** (`[('journal_id.type', '=', 'purchase')]`)
- **Bank** (`[('journal_id.type', '=', 'bank')]`)
- **Cash** (`[('journal_id.type', '=', 'cash')]`)
- **Credit** (`[('journal_id.type', '=', 'credit')]`)
- **Miscellaneous** (`[('journal_id.type', '=', 'general')]`)
- **Date**
- **Invoice Date**


*Agrupar por:*
- Partner
- Journal
- Status
- Payment Method
- Date
- Invoice Date
- Company


**Filtros de búsqueda (account.view_account_invoice_filter):**

- **myinvoices** (`[('invoice_user_id', '=', uid)]`)
- **Draft** (`[('state','=','draft')]`)
- **Posted** (`[('state', '=', 'posted')]`)
- **Cancelled** (`[('state', '=', 'cancel')]`)
- **Not Secured** (`[('secured', '=', False), ('state', '=', 'posted')]`)
- **Not Sent** (`[('is_move_sent', '=', False)]`)
- **Invoices** (`[('move_type', '=', 'out_invoice')]`)
- **Credit Notes** (`[('move_type', '=', 'out_refund')]`)
- **To Check** (`[('checked', '=', False), ('state', '!=', 'draft')]`)
- **To pay** (`[('state', '=', 'posted'), ('payment_state', 'in', ('not_paid', 'partial')), ('move_type', '!=', 'entry')]`)
- **In payment** (`[('state', '=', 'posted'), ('payment_state', '=', 'in_payment')]`)
- **Overdue** (`[                         ('invoice_date_due', '<', time.strftime('%Y-%m-%d')),                         ('state', '=', 'posted'),                         ('payment_state', 'in', ('not_paid', 'partial')),                         ('move_type', '!=', 'entry')                     ]`)
- **Invoice Date**
- **Accounting Date**
- **Due Date**
- **Late Activities** (`[('my_activity_date_deadline', '<', context_today().strftime('%Y-%m-%d'))]`)
- **Today Activities** (`[('my_activity_date_deadline', '=', context_today().strftime('%Y-%m-%d'))]`)
- **Future Activities** (`[('my_activity_date_deadline', '>', context_today().strftime('%Y-%m-%d'))]`)


*Agrupar por:*
- Salesperson
- Partner
- Status
- Payment Method
- Journal
- Company
- Invoice Date
- Due Date
- Accounting Date
- Sequence Prefix



### onboarding.onboarding.step


- Hereda de:

  - onboarding.onboarding.step




- No agrega campos




### account.analytic.distribution.model


- Hereda de:

  - account.analytic.distribution.model




#### Campos
- **account_prefix** (Char)
- **product_id** (Many2one) → product.product
- **product_categ_id** (Many2one) → product.category
- **prefix_placeholder** (Char)





### account.move.line


- Hereda de:

  - account.move.line




- No agrega campos




#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | account.move.line.form | `account.view_move_line_form` | - |
| kanban | account.move.line.kanban | `account.account_move_line_view_kanban` | - |
| pivot | account.move.line.pivot | `account.view_move_line_pivot` | - |
| list | account.move.line.list | `account.view_move_line_tree` | - |
| graph | account.move.line.graph | `account.account_move_line_graph_date` | - |
| search | account.move.line.search | `account.view_account_move_line_filter` | - |
| list | account.move.line.payment.list | `account.view_move_line_payment_tree` | - |
| search | account.move.line.payment.search | `account.view_account_move_line_payment_filter` | - |



**Botones (account.view_move_line_form):**
- **-> View partially reconciled entries** (object)


**Filtros de búsqueda (account.view_account_move_line_filter):**

- **Unposted** (`[('parent_state', '=', 'draft')]`)
- **Posted** (`[('parent_state', '=', 'posted')]`)
- **Not Secured** (`[('move_id.secured', '=', False), ('move_id.state', '=', 'posted')]`)
- **To check** (`[('move_id.checked', '=', False), ('parent_state', '!=', 'draft')]`)
- **Unreconciled** (`[('balance', '!=', 0), ('account_id.reconcile', '=', True), '|', ('matching_number', '=', False), ('matching_number', '=like', 'P%')]`)
- **With residual** (`[('amount_residual', '!=', 0), ('account_id.reconcile', '=', True)]`)
- **Sales** (`[('journal_id.type', '=', 'sale')]`)
- **Purchases** (`[('journal_id.type', '=', 'purchase')]`)
- **Bank** (`[('journal_id.type', '=', 'bank')]`)
- **Cash** (`[('journal_id.type', '=', 'cash')]`)
- **Credit** (`[('journal_id.type', '=', 'credit')]`)
- **Miscellaneous** (`[('journal_id.type', '=', 'general')]`)
- **Payable** (`[('account_id.account_type', '=', 'liability_payable'), ('account_id.non_trade', '=', False)]`)
- **Receivable** (`[('account_id.account_type', '=', 'asset_receivable'), ('account_id.non_trade', '=', False)]`)
- **Non Trade Payable** (`[('account_id.account_type', '=', 'liability_payable'), ('account_id.non_trade', '=', True)]`)
- **Non Trade Receivable** (`[('account_id.account_type', '=', 'asset_receivable'), ('account_id.non_trade', '=', True)]`)
- **P&L Accounts** (`[('account_id.internal_group', 'in', ('income', 'expense'))]`)
- **No Bank Transaction** (`[('statement_line_id', '=', False), ('payment_id', '=', False)]`)
- **Date**
- **Invoice Date**
- **Report Dates** (`[('date', '>=', context.get('date_from')), ('date', '<=', context.get('date_to'))]`)
- **Report Dates** (`[('date', '<=', context.get('date_to'))]`)
- **Analytic Accounts** (`[('analytic_distribution', 'in', context.get('analytic_ids'))]`)


*Agrupar por:*
- Journal Entry
- Account
- Partner
- Journal
- Date
- Invoice Date
- Taxes
- Tax Grid
- Matching


**Filtros de búsqueda (account.view_account_move_line_payment_filter):**

- **Posted** (`[('parent_state', '=', 'posted')]`)
- **Invoices** (`[('amount_residual', '>', '0')]`)
- **Credit Notes** (`[('amount_residual', '<', '0')]`)
- **Bills** (`[('amount_residual', '<', '0')]`)
- **Refunds** (`[('amount_residual', '>', '0')]`)
- **Invoice Date**
- **Next Payment Date**
- **Overdue** (`[('date_maturity', '<', time.strftime('%Y-%m-%d'))]`)
- **Early Discount** (`[('discount_date', '!=', False), ('discount_date', '>', time.strftime('%Y-%m-%d'))]`)
- **Report Dates** (`[('date', '>=', context.get('date_from')), ('date', '<=', context.get('date_to'))]`)
- **Report Dates** (`[('date', '<=', context.get('date_to'))]`)


*Agrupar por:*
- Currency
- Partner
- Journal
- Invoice Date
- Next Payment Date



### ir.actions.report


- Hereda de:

  - ir.actions.report




#### Campos
- **is_invoice_report** (Boolean)





### account.payment.method


- Hereda de: Base



#### Campos
- **name** (Char)
- **code** (Char)
- **payment_type** (Selection)





### account.payment.method.line


- Hereda de: Base



#### Campos
- **name** (Char)
- **sequence** (Integer)
- **payment_method_id** (Many2one) → account.payment.method
- **payment_account_id** (Many2one) → account.account
- **journal_id** (Many2one) → account.journal
- **default_account_id** (Many2one)
- **code** (Char)
- **payment_type** (Selection)
- **company_id** (Many2one)
- **available_payment_method_ids** (Many2many)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | account.payment.method.line.list | `account.view_account_payment_method_line_tree` | - |
| kanban | account.payment.method.line.kanban | `account.view_account_payment_method_line_kanban_mobile` | - |




### digest.digest


- Hereda de:

  - digest.digest




#### Campos
- **kpi_account_total_revenue** (Boolean) → Revenue
- **kpi_account_total_revenue_value** (Monetary)





### account.analytic.account


- Hereda de:

  - account.analytic.account




#### Campos
- **invoice_count** (Integer) → Invoice Count
- **vendor_bill_count** (Integer) → Vendor Bill Count
- **debit** (Monetary)
- **credit** (Monetary)





### account.move


- Hereda de:


  - portal.mixin

  - mail.thread.main.attachment

  - mail.activity.mixin

  - sequence.mixin

  - product.catalog.mixin





#### Campos
- **name** (Char)
- **name_placeholder** (Char)
- **ref** (Char)
- **date** (Date)
- **state** (Selection)
- **move_type** (Selection)
- **is_storno** (Boolean)
- **journal_id** (Many2one) → account.journal
- **journal_group_id** (Many2one) → account.journal.group
- **company_id** (Many2one) → res.company
- **line_ids** (One2many) → account.move.line
- **origin_payment_id** (Many2one) → account.payment
- **matched_payment_ids** (Many2many) → account.payment
- **reconciled_payment_ids** (Many2many) → account.payment
- **payment_count** (Integer)
- **statement_line_id** (Many2one) → account.bank.statement.line
- **statement_id** (Many2one)
- **tax_cash_basis_rec_id** (Many2one) → account.partial.reconcile
- **tax_cash_basis_origin_move_id** (Many2one) → account.move
- **tax_cash_basis_created_move_ids** (One2many) → account.move
- **always_tax_exigible** (Boolean)
- **auto_post** (Selection)
- **auto_post_until** (Date)
- **auto_post_origin_id** (Many2one) → account.move
- **hide_post_button** (Boolean)
- **checked** (Boolean)
- **posted_before** (Boolean)
- **suitable_journal_ids** (Many2many) → account.journal
- **highest_name** (Char)
- **made_sequence_gap** (Boolean)
- **show_name_warning** (Boolean)
- **type_name** (Char) → Type Name
- **country_code** (Char)
- **company_price_include** (Selection)
- **attachment_ids** (One2many) → ir.attachment
- **audit_trail_message_ids** (One2many) → mail.message
- **restrict_mode_hash_table** (Boolean)
- **secure_sequence_number** (Integer)
- **inalterable_hash** (Char)
- **secured** (Boolean)
- **invoice_line_ids** (One2many) → account.move.line
- **invoice_date** (Date)
- **invoice_date_due** (Date)
- **delivery_date** (Date)
- **show_delivery_date** (Boolean)
- **invoice_payment_term_id** (Many2one) → account.payment.term
- **needed_terms** (Binary)
- **needed_terms_dirty** (Boolean)
- **tax_calculation_rounding_method** (Selection)
- **partner_id** (Many2one) → res.partner
- **commercial_partner_id** (Many2one) → res.partner
- **partner_shipping_id** (Many2one) → res.partner
- **partner_bank_id** (Many2one) → res.partner.bank
- **fiscal_position_id** (Many2one) → account.fiscal.position
- **payment_reference** (Char)
- **display_qr_code** (Boolean)
- **qr_code_method** (Selection)
- **invoice_outstanding_credits_debits_widget** (Binary)
- **invoice_has_outstanding** (Boolean)
- **invoice_payments_widget** (Binary)
- **preferred_payment_method_line_id** (Many2one) → account.payment.method.line
- **company_currency_id** (Many2one)
- **currency_id** (Many2one) → res.currency
- **expected_currency_rate** (Float)
- **invoice_currency_rate** (Float)
- **direction_sign** (Integer)
- **amount_untaxed** (Monetary)
- **amount_tax** (Monetary)
- **amount_total** (Monetary)
- **amount_residual** (Monetary)
- **amount_untaxed_signed** (Monetary)
- **amount_untaxed_in_currency_signed** (Monetary)
- **amount_tax_signed** (Monetary)
- **amount_total_signed** (Monetary)
- **amount_total_in_currency_signed** (Monetary)
- **amount_residual_signed** (Monetary)
- **tax_totals** (Binary)
- **payment_state** (Selection)
- **status_in_payment** (Selection)
- **amount_total_words** (Char)
- **reversed_entry_id** (Many2one) → account.move
- **reversal_move_ids** (One2many) → account.move
- **invoice_vendor_bill_id** (Many2one) → account.move
- **invoice_source_email** (Char)
- **invoice_partner_display_name** (Char)
- **is_manually_modified** (Boolean)
- **quick_edit_mode** (Boolean)
- **quick_edit_total_amount** (Monetary)
- **quick_encoding_vals** (Json)
- **narration** (Html)
- **is_move_sent** (Boolean)
- **is_being_sent** (Boolean)
- **move_sent_values** (Selection)
- **invoice_user_id** (Many2one) → res.users
- **user_id** (Many2one)
- **invoice_origin** (Char)
- **invoice_incoterm_id** (Many2one) → account.incoterms
- **incoterm_location** (Char)
- **invoice_cash_rounding_id** (Many2one) → account.cash.rounding
- **sending_data** (Json)
- **invoice_pdf_report_id** (Many2one) → ir.attachment
- **invoice_pdf_report_file** (Binary)
- **invoice_filter_type_domain** (Char)
- **bank_partner_id** (Many2one) → res.partner
- **tax_lock_date_message** (Char)
- **display_inactive_currency_warning** (Boolean)
- **tax_country_id** (Many2one) → res.country
- **tax_country_code** (Char)
- **has_reconciled_entries** (Boolean)
- **show_reset_to_draft_button** (Boolean)
- **partner_credit_warning** (Text)
- **partner_credit** (Monetary)
- **duplicated_ref_ids** (Many2many) → account.move
- **need_cancel_request** (Boolean)
- **show_update_fpos** (Boolean)
- **payment_term_details** (Binary)
- **show_payment_term_details** (Boolean)
- **show_discount_details** (Boolean)
- **abnormal_amount_warning** (Text)
- **abnormal_date_warning** (Text)
- **taxes_legal_notes** (Html)
- **next_payment_date** (Date)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | account.move.list | `account.view_move_tree` | - |
| list | account.invoice.list | `account.view_invoice_tree` | - |
| kanban | account.move.kanban | `account.view_account_move_kanban` | - |
| form | account.move.form | `account.view_move_form` | - |
| activity | account.move.view.activity | `account.account_move_view_activity` | - |
| search | account.move.select | `account.view_account_move_filter` | - |
| search | account.invoice.select | `account.view_account_invoice_filter` | - |



**Botones (account.view_move_form):**
- **Post** (object) - Grupos: `account.group_account_invoice`
- **Confirm** (object) - Grupos: `account.group_account_invoice`
- **Send** (object)
- **Send** (object)
- **Print** (object)
- **Print** (object)
- **Pay** (object) - Grupos: `account.group_account_invoice`
- **Pay** (object) - Grupos: `account.group_account_invoice`
- **Preview** (object)
- **Reverse Entry** (action) - Grupos: `account.group_account_invoice`
- **Credit Note** (object) - Grupos: `account.group_account_invoice`
- **Cancel Entry** (object) - Grupos: `account.group_account_invoice`
- **Cancel** (object) - Grupos: `account.group_account_invoice`
- **Reset to Draft** (object) - Grupos: `account.group_account_invoice`
- **Lock** (object) - Grupos: `account.group_account_invoice`
- **Request Cancel** (object) - Grupos: `account.group_account_invoice`
- **Set as Checked** (object) - Grupos: `account.group_account_invoice`
- **action_activate_currency** (object)
- **action_activate_currency** (object)
- **action_open_business_doc** (object)
- **open_payments** (object)
- **open_reconcile_view** (object)
- **open_created_caba_entries** (object)
- **Update Taxes and Accounts** (object)
- **refresh_invoice_currency_rate** (object)
- **Catalog** (object)
- **Cut-Off** (object)


**Filtros de búsqueda (account.view_account_move_filter):**

- **Unposted** (`[('state', '=', 'draft')]`)
- **Posted** (`[('state', '=', 'posted')]`)
- **Not Secured** (`[('secured', '=', False), ('state', '=', 'posted')]`)
- **Reversed** (`[('payment_state', '=', 'reversed')]`)
- **To Check** (`[('checked', '=', False), ('state', '!=', 'draft')]`)
- **Sales** (`[('journal_id.type', '=', 'sale')]`)
- **Purchases** (`[('journal_id.type', '=', 'purchase')]`)
- **Bank** (`[('journal_id.type', '=', 'bank')]`)
- **Cash** (`[('journal_id.type', '=', 'cash')]`)
- **Credit** (`[('journal_id.type', '=', 'credit')]`)
- **Miscellaneous** (`[('journal_id.type', '=', 'general')]`)
- **Date**
- **Invoice Date**


*Agrupar por:*
- Partner
- Journal
- Status
- Payment Method
- Date
- Invoice Date
- Company


**Filtros de búsqueda (account.view_account_invoice_filter):**

- **myinvoices** (`[('invoice_user_id', '=', uid)]`)
- **Draft** (`[('state','=','draft')]`)
- **Posted** (`[('state', '=', 'posted')]`)
- **Cancelled** (`[('state', '=', 'cancel')]`)
- **Not Secured** (`[('secured', '=', False), ('state', '=', 'posted')]`)
- **Not Sent** (`[('is_move_sent', '=', False)]`)
- **Invoices** (`[('move_type', '=', 'out_invoice')]`)
- **Credit Notes** (`[('move_type', '=', 'out_refund')]`)
- **To Check** (`[('checked', '=', False), ('state', '!=', 'draft')]`)
- **To pay** (`[('state', '=', 'posted'), ('payment_state', 'in', ('not_paid', 'partial')), ('move_type', '!=', 'entry')]`)
- **In payment** (`[('state', '=', 'posted'), ('payment_state', '=', 'in_payment')]`)
- **Overdue** (`[                         ('invoice_date_due', '<', time.strftime('%Y-%m-%d')),                         ('state', '=', 'posted'),                         ('payment_state', 'in', ('not_paid', 'partial')),                         ('move_type', '!=', 'entry')                     ]`)
- **Invoice Date**
- **Accounting Date**
- **Due Date**
- **Late Activities** (`[('my_activity_date_deadline', '<', context_today().strftime('%Y-%m-%d'))]`)
- **Today Activities** (`[('my_activity_date_deadline', '=', context_today().strftime('%Y-%m-%d'))]`)
- **Future Activities** (`[('my_activity_date_deadline', '>', context_today().strftime('%Y-%m-%d'))]`)


*Agrupar por:*
- Salesperson
- Partner
- Status
- Payment Method
- Journal
- Company
- Invoice Date
- Due Date
- Accounting Date
- Sequence Prefix



### account.lock_exception


- Hereda de: Base



#### Campos
- **active** (Boolean)
- **state** (Selection)
- **company_id** (Many2one) → res.company
- **user_id** (Many2one) → res.users
- **reason** (Char)
- **end_datetime** (Datetime)
- **lock_date_field** (Selection)
- **lock_date** (Date)
- **company_lock_date** (Date)
- **fiscalyear_lock_date** (Date)
- **tax_lock_date** (Date)
- **sale_lock_date** (Date)
- **purchase_lock_date** (Date)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | account.lock_exception.form | `account.view_account_lock_exception_form` | - |



**Botones (account.view_account_lock_exception_form):**
- **Revoke** (object)
- **action_show_audit_trail_during_exception** (object)



### account.journal.group


- Hereda de: Base



#### Campos
- **name** (Char) → Ledger group
- **company_id** (Many2one) → res.company
- **excluded_journal_ids** (Many2many) → account.journal
- **sequence** (Integer)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | account.journal.group.list | `account.view_account_journal_group_tree` | - |
| form | account.journal.group.form | `account.view_account_journal_group_form` | - |




### account.journal


- Hereda de:


  - portal.mixin

  - mail.alias.mixin.optional

  - mail.thread

  - mail.activity.mixin





#### Campos
- **name** (Char)
- **code** (Char)
- **active** (Boolean)
- **type** (Selection)
- **autocheck_on_post** (Boolean)
- **account_control_ids** (Many2many) → account.account
- **default_account_type** (Char)
- **default_account_id** (Many2one) → account.account
- **suspense_account_id** (Many2one) → account.account
- **restrict_mode_hash_table** (Boolean)
- **sequence** (Integer)
- **invoice_reference_type** (Selection)
- **invoice_reference_model** (Selection)
- **currency_id** (Many2one) → res.currency
- **company_id** (Many2one) → res.company
- **country_code** (Char)
- **refund_sequence** (Boolean)
- **payment_sequence** (Boolean)
- **sequence_override_regex** (Text)
- **inbound_payment_method_line_ids** (One2many) → account.payment.method.line
- **outbound_payment_method_line_ids** (One2many) → account.payment.method.line
- **profit_account_id** (Many2one) → account.account
- **loss_account_id** (Many2one) → account.account
- **company_partner_id** (Many2one) → res.partner
- **bank_account_id** (Many2one) → res.partner.bank
- **bank_statements_source** (Selection)
- **bank_acc_number** (Char)
- **bank_id** (Many2one) → res.bank
- **alias_id** (Many2one)
- **journal_group_ids** (Many2many) → account.journal.group
- **available_payment_method_ids** (Many2many) → account.payment.method
- **selected_payment_method_codes** (Char)
- **accounting_date** (Date)
- **display_alias_fields** (Boolean)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| kanban | account.journal.dashboard.kanban | `account.account_journal_dashboard_kanban_view` | - |
| list | account.journal.list | `account.view_account_journal_tree` | - |
| form | account.journal.form | `account.view_account_journal_form` | - |
| kanban | account.journal.kanban | `account.account_journal_view_kanban` | - |
| search | account.journal.search | `account.view_account_journal_search` | - |



**Botones (account.view_account_journal_form):**
- **%(action_account_moves_all_a)d** (action)


**Filtros de búsqueda (account.view_account_journal_search):**

- **Favorites** (`[('show_on_dashboard', '=', True)]`)
- **Sales** (`[('type', '=', 'sale')]`)
- **Purchases** (`[('type', '=', 'purchase')]`)
- **Liquidity** (`[('type', 'in', ('cash', 'bank', 'credit'))]`)
- **Miscellaneous** (`[('type', 'not in', ['sale', 'purchase', 'cash', 'bank', 'credit'])]`)
- **Archived** (`[('active', '=', False)]`)



### mail.message


- Hereda de:

  - mail.message




#### Campos
- **account_audit_log_preview** (Text)
- **account_audit_log_move_id** (Many2one) → account.move
- **account_audit_log_partner_id** (Many2one) → res.partner
- **account_audit_log_account_id** (Many2one) → account.account
- **account_audit_log_tax_id** (Many2one) → account.tax
- **account_audit_log_company_id** (Many2one) → res.company
- **account_audit_log_activated** (Boolean)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | mail.message.list.inherit.audit.log | `account.view_message_tree_audit_log` | - |
| search | mail.message.search | `account.view_message_tree_audit_log_search` | - |



**Filtros de búsqueda (account.view_message_tree_audit_log_search):**

- **Journal Entry** (`[('model', '=', 'account.move')]`)
- **Account** (`[('model', '=', 'account.account')]`)
- **Taxes** (`[('model', '=', 'account.tax')]`)
- **Partners** (`[('model', '=', 'res.partner')]`)
- **Company** (`[('model', '=', 'res.company')]`)
- **Update Only** (`[('tracking_value_ids', '!=', False)]`)
- **Create Only** (`[('tracking_value_ids', '=', False)]`)
- **Date**


*Agrupar por:*
- Date
- Record



### mail.tracking.value


- Hereda de:

  - mail.tracking.value




- No agrega campos




### account.bank.statement.line


- Hereda de: Base



#### Campos
- **move_id** (Many2one) → account.move
- **journal_id** (Many2one) → account.journal
- **company_id** (Many2one) → res.company
- **statement_id** (Many2one) → account.bank.statement
- **payment_ids** (Many2many) → account.payment
- **sequence** (Integer)
- **partner_id** (Many2one) → res.partner
- **account_number** (Char)
- **partner_name** (Char)
- **transaction_type** (Char)
- **payment_ref** (Char)
- **currency_id** (Many2one) → res.currency
- **amount** (Monetary)
- **running_balance** (Monetary)
- **foreign_currency_id** (Many2one) → res.currency
- **amount_currency** (Monetary)
- **amount_residual** (Float)
- **country_code** (Char)
- **internal_index** (Char)
- **is_reconciled** (Boolean)
- **statement_complete** (Boolean)
- **statement_valid** (Boolean)
- **statement_balance_end_real** (Monetary)
- **statement_name** (Char)
- **transaction_details** (Json)





### account.move


- Hereda de:


  - account.move





#### Campos
- **statement_line_ids** (One2many) → account.bank.statement.line





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | account.move.list | `account.view_move_tree` | - |
| list | account.invoice.list | `account.view_invoice_tree` | - |
| kanban | account.move.kanban | `account.view_account_move_kanban` | - |
| form | account.move.form | `account.view_move_form` | - |
| activity | account.move.view.activity | `account.account_move_view_activity` | - |
| search | account.move.select | `account.view_account_move_filter` | - |
| search | account.invoice.select | `account.view_account_invoice_filter` | - |



**Botones (account.view_move_form):**
- **Post** (object) - Grupos: `account.group_account_invoice`
- **Confirm** (object) - Grupos: `account.group_account_invoice`
- **Send** (object)
- **Send** (object)
- **Print** (object)
- **Print** (object)
- **Pay** (object) - Grupos: `account.group_account_invoice`
- **Pay** (object) - Grupos: `account.group_account_invoice`
- **Preview** (object)
- **Reverse Entry** (action) - Grupos: `account.group_account_invoice`
- **Credit Note** (object) - Grupos: `account.group_account_invoice`
- **Cancel Entry** (object) - Grupos: `account.group_account_invoice`
- **Cancel** (object) - Grupos: `account.group_account_invoice`
- **Reset to Draft** (object) - Grupos: `account.group_account_invoice`
- **Lock** (object) - Grupos: `account.group_account_invoice`
- **Request Cancel** (object) - Grupos: `account.group_account_invoice`
- **Set as Checked** (object) - Grupos: `account.group_account_invoice`
- **action_activate_currency** (object)
- **action_activate_currency** (object)
- **action_open_business_doc** (object)
- **open_payments** (object)
- **open_reconcile_view** (object)
- **open_created_caba_entries** (object)
- **Update Taxes and Accounts** (object)
- **refresh_invoice_currency_rate** (object)
- **Catalog** (object)
- **Cut-Off** (object)


**Filtros de búsqueda (account.view_account_move_filter):**

- **Unposted** (`[('state', '=', 'draft')]`)
- **Posted** (`[('state', '=', 'posted')]`)
- **Not Secured** (`[('secured', '=', False), ('state', '=', 'posted')]`)
- **Reversed** (`[('payment_state', '=', 'reversed')]`)
- **To Check** (`[('checked', '=', False), ('state', '!=', 'draft')]`)
- **Sales** (`[('journal_id.type', '=', 'sale')]`)
- **Purchases** (`[('journal_id.type', '=', 'purchase')]`)
- **Bank** (`[('journal_id.type', '=', 'bank')]`)
- **Cash** (`[('journal_id.type', '=', 'cash')]`)
- **Credit** (`[('journal_id.type', '=', 'credit')]`)
- **Miscellaneous** (`[('journal_id.type', '=', 'general')]`)
- **Date**
- **Invoice Date**


*Agrupar por:*
- Partner
- Journal
- Status
- Payment Method
- Date
- Invoice Date
- Company


**Filtros de búsqueda (account.view_account_invoice_filter):**

- **myinvoices** (`[('invoice_user_id', '=', uid)]`)
- **Draft** (`[('state','=','draft')]`)
- **Posted** (`[('state', '=', 'posted')]`)
- **Cancelled** (`[('state', '=', 'cancel')]`)
- **Not Secured** (`[('secured', '=', False), ('state', '=', 'posted')]`)
- **Not Sent** (`[('is_move_sent', '=', False)]`)
- **Invoices** (`[('move_type', '=', 'out_invoice')]`)
- **Credit Notes** (`[('move_type', '=', 'out_refund')]`)
- **To Check** (`[('checked', '=', False), ('state', '!=', 'draft')]`)
- **To pay** (`[('state', '=', 'posted'), ('payment_state', 'in', ('not_paid', 'partial')), ('move_type', '!=', 'entry')]`)
- **In payment** (`[('state', '=', 'posted'), ('payment_state', '=', 'in_payment')]`)
- **Overdue** (`[                         ('invoice_date_due', '<', time.strftime('%Y-%m-%d')),                         ('state', '=', 'posted'),                         ('payment_state', 'in', ('not_paid', 'partial')),                         ('move_type', '!=', 'entry')                     ]`)
- **Invoice Date**
- **Accounting Date**
- **Due Date**
- **Late Activities** (`[('my_activity_date_deadline', '<', context_today().strftime('%Y-%m-%d'))]`)
- **Today Activities** (`[('my_activity_date_deadline', '=', context_today().strftime('%Y-%m-%d'))]`)
- **Future Activities** (`[('my_activity_date_deadline', '>', context_today().strftime('%Y-%m-%d'))]`)


*Agrupar por:*
- Salesperson
- Partner
- Status
- Payment Method
- Journal
- Company
- Invoice Date
- Due Date
- Accounting Date
- Sequence Prefix



### res.groups


- Hereda de:

  - res.groups




- No agrega campos




### account.cash.rounding


- Hereda de: Base



#### Campos
- **name** (Char)
- **rounding** (Float)
- **strategy** (Selection)
- **profit_account_id** (Many2one) → account.account
- **loss_account_id** (Many2one) → account.account
- **rounding_method** (Selection)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | account.cash.rounding.form | `account.rounding_form_view` | - |
| search | account.cash.rounding.search | `account.rounding_search_view` | - |
| list | account.cash.rounding.list | `account.rounding_tree_view` | - |




### account.root


- Hereda de: Base



#### Campos
- **name** (Char)
- **parent_id** (Many2one) → account.root





### account.fiscal.position


- Hereda de: Base



#### Campos
- **sequence** (Integer)
- **name** (Char)
- **active** (Boolean)
- **company_id** (Many2one) → res.company
- **account_ids** (One2many) → account.fiscal.position.account
- **account_map** (Binary)
- **tax_ids** (One2many) → account.fiscal.position.tax
- **tax_map** (Binary)
- **note** (Html) → Notes
- **auto_apply** (Boolean)
- **vat_required** (Boolean)
- **company_country_id** (Many2one)
- **fiscal_country_codes** (Char)
- **country_id** (Many2one) → res.country
- **country_group_id** (Many2one) → res.country.group
- **state_ids** (Many2many) → res.country.state
- **zip_from** (Char)
- **zip_to** (Char)
- **states_count** (Integer)
- **foreign_vat** (Char)
- **foreign_vat_header_mode** (Selection)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | account.fiscal.position.form | `account.view_account_position_form` | - |
| search | account.fiscal.position.filter | `account.view_account_position_filter` | - |
| list | account.fiscal.position.list | `account.view_account_position_tree` | - |



**Botones (account.view_account_position_form):**
- **here** (object)


**Filtros de búsqueda (account.view_account_position_filter):**

- **Archived** (`[('active', '=', False)]`)



### account.fiscal.position.tax


- Hereda de: Base



#### Campos
- **position_id** (Many2one) → account.fiscal.position
- **company_id** (Many2one) → res.company
- **tax_src_id** (Many2one) → account.tax
- **tax_dest_id** (Many2one) → account.tax
- **tax_dest_active** (Boolean)





### account.fiscal.position.account


- Hereda de: Base



#### Campos
- **position_id** (Many2one) → account.fiscal.position
- **company_id** (Many2one) → res.company
- **account_src_id** (Many2one) → account.account
- **account_dest_id** (Many2one) → account.account





### res.partner


- Hereda de:

  - res.partner




#### Campos
- **fiscal_country_codes** (Char)
- **partner_vat_placeholder** (Char)
- **partner_company_registry_placeholder** (Char)
- **duplicate_bank_partner_ids** (Many2many)
- **name** (Char)
- **credit** (Monetary)
- **credit_to_invoice** (Monetary)
- **credit_limit** (Float)
- **use_partner_credit_limit** (Boolean)
- **show_credit_limit** (Boolean)
- **days_sales_outstanding** (Float)
- **debit** (Monetary)
- **debit_limit** (Monetary) → Payable Limit
- **total_invoiced** (Monetary)
- **currency_id** (Many2one) → res.currency
- **journal_item_count** (Integer)
- **property_account_payable_id** (Many2one) → account.account
- **property_account_receivable_id** (Many2one) → account.account
- **property_account_position_id** (Many2one) → account.fiscal.position
- **property_payment_term_id** (Many2one) → account.payment.term
- **property_supplier_payment_term_id** (Many2one) → account.payment.term
- **ref_company_ids** (One2many) → res.company
- **supplier_invoice_count** (Integer)
- **invoice_ids** (One2many) → account.move
- **contract_ids** (One2many) → account.analytic.account
- **bank_account_count** (Integer)
- **trust** (Selection)
- **ignore_abnormal_invoice_date** (Boolean)
- **ignore_abnormal_invoice_amount** (Boolean)
- **invoice_warn** (Selection)
- **invoice_warn_msg** (Text) → Message for Invoice
- **invoice_sending_method** (Selection)
- **invoice_edi_format** (Selection)
- **invoice_edi_format_store** (Char)
- **display_invoice_edi_format** (Boolean)
- **invoice_template_pdf_report_id** (Many2one) → ir.actions.report
- **display_invoice_template_pdf_report_id** (Boolean)
- **supplier_rank** (Integer)
- **customer_rank** (Integer)
- **autopost_bills** (Selection)
- **duplicated_bank_account_partners_count** (Integer)
- **is_coa_installed** (Boolean)
- **property_outbound_payment_method_line_id** (Many2one) → account.payment.method.line
- **property_inbound_payment_method_line_id** (Many2one) → account.payment.method.line





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | res.partner.property.form.inherit | `account.view_partner_property_form` | base.view_partner_form |
| list | res.partner.list | `account.partner_missing_account_list_view` | - |




### account.chart.template


- Hereda de:

  - account.chart.template




- No agrega campos




### product.category


- Hereda de:

  - product.category




#### Campos
- **property_account_income_categ_id** (Many2one) → account.account
- **property_account_expense_categ_id** (Many2one) → account.account





### product.template


- Hereda de:

  - product.template




#### Campos
- **taxes_id** (Many2many) → account.tax
- **tax_string** (Char)
- **supplier_taxes_id** (Many2many) → account.tax
- **property_account_income_id** (Many2one) → account.account
- **property_account_expense_id** (Many2one) → account.account
- **account_tag_ids** (Many2many) → account.account.tag
- **fiscal_country_codes** (Char)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | product.template.list | `account.product_template_view_tree` | - |




### product.product


- Hereda de:

  - product.product




#### Campos
- **tax_string** (Char)





### ir.attachment


- Hereda de:

  - ir.attachment




- No agrega campos




### base.partner.merge.automatic.wizard


- Hereda de:

  - base.partner.merge.automatic.wizard




- No agrega campos




### account.journal


- Hereda de:

  - account.journal




#### Campos
- **kanban_dashboard** (Text)
- **kanban_dashboard_graph** (Text)
- **json_activity_data** (Text)
- **show_on_dashboard** (Boolean)
- **color** (Integer) → Color Index
- **current_statement_balance** (Monetary)
- **has_statement_lines** (Boolean)
- **entries_count** (Integer)
- **has_posted_entries** (Boolean)
- **has_entries** (Boolean)
- **has_sequence_holes** (Boolean)
- **has_unhashed_entries** (Boolean)
- **last_statement_id** (Many2one) → account.bank.statement





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| kanban | account.journal.dashboard.kanban | `account.account_journal_dashboard_kanban_view` | - |
| list | account.journal.list | `account.view_account_journal_tree` | - |
| form | account.journal.form | `account.view_account_journal_form` | - |
| kanban | account.journal.kanban | `account.account_journal_view_kanban` | - |
| search | account.journal.search | `account.view_account_journal_search` | - |



**Botones (account.view_account_journal_form):**
- **%(action_account_moves_all_a)d** (action)


**Filtros de búsqueda (account.view_account_journal_search):**

- **Favorites** (`[('show_on_dashboard', '=', True)]`)
- **Sales** (`[('type', '=', 'sale')]`)
- **Purchases** (`[('type', '=', 'purchase')]`)
- **Liquidity** (`[('type', 'in', ('cash', 'bank', 'credit'))]`)
- **Miscellaneous** (`[('type', 'not in', ['sale', 'purchase', 'cash', 'bank', 'credit'])]`)
- **Archived** (`[('active', '=', False)]`)



### onboarding.onboarding


- Hereda de:

  - onboarding.onboarding




- No agrega campos




### account.code.mapping


- Hereda de: Base



#### Campos
- **account_id** (Many2one) → account.account
- **company_id** (Many2one) → res.company
- **code** (Char)





### account.tax.group


- Hereda de: Base



#### Campos
- **name** (Char)
- **sequence** (Integer)
- **company_id** (Many2one) → res.company
- **tax_payable_account_id** (Many2one) → account.account
- **tax_receivable_account_id** (Many2one) → account.account
- **advance_tax_payment_account_id** (Many2one) → account.account
- **country_id** (Many2one) → res.country
- **country_code** (Char)
- **preceding_subtotal** (Char)
- **pos_receipt_label** (Char)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| search | account.tax.group.search.filters | `account.account_tax_group_view_search` | - |
| list | account.tax.group.list | `account.view_tax_group_tree` | - |
| form | account.tax.group.form | `account.view_tax_group_form` | - |



**Filtros de búsqueda (account.account_tax_group_view_search):**


*Agrupar por:*
- Country



### account.tax


- Hereda de:


  - mail.thread





#### Campos
- **name** (Char)
- **name_searchable** (Char)
- **type_tax_use** (Selection)
- **tax_scope** (Selection)
- **amount_type** (Selection)
- **active** (Boolean)
- **company_id** (Many2one) → res.company
- **children_tax_ids** (Many2many) → account.tax
- **sequence** (Integer)
- **amount** (Float)
- **description** (Html)
- **invoice_label** (Char)
- **price_include** (Boolean)
- **company_price_include** (Selection)
- **price_include_override** (Selection)
- **include_base_amount** (Boolean)
- **is_base_affected** (Boolean)
- **analytic** (Boolean)
- **tax_group_id** (Many2one) → account.tax.group
- **hide_tax_exigibility** (Boolean)
- **tax_exigibility** (Selection)
- **cash_basis_transition_account_id** (Many2one) → account.account
- **invoice_repartition_line_ids** (One2many) → account.tax.repartition.line
- **refund_repartition_line_ids** (One2many) → account.tax.repartition.line
- **repartition_line_ids** (One2many) → account.tax.repartition.line
- **country_id** (Many2one) → res.country
- **country_code** (Char)
- **is_used** (Boolean)
- **repartition_lines_str** (Char)
- **invoice_legal_notes** (Html)
- **has_negative_factor** (Boolean)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | account.tax.list | `account.view_tax_tree` | - |
| list | account.invoice.line.tax.search | `account.account_tax_view_tree` | - |
| kanban | account.tax.kanban | `account.view_tax_kanban` | - |
| search | account.tax.search | `account.view_account_tax_search` | - |
| search | account.tax.search.filters | `account.account_tax_view_search` | - |
| form | account.tax.form | `account.view_tax_form` | - |



**Filtros de búsqueda (account.view_account_tax_search):**

- **Sale** (`[('type_tax_use','=','sale')]`)
- **Purchase** (`[('type_tax_use','=','purchase')]`)
- **Services** (`[('tax_scope','=','service')]`)
- **Goods** (`[('tax_scope','=','consu')]`)
- **Active** (`[('active','=',True)]`)
- **Inactive** (`[('active','=',False)]`)


*Agrupar por:*
- Company
- Tax Type
- Tax Scope



### account.tax.repartition.line


- Hereda de: Base



#### Campos
- **factor_percent** (Float)
- **factor** (Float)
- **repartition_type** (Selection)
- **document_type** (Selection)
- **account_id** (Many2one) → account.account
- **tag_ids** (Many2many) → account.account.tag
- **tax_id** (Many2one) → account.tax
- **company_id** (Many2one) → res.company
- **sequence** (Integer)
- **use_in_tax_closing** (Boolean)
- **tag_ids_domain** (Binary)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | account.tax.repartition.line.list | `account.tax_repartition_line_tree` | - |




### res.config.settings


- Hereda de:

  - res.config.settings




#### Campos
- **has_accounting_entries** (Boolean)
- **currency_id** (Many2one) → res.currency
- **currency_exchange_journal_id** (Many2one) → account.journal
- **income_currency_exchange_account_id** (Many2one) → account.account
- **expense_currency_exchange_account_id** (Many2one) → account.account
- **has_chart_of_accounts** (Boolean)
- **chart_template** (Selection)
- **sale_tax_id** (Many2one) → account.tax
- **purchase_tax_id** (Many2one) → account.tax
- **account_price_include** (Selection)
- **tax_calculation_rounding_method** (Selection)
- **account_journal_suspense_account_id** (Many2one) → account.account
- **transfer_account_id** (Many2one) → account.account
- **module_account_accountant** (Boolean)
- **group_warning_account** (Boolean)
- **group_cash_rounding** (Boolean)
- **group_show_sale_receipts** (Boolean)
- **group_show_purchase_receipts** (Boolean)
- **module_account_budget** (Boolean)
- **module_account_payment** (Boolean)
- **module_account_reports** (Boolean) → Dynamic Reports
- **module_account_check_printing** (Boolean) → Allow check printing and deposits
- **module_account_batch_payment** (Boolean)
- **module_account_iso20022** (Boolean)
- **module_account_sepa_direct_debit** (Boolean)
- **module_account_bank_statement_import_qif** (Boolean) → Import .qif files
- **module_account_bank_statement_import_ofx** (Boolean) → Import in .ofx format
- **module_account_bank_statement_import_csv** (Boolean) → Import in .csv, .xls, and .xlsx format
- **module_account_bank_statement_import_camt** (Boolean) → Import in CAMT.053 format
- **module_currency_rate_live** (Boolean)
- **module_account_intrastat** (Boolean)
- **module_product_margin** (Boolean)
- **module_l10n_eu_oss** (Boolean)
- **module_account_extract** (Boolean)
- **module_account_invoice_extract** (Boolean) → Invoice Digitization
- **module_account_bank_statement_extract** (Boolean) → Bank Statement Digitization
- **module_snailmail_account** (Boolean)
- **module_account_peppol** (Boolean)
- **tax_exigibility** (Boolean)
- **tax_cash_basis_journal_id** (Many2one) → account.journal
- **account_cash_basis_base_account_id** (Many2one) → account.account
- **account_fiscal_country_id** (Many2one)
- **qr_code** (Boolean)
- **incoterm_id** (Many2one) → account.incoterms
- **invoice_terms** (Html)
- **invoice_terms_html** (Html)
- **terms_type** (Selection)
- **display_invoice_amount_total_words** (Boolean)
- **display_invoice_tax_company_currency** (Boolean)
- **preview_ready** (Boolean)
- **use_invoice_terms** (Boolean)
- **account_use_credit_limit** (Boolean)
- **account_default_credit_limit** (Monetary)
- **country_code** (Char)
- **account_storno** (Boolean)
- **group_sale_delivery_address** (Boolean) → Customer Addresses
- **quick_edit_mode** (Selection)
- **account_journal_early_pay_discount_loss_account_id** (Many2one) → account.account
- **account_journal_early_pay_discount_gain_account_id** (Many2one) → account.account
- **account_discount_income_allocation_id** (Many2one) → account.account
- **account_discount_expense_allocation_id** (Many2one) → account.account
- **is_account_peppol_eligible** (Boolean)
- **check_account_audit_trail** (Boolean)
- **autopost_bills** (Boolean)





### mail.template


- Hereda de:

  - mail.template




- No agrega campos




### account.move.line


- Hereda de:

  - analytic.mixin




#### Campos
- **move_id** (Many2one) → account.move
- **journal_id** (Many2one)
- **journal_group_id** (Many2one) → account.journal.group
- **company_id** (Many2one)
- **company_currency_id** (Many2one)
- **move_name** (Char)
- **parent_state** (Selection)
- **date** (Date)
- **invoice_date** (Date)
- **ref** (Char)
- **is_storno** (Boolean)
- **sequence** (Integer)
- **move_type** (Selection)
- **account_id** (Many2one) → account.account
- **account_name** (Char)
- **account_code** (Char)
- **name** (Char)
- **debit** (Monetary)
- **credit** (Monetary)
- **balance** (Monetary)
- **cumulated_balance** (Monetary)
- **currency_rate** (Float)
- **amount_currency** (Monetary)
- **currency_id** (Many2one) → res.currency
- **is_same_currency** (Boolean)
- **partner_id** (Many2one) → res.partner
- **is_imported** (Boolean)
- **reconcile_model_id** (Many2one) → account.reconcile.model
- **payment_id** (Many2one) → account.payment
- **statement_line_id** (Many2one) → account.bank.statement.line
- **statement_id** (Many2one)
- **commercial_partner_country** (Many2one)
- **tax_ids** (Many2many) → account.tax
- **group_tax_id** (Many2one) → account.tax
- **tax_line_id** (Many2one) → account.tax
- **tax_group_id** (Many2one)
- **tax_base_amount** (Monetary)
- **tax_repartition_line_id** (Many2one) → account.tax.repartition.line
- **tax_tag_ids** (Many2many) → account.account.tag
- **tax_tag_invert** (Boolean)
- **amount_residual** (Monetary)
- **amount_residual_currency** (Monetary)
- **reconciled** (Boolean)
- **full_reconcile_id** (Many2one) → account.full.reconcile
- **matched_debit_ids** (One2many) → account.partial.reconcile
- **matched_credit_ids** (One2many) → account.partial.reconcile
- **matching_number** (Char)
- **is_account_reconcile** (Boolean)
- **account_type** (Selection)
- **account_internal_group** (Selection)
- **account_root_id** (Many2one)
- **product_category_id** (Many2one)
- **display_type** (Selection)
- **product_id** (Many2one) → product.product
- **product_uom_id** (Many2one) → uom.uom
- **product_uom_category_id** (Many2one) → uom.category
- **quantity** (Float)
- **date_maturity** (Date)
- **price_unit** (Float)
- **price_subtotal** (Monetary)
- **price_total** (Monetary)
- **discount** (Float)
- **tax_calculation_rounding_method** (Selection)
- **term_key** (Binary)
- **epd_key** (Binary)
- **epd_needed** (Binary)
- **epd_dirty** (Boolean)
- **discount_allocation_key** (Binary)
- **discount_allocation_needed** (Binary)
- **discount_allocation_dirty** (Boolean)
- **analytic_line_ids** (One2many) → account.analytic.line
- **analytic_distribution** (Json)
- **discount_date** (Date)
- **discount_amount_currency** (Monetary)
- **discount_balance** (Monetary)
- **payment_date** (Date)
- **is_refund** (Boolean)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | account.move.line.form | `account.view_move_line_form` | - |
| kanban | account.move.line.kanban | `account.account_move_line_view_kanban` | - |
| pivot | account.move.line.pivot | `account.view_move_line_pivot` | - |
| list | account.move.line.list | `account.view_move_line_tree` | - |
| graph | account.move.line.graph | `account.account_move_line_graph_date` | - |
| search | account.move.line.search | `account.view_account_move_line_filter` | - |
| list | account.move.line.payment.list | `account.view_move_line_payment_tree` | - |
| search | account.move.line.payment.search | `account.view_account_move_line_payment_filter` | - |



**Botones (account.view_move_line_form):**
- **-> View partially reconciled entries** (object)


**Filtros de búsqueda (account.view_account_move_line_filter):**

- **Unposted** (`[('parent_state', '=', 'draft')]`)
- **Posted** (`[('parent_state', '=', 'posted')]`)
- **Not Secured** (`[('move_id.secured', '=', False), ('move_id.state', '=', 'posted')]`)
- **To check** (`[('move_id.checked', '=', False), ('parent_state', '!=', 'draft')]`)
- **Unreconciled** (`[('balance', '!=', 0), ('account_id.reconcile', '=', True), '|', ('matching_number', '=', False), ('matching_number', '=like', 'P%')]`)
- **With residual** (`[('amount_residual', '!=', 0), ('account_id.reconcile', '=', True)]`)
- **Sales** (`[('journal_id.type', '=', 'sale')]`)
- **Purchases** (`[('journal_id.type', '=', 'purchase')]`)
- **Bank** (`[('journal_id.type', '=', 'bank')]`)
- **Cash** (`[('journal_id.type', '=', 'cash')]`)
- **Credit** (`[('journal_id.type', '=', 'credit')]`)
- **Miscellaneous** (`[('journal_id.type', '=', 'general')]`)
- **Payable** (`[('account_id.account_type', '=', 'liability_payable'), ('account_id.non_trade', '=', False)]`)
- **Receivable** (`[('account_id.account_type', '=', 'asset_receivable'), ('account_id.non_trade', '=', False)]`)
- **Non Trade Payable** (`[('account_id.account_type', '=', 'liability_payable'), ('account_id.non_trade', '=', True)]`)
- **Non Trade Receivable** (`[('account_id.account_type', '=', 'asset_receivable'), ('account_id.non_trade', '=', True)]`)
- **P&L Accounts** (`[('account_id.internal_group', 'in', ('income', 'expense'))]`)
- **No Bank Transaction** (`[('statement_line_id', '=', False), ('payment_id', '=', False)]`)
- **Date**
- **Invoice Date**
- **Report Dates** (`[('date', '>=', context.get('date_from')), ('date', '<=', context.get('date_to'))]`)
- **Report Dates** (`[('date', '<=', context.get('date_to'))]`)
- **Analytic Accounts** (`[('analytic_distribution', 'in', context.get('analytic_ids'))]`)


*Agrupar por:*
- Journal Entry
- Account
- Partner
- Journal
- Date
- Invoice Date
- Taxes
- Tax Grid
- Matching


**Filtros de búsqueda (account.view_account_move_line_payment_filter):**

- **Posted** (`[('parent_state', '=', 'posted')]`)
- **Invoices** (`[('amount_residual', '>', '0')]`)
- **Credit Notes** (`[('amount_residual', '<', '0')]`)
- **Bills** (`[('amount_residual', '<', '0')]`)
- **Refunds** (`[('amount_residual', '>', '0')]`)
- **Invoice Date**
- **Next Payment Date**
- **Overdue** (`[('date_maturity', '<', time.strftime('%Y-%m-%d'))]`)
- **Early Discount** (`[('discount_date', '!=', False), ('discount_date', '>', time.strftime('%Y-%m-%d'))]`)
- **Report Dates** (`[('date', '>=', context.get('date_from')), ('date', '<=', context.get('date_to'))]`)
- **Report Dates** (`[('date', '<=', context.get('date_to'))]`)


*Agrupar por:*
- Currency
- Partner
- Journal
- Invoice Date
- Next Payment Date



### ir.ui.menu


- Hereda de:

  - ir.ui.menu




- No agrega campos




### sequence.mixin


- Hereda de: Base



#### Campos
- **sequence_prefix** (Char)
- **sequence_number** (Integer)





### account.account


- Hereda de:


  - mail.thread





#### Campos
- **name** (Char)
- **currency_id** (Many2one) → res.currency
- **company_currency_id** (Many2one) → res.currency
- **company_fiscal_country_code** (Char)
- **code** (Char)
- **code_store** (Char)
- **placeholder_code** (Char)
- **deprecated** (Boolean)
- **used** (Boolean)
- **account_type** (Selection)
- **include_initial_balance** (Boolean)
- **internal_group** (Selection)
- **reconcile** (Boolean)
- **tax_ids** (Many2many) → account.tax
- **note** (Text) → Internal Notes
- **company_ids** (Many2many) → res.company
- **code_mapping_ids** (One2many) → account.code.mapping
- **tag_ids** (Many2many) → account.account.tag
- **group_id** (Many2one) → account.group
- **root_id** (Many2one) → account.root
- **allowed_journal_ids** (Many2many) → account.journal
- **opening_debit** (Monetary)
- **opening_credit** (Monetary)
- **opening_balance** (Monetary)
- **current_balance** (Float)
- **related_taxes_amount** (Integer)
- **non_trade** (Boolean)
- **display_mapping_tab** (Boolean)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | account.account.form | `account.view_account_form` | - |
| list | account.account.list | `account.view_account_list` | - |
| kanban | account.account.kanban | `account.view_account_account_kanban` | - |
| search | account.account.search | `account.view_account_search` | - |
| list | account.setup.opening.move.line.list | `account.init_accounts_tree` | - |



**Botones (account.view_account_form):**
- **action_open_related_taxes** (object)
- **account.action_move_line_select** (action)


**Filtros de búsqueda (account.view_account_search):**

- **Receivable** (`[('account_type','=','asset_receivable')]`)
- **Payable** (`[('account_type','=','liability_payable')]`)
- **Equity** (`[('internal_group','=', 'equity')]`)
- **Assets** (`[('internal_group','=', 'asset')]`)
- **Liability** (`[('internal_group','=', 'liability')]`)
- **Income** (`[('internal_group','=', 'income')]`)
- **Expenses** (`[('internal_group','=', 'expense')]`)
- **Account with Entries** (`[('used', '=', True)]`)
- **Active Account** (`[('deprecated', '=', False)]`)


*Agrupar por:*
- Account Type



### account.group


- Hereda de: Base



#### Campos
- **parent_id** (Many2one) → account.group
- **name** (Char)
- **code_prefix_start** (Char)
- **code_prefix_end** (Char)
- **company_id** (Many2one) → res.company





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | account.group.form | `account.view_account_group_form` | - |
| search | account.group.search | `account.view_account_group_search` | - |
| list | account.group.list | `account.view_account_group_tree` | - |




### account.chart.template


- Hereda de: Base



- No agrega campos




### account.analytic.applicability


- Hereda de:

  - account.analytic.applicability




#### Campos
- **business_domain** (Selection)
- **account_prefix** (Char)
- **product_categ_id** (Many2one) → product.category
- **display_account_prefix** (Boolean)
- **account_prefix_placeholder** (Char)





### account.payment.term


- Hereda de: Base



#### Campos
- **name** (Char)
- **active** (Boolean)
- **note** (Html)
- **line_ids** (One2many) → account.payment.term.line
- **company_id** (Many2one) → res.company
- **fiscal_country_codes** (Char)
- **sequence** (Integer)
- **currency_id** (Many2one) → res.currency
- **display_on_invoice** (Boolean)
- **example_amount** (Monetary)
- **example_date** (Date)
- **example_invalid** (Boolean)
- **example_preview** (Html)
- **example_preview_discount** (Html)
- **discount_percentage** (Float)
- **discount_days** (Integer)
- **early_pay_discount_computation** (Selection)
- **early_discount** (Boolean)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| search | account.payment.term.search | `account.view_payment_term_search` | - |
| list | account.payment.term.list | `account.view_payment_term_tree` | - |
| form | account.payment.term.form | `account.view_payment_term_form` | - |
| kanban | account.payment.term.kanban | `account.view_account_payment_term_kanban` | - |



**Filtros de búsqueda (account.view_payment_term_search):**

- **Archived** (`[('active', '=', False)]`)



### account.payment.term.line


- Hereda de: Base



#### Campos
- **value** (Selection)
- **value_amount** (Float)
- **delay_type** (Selection)
- **display_days_next_month** (Boolean)
- **days_next_month** (Char)
- **nb_days** (Integer)
- **payment_id** (Many2one) → account.payment.term





### account.account.tag


- Hereda de: Base



#### Campos
- **name** (Char) → Tag Name
- **applicability** (Selection)
- **color** (Integer) → Color Index
- **active** (Boolean)
- **tax_negate** (Boolean)
- **country_id** (Many2one) → res.country





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | Tags | `account.account_tag_view_form` | - |
| list | Tags | `account.account_tag_view_tree` | - |
| search | account.tag.view.search | `account.account_tag_view_search` | - |



**Filtros de búsqueda (account.account_tag_view_search):**

- **Archived** (`[('active', '=', False)]`)



### account.reconcile.model.partner.mapping


- Hereda de: Base



#### Campos
- **model_id** (Many2one) → account.reconcile.model
- **company_id** (Many2one)
- **partner_id** (Many2one) → res.partner
- **payment_ref_regex** (Char)
- **narration_regex** (Char)





### account.reconcile.model.line


- Hereda de:

  - analytic.mixin




#### Campos
- **model_id** (Many2one) → account.reconcile.model
- **allow_payment_tolerance** (Boolean)
- **payment_tolerance_param** (Float)
- **rule_type** (Selection)
- **company_id** (Many2one)
- **sequence** (Integer)
- **account_id** (Many2one) → account.account
- **journal_id** (Many2one) → account.journal
- **label** (Char)
- **amount_type** (Selection)
- **show_force_tax_included** (Boolean)
- **force_tax_included** (Boolean)
- **amount** (Float)
- **amount_string** (Char)
- **tax_ids** (Many2many) → account.tax





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | account.reconcile.model.line.form | `account.view_account_reconcile_model_line_form` | - |




### account.reconcile.model


- Hereda de:


  - mail.thread





#### Campos
- **active** (Boolean)
- **name** (Char)
- **sequence** (Integer)
- **company_id** (Many2one) → res.company
- **rule_type** (Selection)
- **auto_reconcile** (Boolean)
- **to_check** (Boolean)
- **matching_order** (Selection)
- **counterpart_type** (Selection)
- **match_text_location_label** (Boolean)
- **match_text_location_note** (Boolean)
- **match_text_location_reference** (Boolean)
- **match_journal_ids** (Many2many) → account.journal
- **match_nature** (Selection)
- **match_amount** (Selection)
- **match_amount_min** (Float)
- **match_amount_max** (Float)
- **match_label** (Selection)
- **match_label_param** (Char)
- **match_note** (Selection)
- **match_note_param** (Char)
- **match_transaction_type** (Selection)
- **match_transaction_type_param** (Char)
- **match_same_currency** (Boolean)
- **allow_payment_tolerance** (Boolean)
- **payment_tolerance_param** (Float)
- **payment_tolerance_type** (Selection)
- **match_partner** (Boolean)
- **match_partner_ids** (Many2many) → res.partner
- **match_partner_category_ids** (Many2many) → res.partner.category
- **line_ids** (One2many) → account.reconcile.model.line
- **partner_mapping_line_ids** (One2many) → account.reconcile.model.partner.mapping
- **past_months_limit** (Integer)
- **decimal_separator** (Char)
- **show_decimal_separator** (Boolean)
- **number_entries** (Integer)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | account.reconcile.model.list | `account.view_account_reconcile_model_tree` | - |
| form | account.reconcile.model.form | `account.view_account_reconcile_model_form` | - |
| search | account.reconcile.model.search | `account.view_account_reconcile_model_search` | - |



**Botones (account.view_account_reconcile_model_form):**
- **action_reconcile_stat** (object)


**Filtros de búsqueda (account.view_account_reconcile_model_search):**

- **Matching rules** (`[('rule_type', '=', 'invoice_matching')]`)
- **Counterpart rules** (`[('rule_type', '=', 'writeoff_suggestion')]`)
- **Counterpart buttons** (`[('rule_type', '=', 'writeoff_button')]`)
- **Auto validate** (`[('auto_reconcile', '=', True)]`)
- **With Partner matching** (`[('match_partner', '=', True)]`)
- **With tax** (`[('line_ids.tax_ids', '!=', False)]`)
- **Archived** (`[('active', '=', False)]`)


*Agrupar por:*
- Type
- Journals Availability
- Auto-validate



### decimal.precision


- Hereda de:

  - decimal.precision




- No agrega campos









## Vistas Adicionales


### account.payment.register

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | account.payment.register.form | `account.view_account_payment_register_form` | - |



**Botones (account.view_account_payment_register_form):**
- **action_open_untrusted_bank_accounts** (object)
- **action_open_missing_account_partners** (object)
- **Create Payments** (object)
- **Create Payment** (object)


### account.financial.year.op

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | account.financial.year.op.setup.wizard.form | `account.setup_financial_year_opening_form` | - |



**Botones (account.setup_financial_year_opening_form):**
- **Apply** (object)


### account.setup.bank.manual.config

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | account.online.sync.res.partner.bank.setup.form | `account.setup_bank_account_wizard` | - |



**Botones (account.setup_bank_account_wizard):**
- **Create** (object)


### account.autopost.bills.wizard

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | Autopost Bills | `account.autopost_bills_wizard` | - |



**Botones (account.autopost_bills_wizard):**
- **action_automate_partner** (object)
- **action_ask_later** (object)
- **action_never_automate_partner** (object)


### account.move.reversal

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | account.move.reversal.form | `account.view_account_move_reversal` | - |



**Botones (account.view_account_move_reversal):**
- **Reverse** (object)
- **Reverse and Create Invoice** (object)


### account.resequence.wizard

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | Re-sequence Journal Entries | `account.account_resequence_view` | - |



**Botones (account.account_resequence_view):**
- **Confirm** (object)


### account.accrued.orders.wizard

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | account.accrued.orders.wizard.view | `account.view_account_accrued_orders_wizard` | - |



**Botones (account.view_account_accrued_orders_wizard):**
- **Create Entry** (object)


### account.move.send.wizard

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | account.move.send.wizard.form | `account.account_move_send_wizard_form` | - |



**Botones (account.account_move_send_wizard_form):**
- **Send** (object)
- **Print** (object)


### account.merge.wizard

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | account.merge.wizard.form | `account.account_merge_wizard_form` | - |



**Botones (account.account_merge_wizard_form):**
- **Merge** (object)
- **Merge** (object)


### account.secure.entries.wizard

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | account.secure.entries.wizard.form | `account.view_account_secure_entries_wizard` | - |



**Botones (account.view_account_secure_entries_wizard):**
- **Secure Entries** (object)


### validate.account.move

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | Confirm Entries | `account.validate_account_move_view` | - |



**Botones (account.validate_account_move_view):**
- **Confirm** (object)


### account.automatic.entry.wizard

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | account.automatic.entry.wizard.form | `account.account_automatic_entry_wizard_form` | - |



**Botones (account.account_automatic_entry_wizard_form):**
- **Create Journal Entries** (object)


### account.move.send.batch.wizard

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | account.move.send.batch.wizard.form | `account.account_move_send_batch_wizard_form` | - |



**Botones (account.account_move_send_batch_wizard_form):**
- **Send** (object)


### account.invoice.report

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| pivot | account.invoice.report.pivot | `account.view_account_invoice_report_pivot` | - |
| graph | account.invoice.report.graph | `account.view_account_invoice_report_graph` | - |
| list | account.invoice.report.view.list | `account.account_invoice_report_view_tree` | - |
| search | account.invoice.report.search | `account.view_account_invoice_report_search` | - |



**Filtros de búsqueda (account.view_account_invoice_report_search):**

- **My Invoices** (`[('invoice_user_id', '=', uid)]`)
- **To Invoice** (`[('state','=','draft')]`)
- **Invoiced** (`[('state','not in', ('draft','cancel'))]`)
- **Customers** (`['|', ('move_type','=','out_invoice'),('move_type','=','out_refund')]`)
- **Vendors** (`['|', ('move_type','=','in_invoice'),('move_type','=','in_refund')]`)
- **Invoices** (`['|', ('move_type','=','out_invoice'),('move_type','=','in_invoice')]`)
- **Credit Notes** (`['|', ('move_type','=','out_refund'),('move_type','=','in_refund')]`)
- **filter_invoice_date**
- **invoice_date_due**


*Agrupar por:*
- Salesperson
- Partner
- Product Category
- Status
- Company
- Date
- Date
- Due Date



