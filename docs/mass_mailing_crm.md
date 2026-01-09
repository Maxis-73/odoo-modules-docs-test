# Módulo: Mass mailing on lead / opportunities

## Información General
- **Nombre técnico:** mass_mailing_crm
- **Versión:** 1.0
- **Categoría:** Hidden
- **Dependencias:** crm, mass_mailing


## Propósito
Add lead / opportunities UTM info on mass mailing



## Descripción
UTM and mass mailing on lead / opportunities



## Modelos

### utm.campaign


- Hereda de:

  - utm.campaign




- Campos:

  - **ab_testing_winner_selection** (Selection)





### crm.lead


- Hereda de:

  - crm.lead




- No agrega campos



### mailing.mailing


- Hereda de:

  - mailing.mailing




- Campos:

  - **use_leads** (Boolean) → Use Leads


  - **crm_lead_count** (Integer) → Leads/Opportunities Count







