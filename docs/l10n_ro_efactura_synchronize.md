# Módulo: Romania - Synchronize E-Factura

## Información General
- **Nombre técnico:** l10n_ro_efactura_synchronize
- **Versión:** 1.0
- **Categoría:** Accounting/Localizations/EDI
- **Dependencias:** l10n_ro_edi


## Propósito
Additional module to synchronize bills with the SPV





## Modelos

### l10n_ro_edi.document


- Hereda de:

  - l10n_ro_edi.document




- No agrega campos



### account.move


- Hereda de:

  - account.move




- No agrega campos



### res.config.settings


- Hereda de:

  - res.config.settings




- Campos:

  - **l10n_ro_edi_anaf_imported_inv_journal_id** (Many2one)





### res.company


- Hereda de:

  - res.company




- Campos:

  - **l10n_ro_edi_anaf_imported_inv_journal_id** (Many2one) → account.journal







