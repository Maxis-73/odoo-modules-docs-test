# Módulo: Uruguay - Accounting

## Información General
- **Nombre técnico:** l10n_uy
- **Versión:** 0.1
- **Categoría:** Accounting/Localizations/Account Charts
- **Dependencias:** account, l10n_latam_invoice_document, l10n_latam_base




## Descripción

General Chart of Accounts.

This module adds accounting functionalities for the Uruguayan localization, representing the minimum required configuration for a company to operate in Uruguay under the regulations and guidelines provided by the DGI (Dirección General Impositiva).

Among the functionalities are:

* Uruguayan Generic Chart of Account
* Pre-configured VAT Taxes and Tax Groups.
* Legal document types in Uruguay.
* Valid contact identification types in Uruguay.
* Configuration and activation of Uruguayan Currencies  (UYU, UYI - Unidad Indexada Uruguaya).
* Frequently used default contacts already configured: DGI, Consumidor Final Uruguayo.

Configuration
-------------

Demo data for testing:

* Uruguayan company named "UY Company" with the Uruguayan chart of accounts already installed, pre configured taxes, document types and identification types.
* Uruguayan contacts for testing:

   * IEB Internacional
   * Consumidor Final Anónimo Uruguayo.





## Modelos

### l10n_latam.document.type


- Hereda de:

  - l10n_latam.document.type




- No agrega campos



### account.move


- Hereda de:

  - account.move




- No agrega campos



### l10n_latam.identification.type


- Hereda de:

  - l10n_latam.identification.type




- Campos:

  - **l10n_uy_dgi_code** (Char) → DGI Code





### account.tax


- Hereda de:

  - account.tax




- Campos:

  - **l10n_uy_tax_category** (Selection)





### res.company


- Hereda de:

  - res.company




- No agrega campos



### res.partner


- Hereda de:

  - res.partner




- No agrega campos



### account.chart.template


- Hereda de:

  - account.chart.template




- No agrega campos





