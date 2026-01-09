# Módulo: Event CRM

## Información General
- **Nombre técnico:** event_crm
- **Versión:** 1.0
- **Categoría:** Marketing/Events
- **Dependencias:** event, crm




## Descripción
Create leads from event registrations.



## Modelos

### event.lead.request


- Hereda de: Base



#### Campos
- **event_id** (Many2one) → event.event
- **processed_registration_id** (Integer) → Processed Registration





### event.lead.rule


- Hereda de: Base



#### Campos
- **name** (Char) → Rule Name
- **active** (Boolean) → Active
- **lead_ids** (One2many) → crm.lead
- **lead_creation_basis** (Selection)
- **lead_creation_trigger** (Selection)
- **event_type_ids** (Many2many) → event.type
- **event_id** (Many2one) → event.event
- **company_id** (Many2one) → res.company
- **event_registration_filter** (Text)
- **lead_type** (Selection)
- **lead_sales_team_id** (Many2one) → crm.team
- **lead_user_id** (Many2one) → res.users
- **lead_tag_ids** (Many2many) → crm.tag





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| search | event.lead.rule.view.search | `event_crm.event_lead_rule_view_search` | - |
| list | event.lead.rule.view.list | `event_crm.event_lead_rule_view_tree` | - |
| form | event.lead.rule.view.form | `event_crm.event_lead_rule_view_form` | - |



**Filtros de búsqueda (event_crm.event_lead_rule_view_search):**

- **Archived** (`[('active', '=', False)]`)


*Agrupar por:*
- Creation Type
- Trigger Type



### event.event


- Hereda de:

  - event.event




#### Campos
- **lead_ids** (One2many) → crm.lead
- **lead_count** (Integer)
- **has_lead_request** (Boolean) → Ongoing Generation Request





### event.registration


- Hereda de:

  - event.registration




#### Campos
- **lead_ids** (Many2many) → crm.lead
- **lead_count** (Integer) → # Leads





### crm.lead


- Hereda de:

  - crm.lead




#### Campos
- **event_lead_rule_id** (Many2one) → event.lead.rule
- **event_id** (Many2one) → event.event
- **registration_ids** (Many2many) → event.registration
- **registration_count** (Integer)










