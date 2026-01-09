# Módulo: Lead Generation

## Información General
- **Nombre técnico:** crm_iap_mine
- **Versión:** 1.2
- **Categoría:** Sales/CRM
- **Dependencias:** iap_crm, iap_mail


## Propósito
Generate Leads/Opportunities based on country, industries, size, etc.





## Modelos

### crm.iap.lead.industry


- Hereda de: Base



- Campos:

  - **name** (Char)


  - **reveal_ids** (Char)


  - **color** (Integer)


  - **sequence** (Integer) → Sequence





### crm.iap.lead.seniority


- Hereda de: Base



- Campos:

  - **name** (Char)


  - **reveal_id** (Char)





### crm.iap.lead.role


- Hereda de: Base



- Campos:

  - **name** (Char)


  - **reveal_id** (Char)


  - **color** (Integer)





### crm.iap.lead.helpers


- Hereda de: Base



- No agrega campos



### crm.iap.lead.mining.request


- Hereda de: Base



- Campos:

  - **name** (Char)


  - **state** (Selection)


  - **lead_number** (Integer)


  - **search_type** (Selection)


  - **error_type** (Selection)


  - **lead_type** (Selection)


  - **team_id** (Many2one) → crm.team


  - **user_id** (Many2one) → res.users


  - **tag_ids** (Many2many) → crm.tag


  - **lead_ids** (One2many) → crm.lead


  - **lead_count** (Integer)


  - **filter_on_size** (Boolean)


  - **company_size_min** (Integer)


  - **company_size_max** (Integer)


  - **country_ids** (Many2many) → res.country


  - **state_ids** (Many2many) → res.country.state


  - **available_state_ids** (One2many) → res.country.state


  - **industry_ids** (Many2many) → crm.iap.lead.industry


  - **contact_number** (Integer)


  - **contact_filter_type** (Selection)


  - **preferred_role_id** (Many2one) → crm.iap.lead.role


  - **role_ids** (Many2many) → crm.iap.lead.role


  - **seniority_id** (Many2one) → crm.iap.lead.seniority


  - **lead_credits** (Char)


  - **lead_contacts_credits** (Char)


  - **lead_total_credits** (Char)





### crm.lead


- Hereda de:

  - crm.lead




- Campos:

  - **lead_mining_request_id** (Many2one) → crm.iap.lead.mining.request








## Vistas


### crm.iap.lead.mining.request

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | crm.iap.lead.mining.request.view.form | `crm_iap_mine.crm_iap_lead_mining_request_view_form` | - |
| list | crm.iap.lead.mining.request.view.list | `crm_iap_mine.crm_iap_lead_mining_request_view_tree` | - |
| search | crm.iap.lead.mining.request.view.search | `crm_iap_mine.crm_iap_lead_mining_request_view_search` | - |



#### Botones (crm_iap_mine.crm_iap_lead_mining_request_view_form)
- **Submit** (object)
- **Retry** (object)
- **action_buy_credits** (object)
- **action_get_opportunity_action** (object)
- **action_get_lead_action** (object) - Grupos: `crm.group_use_lead`
- **Generate Leads** (object)


#### Filtros de búsqueda (crm_iap_mine.crm_iap_lead_mining_request_view_search)

**Filtros:**
- **Draft** (`[('state', '=', 'draft')]`)
- **Done** (`[('state', '=', 'done')]`)
- **Error** (`[('state', '=', 'error')]`)
- **Leads** (`[('lead_type', '=', 'lead')]`)
- **Opportunities** (`[('lead_type', '=', 'opportunity')]`)


**Agrupar por:**
- Type
- Sales Team
- Salesperson

