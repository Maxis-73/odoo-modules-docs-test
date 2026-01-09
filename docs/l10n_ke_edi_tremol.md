# Módulo: Kenya Tremol Device EDI Integration

## Información General
- **Nombre técnico:** l10n_ke_edi_tremol
- **Versión:** 1.0
- **Categoría:** Accounting/Localizations/EDI
- **Dependencias:** l10n_ke


## Propósito
Kenya Tremol Device EDI Integration



## Descripción

This module integrates with the Kenyan G03 Tremol control unit device to the KRA through TIMS.
    



## Modelos

### account.move.send


- Hereda de:

  - account.move.send




- No agrega campos



### account.move


- Hereda de:

  - account.move




- Campos:

  - **l10n_ke_cu_datetime** (Datetime)


  - **l10n_ke_cu_serial_number** (Char)


  - **l10n_ke_cu_invoice_number** (Char)


  - **l10n_ke_cu_qrcode** (Char)


  - **l10n_ke_cu_show_send_button** (Boolean)





### res.config.settings


- Hereda de:

  - res.config.settings




- Campos:

  - **l10n_ke_cu_proxy_address** (Char)





### res.company


- Hereda de:

  - res.company




- Campos:

  - **l10n_ke_cu_proxy_address** (Char)





### res.partner


- Hereda de:

  - res.partner




- Campos:

  - **l10n_ke_exemption_number** (Char)







