# Módulo: Indian - E-waybill

## Información General
- **Nombre técnico:** l10n_in_edi_ewaybill
- **Versión:** 1.03.00
- **Categoría:** Accounting/Localizations/EDI
- **Dependencias:** l10n_in_edi




## Descripción

Indian - E-waybill
To submit E-waybill through API to the government.
We use "Tera Software Limited" as GSP

Step 1: First you need to create an API username and password in the E-waybill portal.
Step 2: Switch to company related to that GST number
Step 3: Set that username and password in Odoo (Goto: Invoicing/Accounting -> Configration -> Settings -> Indian Electronic WayBill or find "E-waybill" in search bar)
Step 4: Repeat steps 1,2,3 for all GSTIN you have in odoo. If you have a multi-company with the same GST number then perform step 1 for the first company only.
    



## Modelos

### l10n.in.ewaybill.type


- Hereda de: Base



- Campos:

  - **name** (Char) → Type


  - **code** (Char) → Type Code


  - **sub_type** (Char) → Sub-type


  - **sub_type_code** (Char) → Sub-type Code


  - **allowed_supply_type** (Selection)


  - **active** (Boolean) → Active





### account.move


- Hereda de:

  - account.move




- Campos:

  - **l10n_in_type_id** (Many2one) → l10n.in.ewaybill.type


  - **l10n_in_distance** (Integer) → Distance


  - **l10n_in_mode** (Selection)


  - **l10n_in_vehicle_no** (Char) → Vehicle Number


  - **l10n_in_vehicle_type** (Selection)


  - **l10n_in_transportation_doc_no** (Char)


  - **l10n_in_transportation_doc_date** (Date)


  - **l10n_in_transporter_id** (Many2one) → res.partner


  - **l10n_in_edi_ewaybill_direct_api** (Boolean)


  - **l10n_in_edi_ewaybill_show_send_button** (Boolean)





### account.edi.format


- Hereda de:

  - account.edi.format




- No agrega campos



### res.config.settings


- Hereda de:

  - res.config.settings




- Campos:

  - **l10n_in_edi_ewaybill_username** (Char) → Indian EDI Stock username


  - **l10n_in_edi_ewaybill_password** (Char) → Indian EDI Stock password





### res.company


- Hereda de:

  - res.company




- Campos:

  - **l10n_in_edi_ewaybill_username** (Char) → E-Waybill (IN) Username


  - **l10n_in_edi_ewaybill_password** (Char) → E-Waybill (IN) Password


  - **l10n_in_edi_ewaybill_auth_validity** (Datetime) → E-Waybill (IN) Valid Until







