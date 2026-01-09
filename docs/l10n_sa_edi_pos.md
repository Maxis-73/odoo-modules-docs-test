# Módulo: Saudi Arabia - E-invoicing (Simplified)

## Información General
- **Nombre técnico:** l10n_sa_edi_pos
- **Versión:** 0.2
- **Categoría:** Accounting/Localizations/EDI
- **Dependencias:** l10n_sa_pos, l10n_sa_edi


## Propósito

        ZATCA E-Invoicing, support for PoS
    



## Descripción

E-invoice implementation for Saudi Arabia; Integration with ZATCA (POS)
    



## Modelos

### pos.config


- Hereda de:

  - pos.config




- No agrega campos



### account.edi.xml.ubl_21.zatca


- Hereda de:

  - account.edi.xml.ubl_21.zatca




- No agrega campos



### pos.order


- Hereda de:

  - pos.order




- Campos:

  - **l10n_sa_invoice_qr_code_str** (Char)


  - **l10n_sa_invoice_edi_state** (Selection)





### account.move


- Hereda de:

  - account.move




- No agrega campos





