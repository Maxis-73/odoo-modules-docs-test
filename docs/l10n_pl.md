# Módulo: Poland - Accounting

## Información General
- **Nombre técnico:** l10n_pl
- **Versión:** 2.0
- **Categoría:** Accounting/Localizations/Account Charts
- **Dependencias:** base_iban, base_vat, account




## Descripción

This is the module to manage the accounting chart and taxes for Poland in Odoo.

To jest moduł do tworzenia wzorcowego planu kont, podatków, obszarów podatkowych i
rejestrów podatkowych. Moduł ustawia też konta do kupna i sprzedaży towarów
zakładając, że wszystkie towary są w obrocie hurtowym.

Niniejszy moduł jest przeznaczony dla odoo 8.0.
Wewnętrzny numer wersji OpenGLOBE 1.02
    



## Modelos

### l10n_pl.l10n_pl_tax_office


- Hereda de: Base



- Campos:

  - **code** (Char) → Code


  - **name** (Char) → Description





### account.move


- Hereda de:

  - account.move




- Campos:

  - **l10n_pl_vat_b_spv** (Boolean)


  - **l10n_pl_vat_b_spv_dostawa** (Boolean)


  - **l10n_pl_vat_b_mpv_prowizja** (Boolean)





### account.chart.template


- Hereda de:

  - account.chart.template




- No agrega campos



### product.template


- Hereda de:

  - product.template




- Campos:

  - **l10n_pl_vat_gtu** (Selection)





### res.config.settings


- Hereda de:

  - res.config.settings




- Campos:

  - **l10n_pl_reports_tax_office_id** (Many2one)





### res.company


- Hereda de:

  - res.company




- Campos:

  - **l10n_pl_reports_tax_office_id** (Many2one) → l10n_pl.l10n_pl_tax_office





### res.partner


- Hereda de:

  - res.partner




- Campos:

  - **l10n_pl_links_with_customer** (Boolean)







