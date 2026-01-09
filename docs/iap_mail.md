# Módulo: IAP / Mail

## Información General
- **Nombre técnico:** iap_mail
- **Versión:** 1.0
- **Categoría:** Hidden/Tools
- **Dependencias:** iap, mail


## Propósito
Bridge between IAP and mail



## Descripción
Bridge between IAP and mail



## Modelos

### iap.account


- Hereda de:


  - iap.account

  - mail.thread





- Campos:

  - **company_ids** (Many2many) → res.company


  - **warning_threshold** (Float) → Email Alert Threshold


  - **warning_user_ids** (Many2many) → res.users







