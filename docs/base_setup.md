# Módulo: Initial Setup Tools

## Información General
- **Nombre técnico:** base_setup
- **Versión:** 1.0
- **Categoría:** Hidden
- **Dependencias:** base, web




## Descripción

This module helps to configure the system at the installation of a new database.

Shows you a list of applications features to install from.

    



## Modelos

### kpi.provider


- Hereda de: Base



- No agrega campos



### res.users


- Hereda de:

  - res.users




- No agrega campos



### res.config.settings


- Hereda de:

  - res.config.settings




- Campos:

  - **company_id** (Many2one) → res.company


  - **is_root_company** (Boolean)


  - **user_default_rights** (Boolean) → Default Access Rights


  - **module_base_import** (Boolean) → Allow users to import data from CSV/XLS/XLSX/ODS files


  - **module_google_calendar** (Boolean)


  - **module_microsoft_calendar** (Boolean)


  - **module_mail_plugin** (Boolean)


  - **module_auth_oauth** (Boolean) → Use external authentication providers (OAuth)


  - **module_auth_ldap** (Boolean) → LDAP Authentication


  - **module_account_inter_company_rules** (Boolean) → Manage Inter Company


  - **module_voip** (Boolean) → VoIP


  - **module_web_unsplash** (Boolean) → Unsplash Image Library


  - **module_sms** (Boolean) → SMS


  - **module_partner_autocomplete** (Boolean) → Partner Autocomplete


  - **module_base_geolocalize** (Boolean) → GeoLocalize


  - **module_google_recaptcha** (Boolean) → reCAPTCHA


  - **module_website_cf_turnstile** (Boolean) → Cloudflare Turnstile


  - **report_footer** (Html)


  - **group_multi_currency** (Boolean)


  - **external_report_layout_id** (Many2one)


  - **show_effect** (Boolean)


  - **company_count** (Integer) → Number of Companies


  - **active_user_count** (Integer) → Number of Active Users


  - **language_count** (Integer) → Number of Languages


  - **company_name** (Char)


  - **company_informations** (Text)


  - **company_country_code** (Char)


  - **profiling_enabled_until** (Datetime) → Profiling enabled until


  - **module_product_images** (Boolean) → Get product pictures using barcode





### ir.http


- Hereda de:

  - ir.http




- No agrega campos





