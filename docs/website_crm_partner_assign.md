# Módulo: Resellers

## Información General
- **Nombre técnico:** website_crm_partner_assign
- **Versión:** 1.2
- **Categoría:** Website/Website
- **Dependencias:** base_geolocalize, crm, account, website_partner, website_google_map, portal


## Propósito
Publish your resellers/partners and forward leads to them



## Descripción

This module allows to publish your resellers/partners on your website and to forward incoming leads/opportunities to them.


**Publish a partner**

To publish a partner, set a *Level* in their contact form (in the Partner Assignment section) and click the *Publish* button.

**Forward leads**

Forwarding leads can be done for one or several leads at a time. The action is available in the *Assigned Partner* section of the lead/opportunity form view and in the *Action* menu of the list view.

The automatic assignment is figured from the weight of partner levels and the geolocalization. Partners get leads that are located around them.

    



## Modelos

### website


- Hereda de:

  - website




- No agrega campos




### res.partner.activation


- Hereda de: Base



#### Campos
- **sequence** (Integer) → Sequence
- **name** (Char) → Name
- **active** (Boolean)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | res.partner.activation.form | `website_crm_partner_assign.res_partner_activation_form` | - |
| list | res.partner.activation.list | `website_crm_partner_assign.res_partner_activation_tree` | - |
| search | res.partner.activation.view.search | `website_crm_partner_assign.res_partner_activation_view_search` | - |



**Filtros de búsqueda (website_crm_partner_assign.res_partner_activation_view_search):**

- **Archived** (`[('active', '=', False)]`)



### res.partner.grade


- Hereda de:


  - website.published.mixin





#### Campos
- **sequence** (Integer) → Sequence
- **active** (Boolean) → Active
- **name** (Char) → Level Name
- **partner_weight** (Integer) → Level Weight





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | res.partner.grade.list | `website_crm_partner_assign.view_partner_grade_tree` | - |
| form | res.partner.grade.form | `website_crm_partner_assign.view_partner_grade_form` | - |
| search | res.partner.grade.view.search | `website_crm_partner_assign.res_partner_grade_view_search` | - |



**Filtros de búsqueda (website_crm_partner_assign.res_partner_grade_view_search):**

- **Archived** (`[('active', '=', False)]`)



### crm.lead


- Hereda de:

  - crm.lead




#### Campos
- **partner_latitude** (Float) → Geo Latitude
- **partner_longitude** (Float) → Geo Longitude
- **partner_assigned_id** (Many2one) → res.partner
- **partner_declined_ids** (Many2many) → res.partner
- **date_partner_assign** (Date) → Partner Assignment Date





### res.partner


- Hereda de:

  - res.partner




#### Campos
- **partner_weight** (Integer) → Level Weight
- **grade_id** (Many2one) → res.partner.grade
- **grade_sequence** (Integer)
- **activation** (Many2one) → res.partner.activation
- **date_partnership** (Date) → Partnership Date
- **date_review** (Date) → Latest Partner Review
- **date_review_next** (Date) → Next Partner Review
- **assigned_partner_id** (Many2one) → res.partner
- **implemented_partner_ids** (One2many) → res.partner
- **implemented_partner_count** (Integer)










## Vistas Adicionales


### crm.lead.forward.to.partner

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | crm_lead_forward_to_partner | `website_crm_partner_assign.crm_lead_forward_to_partner_form` | - |



**Botones (website_crm_partner_assign.crm_lead_forward_to_partner_form):**
- **Send** (object)


### crm.partner.report.assign

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| search | crm.partner.report.assign.select | `website_crm_partner_assign.view_report_crm_partner_assign_filter` | - |
| graph | crm.partner.assign.report.graph | `website_crm_partner_assign.view_report_crm_partner_assign_graph` | - |



**Filtros de búsqueda (website_crm_partner_assign.view_report_crm_partner_assign_filter):**

- **filter_date_partnership**
- **filter_date_review**


*Agrupar por:*
- Salesperson
- Partner
- Date Partnership
- Date Review



