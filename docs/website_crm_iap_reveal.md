# Módulo: Lead Generation From Website Visits

## Información General
- **Nombre técnico:** website_crm_iap_reveal
- **Versión:** 1.1
- **Categoría:** Sales/CRM
- **Dependencias:** iap_crm, iap_mail, crm_iap_mine, website_crm


## Propósito
Generate Leads/Opportunities from your website's traffic





## Modelos

### crm.reveal.view


- Hereda de: Base



#### Campos
- **reveal_ip** (Char)
- **reveal_rule_id** (Many2one) → crm.reveal.rule
- **reveal_state** (Selection)
- **create_date** (Datetime)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | crm.reveal.view.form | `website_crm_iap_reveal.crm_reveal_view_form` | - |
| list | crm.reveal.view.list | `website_crm_iap_reveal.crm_reveal_view_tree` | - |




### crm.reveal.rule


- Hereda de: Base



#### Campos
- **name** (Char)
- **active** (Boolean)
- **country_ids** (Many2many) → res.country
- **website_id** (Many2one) → website
- **state_ids** (Many2many) → res.country.state
- **regex_url** (Char)
- **sequence** (Integer)
- **industry_tag_ids** (Many2many) → crm.iap.lead.industry
- **filter_on_size** (Boolean)
- **company_size_min** (Integer)
- **company_size_max** (Integer)
- **contact_filter_type** (Selection)
- **preferred_role_id** (Many2one) → crm.iap.lead.role
- **other_role_ids** (Many2many) → crm.iap.lead.role
- **seniority_id** (Many2one) → crm.iap.lead.seniority
- **extra_contacts** (Integer)
- **lead_for** (Selection)
- **lead_type** (Selection)
- **suffix** (Char)
- **team_id** (Many2one) → crm.team
- **tag_ids** (Many2many) → crm.tag
- **user_id** (Many2one) → res.users
- **priority** (Selection)
- **lead_ids** (One2many) → crm.lead
- **lead_count** (Integer)
- **opportunity_count** (Integer)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | crm.reveal.rule.form | `website_crm_iap_reveal.crm_reveal_rule_form` | - |
| list | crm.reveal.rule.list | `website_crm_iap_reveal.crm_reveal_rule_tree` | - |
| search | crm.reveal.rule.view.search | `website_crm_iap_reveal.crm_reveal_rule_view_search` | - |



**Botones (website_crm_iap_reveal.crm_reveal_rule_form):**
- **action_get_opportunity_tree_view** (object)
- **action_get_lead_tree_view** (object) - Grupos: `crm.group_use_lead`


**Filtros de búsqueda (website_crm_iap_reveal.crm_reveal_rule_view_search):**

- **Archived** (`[('active', '=', False)]`)



### crm.lead


- Hereda de:

  - crm.lead




#### Campos
- **reveal_ip** (Char)
- **reveal_iap_credits** (Integer)
- **reveal_rule_id** (Many2one) → crm.reveal.rule





### ir.http


- Hereda de:

  - ir.http




- No agrega campos









