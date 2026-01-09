# Módulo: Taiwan - E-invoicing Ecommerce

## Información General
- **Nombre técnico:** l10n_tw_edi_ecpay_website_sale
- **Versión:** N/A
- **Categoría:** Website Sale/Localizations/EDI
- **Dependencias:** website_sale, l10n_tw_edi_ecpay


## Propósito
ECpay E-invoice bridge module for Ecommerce



## Descripción

        This bridge module allows the user to input Ecpay information in ecommerce for sending their invoices to the Ecpay system
    



## Modelos

### website


- Hereda de:

  - website




- No agrega campos



### sale.order


- Hereda de:

  - sale.order




- Campos:

  - **l10n_tw_edi_is_print** (Boolean)


  - **l10n_tw_edi_love_code** (Char)


  - **l10n_tw_edi_carrier_type** (Selection)


  - **l10n_tw_edi_carrier_number** (Char)


  - **l10n_tw_edi_carrier_number_2** (Char)





### res.partner


- Hereda de:

  - res.partner




- Campos:

  - **l10n_tw_edi_require_paper_format** (Boolean)







