# Módulo: Third Party and Deferred/Electronic Checks Management

## Información General
- **Nombre técnico:** l10n_latam_check
- **Versión:** 1.0.0
- **Categoría:** Accounting/Localizations
- **Dependencias:** account, base_vat


## Propósito
Checks Management



## Descripción

Own Checks Management
---------------------

Extends 'Check Printing Base' module to manage own checks with more features:

* allow using own checks that are not printed but filled manually by the user
* allow to use deferred or electronic checks
  * printing is disabled
  * check number is set manually by the user
* add an optional "Check Cash-In Date" for post-dated checks (deferred payments)
* add a menu to track own checks

Third Party Checks Management
-----------------------------

Add new "Third party check Management" feature.

There are 2 main Payment Methods additions:

* New Third Party Checks:

  * Payments of this payment method represent the check you get from a customer when getting paid (from an invoice or a manual payment)

* Existing Third Party check.

  * Payments of this payment method are to track moves of the check, for eg:

    * Use a check to pay a vendor
    * Deposit the check on the bank
    * Get the check back from the bank (rejection)
    * Get the check back from the vendor (a rejection or return)
    * Transfer the check from one third party check journal to the other (one shop to another)

  * Those operations can be done with multiple checks at once




## Modelos

### account.payment


- Hereda de:

  - account.payment




- Campos:

  - **l10n_latam_new_check_ids** (One2many) → l10n_latam.check


  - **l10n_latam_move_check_ids** (Many2many) → l10n_latam.check


  - **l10n_latam_check_warning_msg** (Text)


  - **amount** (Monetary)





### account.payment.method


- Hereda de:

  - account.payment.method




- No agrega campos



### account.move


- Hereda de:

  - account.move




- No agrega campos



### account.journal


- Hereda de:

  - account.journal




- No agrega campos



### account.move.line


- Hereda de:

  - account.move.line




- Campos:

  - **l10n_latam_check_ids** (One2many) → l10n_latam.check





### account.chart.template


- Hereda de:

  - account.chart.template




- No agrega campos



### l10n_latam.check


- Hereda de:


  - mail.thread

  - mail.activity.mixin





- Campos:

  - **payment_id** (Many2one) → account.payment


  - **operation_ids** (Many2many) → account.payment


  - **current_journal_id** (Many2one) → account.journal


  - **name** (Char)


  - **bank_id** (Many2one) → res.bank


  - **issuer_vat** (Char)


  - **payment_date** (Date)


  - **amount** (Monetary)


  - **outstanding_line_id** (Many2one) → account.move.line


  - **issue_state** (Selection)


  - **payment_method_code** (Char)


  - **partner_id** (Many2one)


  - **original_journal_id** (Many2one)


  - **company_id** (Many2one)


  - **currency_id** (Many2one)


  - **payment_method_line_id** (Many2one)








## Vistas


### account.payment

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | account.payment.form.inherited | `l10n_latam_check.view_account_payment_form_inherited` | account.view_account_payment_form |
| list | account.check.operations.list | `l10n_latam_check.view_account_third_party_check_operations_tree` | - |



### l10n_latam.check

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| search | account.check.search | `l10n_latam_check.view_account_payment_search` | - |
| calendar | account.check.calendar | `l10n_latam_check.view_account_check_calendar` | - |
| pivot | account.check.calendar | `l10n_latam_check.view_account_check_pivot` | - |
| form | l10n_latam_check.view.form | `l10n_latam_check.l10n_latam_check_view_form` | - |
| list | account.check.list | `l10n_latam_check.view_account_own_check_tree` | - |
| list | account.check.list | `l10n_latam_check.view_account_third_party_check_tree` | view_account_own_check_tree |



#### Filtros de búsqueda (l10n_latam_check.view_account_payment_search)

**Filtros:**
- **Payment Date**
- **Handed** (`[('issue_state', '=', 'handed')]`)
- **Voided** (`[('issue_state', '=', 'voided')]`)
- **Debited** (`[('issue_state', '=', 'debited')]`)
- **Late Activities** (`[('my_activity_date_deadline', '<', context_today().strftime('%Y-%m-%d'))]`)
- **Today Activities** (`[('my_activity_date_deadline', '=', context_today().strftime('%Y-%m-%d'))]`)
- **Future Activities** (`[('my_activity_date_deadline', '>', context_today().strftime('%Y-%m-%d'))]`)


**Agrupar por:**
- Partner
- Payment Date
- State
- Company


#### Botones (l10n_latam_check.l10n_latam_check_view_form)
- **Void Check** (object)
- **button_open_check_operations** (object)
- **button_open_payment** (object)
- **action_show_journal_entry** (object) - Grupos: `account.group_account_user,account.group_account_readonly`
- **action_show_reconciled_move** (object) - Grupos: `account.group_account_user,account.group_account_readonly`

