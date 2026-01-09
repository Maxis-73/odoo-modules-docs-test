# Módulo: France - VAT Anti-Fraud Certification for Point of Sale (CGI 286 I-3 bis)

## Información General
- **Nombre técnico:** l10n_fr_pos_cert
- **Versión:** 1.1
- **Categoría:** Accounting/Localizations/Point of Sale
- **Dependencias:** l10n_fr_account, point_of_sale




## Descripción

This add-on brings the technical requirements of the French regulation CGI art. 286, I. 3° bis that stipulates certain criteria concerning the inalterability, security, storage and archiving of data related to sales to private individuals (B2C).
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Install it if you use the Point of Sale app to sell to individuals.

The module adds following features:

    Inalterability: deactivation of all the ways to cancel or modify key data of POS orders, invoices and journal entries

    Security: chaining algorithm to verify the inalterability

    Storage: automatic sales closings with computation of both period and cumulative totals (daily, monthly, annually)

    Access to download the mandatory Certificate of Conformity delivered by Odoo SA (only for Odoo Enterprise users)




## Modelos

### account.sale.closing


- Hereda de: Base



- Campos:

  - **name** (Char)


  - **company_id** (Many2one) → res.company


  - **date_closing_stop** (Datetime)


  - **date_closing_start** (Datetime)


  - **frequency** (Selection)


  - **total_interval** (Monetary)


  - **cumulative_total** (Monetary)


  - **sequence_number** (Integer) → Sequence #


  - **last_order_id** (Many2one) → pos.order


  - **last_order_hash** (Char)


  - **currency_id** (Many2one) → res.currency





### account.fiscal.position


- Hereda de:

  - account.fiscal.position




- No agrega campos



### pos.config


- Hereda de:

  - pos.config




- No agrega campos



### pos.session


- Hereda de:

  - pos.session




- No agrega campos



### pos.order


- Hereda de:

  - pos.order




- Campos:

  - **l10n_fr_hash** (Char)


  - **l10n_fr_secure_sequence_number** (Integer)


  - **l10n_fr_string_to_hash** (Char)


  - **previous_order_id** (Many2one) → pos.order


  - **pos_version** (Char)





### pos.order.line


- Hereda de:

  - pos.order.line




- No agrega campos



### res.company


- Hereda de:

  - res.company




- Campos:

  - **l10n_fr_pos_cert_sequence_id** (Many2one) → ir.sequence








## Vistas


### res.config.settings

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | res.config.settings.view.form.inherit.l10n_fr_pos_cert | `l10n_fr_pos_cert.res_config_settings_view_form` | point_of_sale.res_config_settings_view_form |



### account.sale.closing

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | Sales Closings | `l10n_fr_pos_cert.list_view_account_sale_closing` | - |
| form | Sales Closings | `l10n_fr_pos_cert.form_view_account_sale_closing` | - |


