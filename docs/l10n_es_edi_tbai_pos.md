# Módulo: Spain - Point of Sale + TicketBAI

## Información General
- **Nombre técnico:** l10n_es_edi_tbai_pos
- **Versión:** 1.0
- **Categoría:** Accounting/Localizations/Point of Sale
- **Dependencias:** l10n_es_edi_tbai, point_of_sale






## Modelos

### pos.order


- Hereda de:

  - pos.order




- Campos:

  - **l10n_es_tbai_state** (Selection)


  - **l10n_es_tbai_chain_index** (Integer)


  - **l10n_es_tbai_post_document_id** (Many2one) → l10n_es_edi_tbai.document


  - **l10n_es_tbai_post_file** (Binary)


  - **l10n_es_tbai_post_file_name** (Char)


  - **l10n_es_tbai_is_required** (Boolean)


  - **l10n_es_tbai_refund_reason** (Selection)





### res.company


- Hereda de:

  - res.company




- No agrega campos



### pos.session


- Hereda de:

  - pos.session




- No agrega campos





