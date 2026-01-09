# Módulo: Italy - Declaration of Intent

## Información General
- **Nombre técnico:** l10n_it_edi_doi
- **Versión:** 0.1
- **Categoría:** Accounting/Localizations
- **Dependencias:** l10n_it_edi, sale




## Descripción

    Add support for the Declaration of Intent (Dichiarazione di Intento) to the Italian localization.
    



## Modelos

### sale.order


- Hereda de:

  - sale.order




- Campos:

  - **l10n_it_edi_doi_date** (Date)


  - **l10n_it_edi_doi_use** (Boolean)


  - **l10n_it_edi_doi_id** (Many2one) → l10n_it_edi_doi.declaration_of_intent


  - **l10n_it_edi_doi_not_yet_invoiced** (Monetary)


  - **l10n_it_edi_doi_warning** (Text)





### l10n_it_edi_doi.declaration_of_intent


- Hereda de:


  - mail.thread.main.attachment

  - mail.activity.mixin





- Campos:

  - **state** (Selection)


  - **company_id** (Many2one) → res.company


  - **partner_id** (Many2one) → res.partner


  - **currency_id** (Many2one) → res.currency


  - **issue_date** (Date)


  - **start_date** (Date)


  - **end_date** (Date)


  - **threshold** (Monetary)


  - **invoiced** (Monetary)


  - **not_yet_invoiced** (Monetary)


  - **remaining** (Monetary)


  - **protocol_number_part1** (Char)


  - **protocol_number_part2** (Char)


  - **invoice_ids** (One2many) → account.move


  - **sale_order_ids** (One2many) → sale.order





### account.move


- Hereda de:

  - account.move




- Campos:

  - **l10n_it_edi_doi_date** (Date)


  - **l10n_it_edi_doi_use** (Boolean)


  - **l10n_it_edi_doi_id** (Many2one) → l10n_it_edi_doi.declaration_of_intent


  - **l10n_it_edi_doi_amount** (Monetary)


  - **l10n_it_edi_doi_warning** (Text)





### account.fiscal.position


- Hereda de:

  - account.fiscal.position




- No agrega campos



### account.tax


- Hereda de:

  - account.tax




- No agrega campos



### res.company


- Hereda de:

  - res.company




- Campos:

  - **l10n_it_edi_doi_tax_id** (Many2one) → account.tax


  - **l10n_it_edi_doi_fiscal_position_id** (Many2one) → account.fiscal.position





### account.chart.template


- Hereda de:

  - account.chart.template




- No agrega campos



### res.partner


- Hereda de:

  - res.partner




- Campos:

  - **l10n_it_edi_doi_ids** (One2many) → l10n_it_edi_doi.declaration_of_intent








## Vistas


### account.move

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | account.move.list | `l10n_it_edi_doi.view_move_tree` | - |



### sale.order

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | sale.order.list | `l10n_it_edi_doi.view_quotation_tree` | - |



### l10n_it_edi_doi.declaration_of_intent

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | l10n_it_edi_doi.declaration_of_intent.list | `l10n_it_edi_doi.view_l10n_it_edi_doi_tree` | - |
| form | l10n_it_edi_doi.declaration_of_intent.form | `l10n_it_edi_doi.view_l10n_it_edi_doi_form` | - |
| search | l10n_it_edi_doi.declaration_of_intent.search | `l10n_it_edi_doi.view_l10n_it_edi_doi_declaration_of_intent_search` | - |



#### Botones (l10n_it_edi_doi.view_l10n_it_edi_doi_form)
- **Validate** (object)
- **Terminate** (object)
- **Reset to Draft** (object)
- **Reactivate** (object)
- **Revoke** (object)
- **action_open_invoice_ids** (object)
- **action_open_sale_order_ids** (object)


#### Filtros de búsqueda (l10n_it_edi_doi.view_l10n_it_edi_doi_declaration_of_intent_search)

**Filtros:**
- **Active** (`[('state','=', 'active')]`)
- **Draft** (`[('state','=', 'draft')]`)
- **Terminated / Revoked** (`[('state','in', ['terminated', 'revoked'])]`)

