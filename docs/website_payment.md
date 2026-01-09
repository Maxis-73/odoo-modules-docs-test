# Módulo: Website Payment

## Información General
- **Nombre técnico:** website_payment
- **Versión:** 1.0
- **Categoría:** Hidden
- **Dependencias:** website, account_payment, portal


## Propósito
Payment integration with website



## Descripción

This is a bridge module that adds multi-website support for payment providers.
    



## Modelos

### payment.transaction


- Hereda de:

  - payment.transaction




#### Campos
- **is_donation** (Boolean)





### account.payment


- Hereda de:

  - account.payment




#### Campos
- **is_donation** (Boolean)





### payment.provider


- Hereda de:

  - payment.provider




#### Campos
- **website_id** (Many2one) → website





### res.config.settings


- Hereda de:

  - res.config.settings




#### Campos
- **providers_state** (Selection)
- **first_provider_label** (Char)
- **is_stripe_supported_country** (Boolean)







