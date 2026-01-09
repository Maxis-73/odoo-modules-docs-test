# Módulo: Italy - E-invoicing - Additional module to support the debit notes (nota di debito - NDD)

## Información General
- **Nombre técnico:** l10n_it_edi_ndd
- **Versión:** 1.0
- **Categoría:** Accounting/Localizations/EDI
- **Dependencias:** l10n_it_edi




## Descripción

Additional module to support the debit notes (nota di debito - NDD) by adding payment method and document types
    



## Modelos

### account.move


- Hereda de:

  - account.move




- Campos:

  - **l10n_it_payment_method** (Selection)


  - **l10n_it_document_type** (Many2one) → l10n_it.document.type





### account.payment.method.line


- Hereda de:

  - account.payment.method.line




- Campos:

  - **l10n_it_payment_method** (Selection)





### l10n_it.document.type


- Hereda de: Base



- Campos:

  - **name** (Char)


  - **code** (Char)


  - **type** (Selection)








## Vistas


### l10n_it.document.type

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | Document Type Tree | `l10n_it_edi_ndd.l10n_it_document_type_tree` | - |
| form | l10n_it.document.type.form | `l10n_it_edi_ndd.l10n_it_document_type_form` | - |


