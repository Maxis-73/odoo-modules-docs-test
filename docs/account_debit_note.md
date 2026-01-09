# Módulo: Debit Notes

## Información General
- **Nombre técnico:** account_debit_note
- **Versión:** 1.0
- **Categoría:** Accounting/Accounting
- **Dependencias:** account


## Propósito
Debit Notes



## Descripción

In a lot of countries, a debit note is used as an increase of the amounts of an existing invoice 
or in some specific cases to cancel a credit note. 
It is like a regular invoice, but we need to keep track of the link with the original invoice.  
The wizard used is similar as the one for the credit note.
    



## Modelos

### account.move


- Hereda de:

  - account.move




#### Campos
- **debit_origin_id** (Many2one) → account.move
- **debit_note_ids** (One2many) → account.move
- **debit_note_count** (Integer) → Number of Debit Notes





### account.journal


- Hereda de:

  - account.journal




#### Campos
- **debit_sequence** (Boolean)










## Vistas Adicionales


### account.debit.note

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | account.debit.note.form | `account_debit_note.view_account_debit_note` | - |



**Botones (account_debit_note.view_account_debit_note):**
- **Create Debit Note** (object)



