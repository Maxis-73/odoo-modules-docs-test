# Módulo: Croatia - e-invoicing

## Información General
- **Nombre técnico:** l10n_hr_edi
- **Versión:** 1.0
- **Categoría:** Accounting/Localizations/Reporting
- **Dependencias:** l10n_hr, account_edi_ubl_cii, account_peppol




## Descripción

e-invoicing for Croatia
    



## Modelos

### account.move.send


- Hereda de:

  - account.move.send




- No agrega campos



### product.template


- Hereda de:

  - product.template




- Campos:

  - **l10n_hr_kpd_category_id** (Many2one) → l10n_hr.kpd.category





### l10n_hr.kpd.category


- Hereda de: Base



- Campos:

  - **name** (Char) → Code


  - **sector** (Char) → Industry


  - **description** (Char) → Description





### account.edi.xml.ubl_hr


- Hereda de:

  - account.edi.xml.ubl_bis3




- No agrega campos



### account.move


- Hereda de:

  - account.move




- Campos:

  - **l10n_hr_process_type** (Selection)


  - **l10n_hr_customer_defined_process_name** (Char)


  - **l10n_hr_fiscal_user_id** (Many2one) → res.partner


  - **l10n_hr_operator_name** (Char)


  - **l10n_hr_operator_oib** (Char)


  - **l10n_hr_edi_addendum_id** (One2many) → l10n_hr_edi.addendum


  - **l10n_hr_invoice_sending_time** (Datetime)


  - **l10n_hr_business_document_status** (Selection)


  - **l10n_hr_business_status_reason** (Char)


  - **l10n_hr_fiscalization_number** (Char)


  - **l10n_hr_fiscalization_status** (Selection)


  - **l10n_hr_fiscalization_error** (Char)


  - **l10n_hr_fiscalization_request** (Char)


  - **l10n_hr_fiscalization_channel_type** (Selection)


  - **l10n_hr_payment_reported_amount** (Monetary)


  - **l10n_hr_payment_unreported** (Boolean)


  - **l10n_hr_payment_method_type** (Selection)


  - **l10n_hr_mer_document_eid** (Char)


  - **l10n_hr_mer_document_status** (Selection)





### account.journal


- Hereda de:

  - account.journal




- Campos:

  - **l10n_hr_business_premises_label** (Char)


  - **l10n_hr_issuing_device_label** (Char)


  - **l10n_hr_business_premises_label_refund** (Char)


  - **l10n_hr_issuing_device_label_refund** (Char)


  - **l10n_hr_mer_connection_state** (Selection)


  - **l10n_hr_is_mer_journal** (Boolean)





### account.tax


- Hereda de:

  - account.tax




- Campos:

  - **l10n_hr_tax_category_id** (Many2one) → l10n.hr.tax.category





### l10n.hr.tax.category


- Hereda de: Base



- Campos:

  - **name** (Char) → Name/Mark


  - **code_untdid** (Char) → UNTDID code


  - **code_hr** (Char) → HR tax category code


  - **code_tax_scheme** (Char) → UNTDID tax scheme code


  - **category_name** (Char) → Categody code name


  - **description** (Char) → Description





### res.config.settings


- Hereda de:

  - res.config.settings




- Campos:

  - **l10n_hr_mer_connection_state** (Selection)


  - **l10n_hr_mer_connection_mode** (Selection)


  - **l10n_hr_mer_username** (Char)


  - **l10n_hr_mer_password** (Char)


  - **l10n_hr_mer_company_ident** (Char)


  - **l10n_hr_mer_company_bu** (Char)


  - **l10n_hr_mer_software_ident** (Char)


  - **l10n_hr_mer_purchase_journal_id** (Many2one)





### account.move.line


- Hereda de:

  - account.move.line




- Campos:

  - **l10n_hr_kpd_category_id** (Many2one) → l10n_hr.kpd.category





### sequence.mixin


- Hereda de:

  - sequence.mixin




- No agrega campos



### res.company


- Hereda de:

  - res.company




- Campos:

  - **l10n_hr_mer_username** (Char) → MojEracun username


  - **l10n_hr_mer_password** (Char) → MojEracun password


  - **l10n_hr_mer_company_ident** (Char) → MojEracun CompanyId


  - **l10n_hr_mer_software_ident** (Char) → MojEracun SoftwareId


  - **l10n_hr_mer_connection_state** (Selection)


  - **l10n_hr_mer_connection_mode** (Selection)


  - **l10n_hr_mer_purchase_journal_id** (Many2one) → account.journal





### account.chart.template


- Hereda de:

  - account.chart.template




- No agrega campos



### l10n_hr_edi.addendum


- Hereda de: Base



- Campos:

  - **move_id** (Many2one) → account.move


  - **invoice_sending_time** (Datetime)


  - **business_document_status** (Selection)


  - **business_status_reason** (Char)


  - **fiscalization_number** (Char)


  - **fiscalization_status** (Selection)


  - **fiscalization_error** (Char)


  - **fiscalization_request** (Char)


  - **fiscalization_channel_type** (Selection)


  - **currency_id** (Many2one)


  - **payment_reported_amount** (Monetary)


  - **payment_method_type** (Selection)


  - **mer_document_eid** (Char)


  - **mer_document_status** (Selection)


  - **mer_signed_xml_archived** (Boolean)





### res.partner


- Hereda de:

  - res.partner




- Campos:

  - **invoice_sending_method** (Selection)


  - **invoice_edi_format** (Selection)


  - **l10n_hr_personal_oib** (Char)


  - **l10n_hr_business_unit_code** (Char) → Business Unit Code








## Vistas


### l10n_hr.kpd.category

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | l10n_hr.kpd.category.list | `l10n_hr_edi.l10n_hr_kpd_category_view_tree` | - |
| search | l10n_hr.kpd.category.search | `l10n_hr_edi.l10n_hr_kpd_category_view_search` | - |



#### Filtros de búsqueda (l10n_hr_edi.l10n_hr_kpd_category_view_search)


**Agrupar por:**
- Industry


### l10n_hr_edi.mojeracun_reject_wizard

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | l10n_hr_edi.mojeracun_reject_wizard.form | `l10n_hr_edi.mojeracun_reject_wizard_form` | - |



#### Botones (l10n_hr_edi.mojeracun_reject_wizard_form)
- **Reject invoice** (object)

