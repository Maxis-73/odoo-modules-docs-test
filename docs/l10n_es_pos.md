# Módulo: Spain - Point of Sale

## Información General
- **Nombre técnico:** l10n_es_pos
- **Versión:** N/A
- **Categoría:** Accounting/Localizations/Point of Sale
- **Dependencias:** point_of_sale, l10n_es


## Propósito
Spanish localization for Point of Sale





## Modelos

### pos.config


- Hereda de:

  - pos.config




- Campos:

  - **is_spanish** (Boolean)


  - **l10n_es_simplified_invoice_journal_id** (Many2one) → account.journal


  - **simplified_partner_id** (Many2one) → res.partner





### pos.order


- Hereda de:

  - pos.order




- Campos:

  - **is_l10n_es_simplified_invoice** (Boolean) → Simplified invoice


  - **l10n_es_simplified_invoice_number** (Char) → Simplified invoice number





### account.move


- Hereda de:

  - account.move




- No agrega campos



### res.config.settings


- Hereda de:

  - res.config.settings




- Campos:

  - **pos_l10n_es_simplified_invoice_journal_id** (Many2one)





### res.company


- Hereda de:

  - res.company




- No agrega campos





