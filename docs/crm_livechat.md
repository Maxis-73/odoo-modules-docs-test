# Módulo: CRM Livechat

## Información General
- **Nombre técnico:** crm_livechat
- **Versión:** N/A
- **Categoría:** Sales/CRM
- **Dependencias:** crm, im_livechat


## Propósito
Create lead from livechat conversation



## Descripción
Create new lead with using /lead command in the channel



## Modelos

### chatbot.script


- Hereda de:

  - chatbot.script




#### Campos
- **lead_count** (Integer)





### discuss.channel


- Hereda de:

  - discuss.channel




- No agrega campos




### chatbot.script.step


- Hereda de:

  - chatbot.script.step




#### Campos
- **step_type** (Selection)
- **crm_team_id** (Many2one) → crm.team







