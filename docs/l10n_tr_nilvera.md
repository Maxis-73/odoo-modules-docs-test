# Módulo: Türkiye - Nilvera

## Información General
- **Nombre técnico:** l10n_tr_nilvera
- **Versión:** 1.0
- **Categoría:** Accounting/Accounting
- **Dependencias:** l10n_tr




## Descripción

Base module containing core functionalities required by other Nilvera modules.
    



## Modelos

### uom.uom


- Hereda de:

  - uom.uom




- No agrega campos



### l10n_tr.nilvera.alias


- Hereda de: Base



- Campos:

  - **name** (Char)


  - **partner_id** (Many2one) → res.partner





### account.journal


- Hereda de:

  - account.journal




- Campos:

  - **l10n_tr_nilvera_api_key** (Char)


  - **is_nilvera_journal** (Boolean)





### res.config.settings


- Hereda de:

  - res.config.settings




- Campos:

  - **l10n_tr_nilvera_api_key** (Char)


  - **l10n_tr_nilvera_environment** (Selection)


  - **l10n_tr_nilvera_purchase_journal_id** (Many2one)





### res.company


- Hereda de:

  - res.company




- Campos:

  - **l10n_tr_nilvera_api_key** (Char)


  - **l10n_tr_nilvera_environment** (Selection)


  - **l10n_tr_nilvera_purchase_journal_id** (Many2one) → account.journal





### res.partner


- Hereda de:


  - res.partner





- Campos:

  - **invoice_edi_format** (Selection)


  - **l10n_tr_nilvera_customer_status** (Selection)


  - **l10n_tr_nilvera_customer_alias_id** (Many2one) → l10n_tr.nilvera.alias


  - **l10n_tr_nilvera_customer_alias_ids** (One2many) → l10n_tr.nilvera.alias







