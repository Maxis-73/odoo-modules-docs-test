# Módulo: Import/Export Invoices From XML/PDF

## Información General
- **Nombre técnico:** account_edi
- **Versión:** 1.0
- **Categoría:** Accounting/Accounting
- **Dependencias:** account




## Descripción

Electronic Data Interchange
EDI is the electronic interchange of business information using a standardized format.

This is the base module for import and export of invoices in various EDI formats, and the
the transmission of said documents to various parties involved in the exchange (other company,
governements, etc.)
    



## Modelos

### account.move.send


- Hereda de:

  - account.move.send




- No agrega campos



### ir.actions.report


- Hereda de:

  - ir.actions.report




- No agrega campos



### account.move


- Hereda de:

  - account.move




- Campos:

  - **edi_document_ids** (One2many) → account.edi.document


  - **edi_state** (Selection)


  - **edi_error_count** (Integer)


  - **edi_blocking_level** (Selection)


  - **edi_error_message** (Html)


  - **edi_web_services_to_process** (Text)


  - **edi_show_cancel_button** (Boolean)


  - **edi_show_abandon_cancel_button** (Boolean)


  - **edi_show_force_cancel_button** (Boolean)





### account.journal


- Hereda de:

  - account.journal




- Campos:

  - **edi_format_ids** (Many2many) → account.edi.format


  - **compatible_edi_ids** (Many2many) → account.edi.format





### account.edi.format


- Hereda de: Base



- Campos:

  - **name** (Char)


  - **code** (Char)





### ir.attachment


- Hereda de:

  - ir.attachment




- No agrega campos



### account.edi.document


- Hereda de: Base



- Campos:

  - **move_id** (Many2one) → account.move


  - **edi_format_id** (Many2one) → account.edi.format


  - **attachment_id** (Many2one) → ir.attachment


  - **state** (Selection)


  - **error** (Html)


  - **blocking_level** (Selection)


  - **name** (Char)


  - **edi_format_name** (Char)


  - **edi_content** (Binary)








## Vistas


### account.move

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | account.move.form.inherit | `account_edi.view_move_form_inherit` | account.view_move_form |



### account.edi.document

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | Account.edi.document.list | `account_edi.view_tree_account_edi_document` | - |


