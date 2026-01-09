# Módulo: CRM

## Información General
- **Nombre técnico:** crm
- **Versión:** 1.8
- **Categoría:** Sales/CRM
- **Dependencias:** base_setup, sales_team, mail, calendar, resource, utm, web_tour, contacts, digest, phone_validation


## Propósito
Track leads and close opportunities





## Modelos

### utm.campaign


- Hereda de:

  - utm.campaign




#### Campos
- **use_leads** (Boolean) → Use Leads
- **crm_lead_count** (Integer) → Leads/Opportunities count





### crm.lead.scoring.frequency


- Hereda de: Base



#### Campos
- **variable** (Char) → Variable
- **value** (Char) → Value
- **won_count** (Float) → Won Count
- **lost_count** (Float) → Lost Count
- **team_id** (Many2one) → crm.team





### crm.lead.scoring.frequency.field


- Hereda de: Base



#### Campos
- **name** (Char)
- **field_id** (Many2one) → ir.model.fields





### crm.lost.reason


- Hereda de: Base



#### Campos
- **name** (Char) → Description
- **active** (Boolean) → Active
- **leads_count** (Integer) → Leads Count





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| search | crm.lost.reason.view.search | `crm.crm_lost_reason_view_search` | - |
| form | crm.lost.reason.form | `crm.crm_lost_reason_view_form` | - |
| list | crm.lost.reason.list | `crm.crm_lost_reason_view_tree` | - |



**Filtros de búsqueda (crm.crm_lost_reason_view_search):**

- **Active** (`[('active', '=', True)]`)
- **Archived** (`[('active', '=', False)]`)


**Botones (crm.crm_lost_reason_view_form):**
- **action_lost_leads** (object)



### crm.recurring.plan


- Hereda de: Base



#### Campos
- **name** (Char) → Plan Name
- **number_of_months** (Integer) → # Months
- **active** (Boolean) → Active
- **sequence** (Integer) → Sequence





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | crm.recurring.plan.view.list | `crm.crm_recurring_plan_view_tree` | - |
| search | crm.recurring.plan.view.search | `crm.crm_recurring_plan_view_search` | - |



**Filtros de búsqueda (crm.crm_recurring_plan_view_search):**

- **Archived** (`[('active', '=', False)]`)



### crm.stage


- Hereda de: Base



#### Campos
- **name** (Char) → Stage Name
- **sequence** (Integer) → Sequence
- **is_won** (Boolean) → Is Won Stage?
- **requirements** (Text) → Requirements
- **team_id** (Many2one) → crm.team
- **fold** (Boolean) → Folded in Pipeline
- **team_count** (Integer) → team_count





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| search | Stage - Search | `crm.crm_lead_stage_search` | - |
| list | crm.stage.list | `crm.crm_stage_tree` | - |
| form | crm.stage.form | `crm.crm_stage_form` | - |




### digest.digest


- Hereda de:

  - digest.digest




#### Campos
- **kpi_crm_lead_created** (Boolean) → New Leads
- **kpi_crm_lead_created_value** (Integer)
- **kpi_crm_opportunities_won** (Boolean) → Opportunities Won
- **kpi_crm_opportunities_won_value** (Integer)





### res.users


- Hereda de:

  - res.users




#### Campos
- **target_sales_won** (Integer) → Won in Opportunities Target
- **target_sales_done** (Integer) → Activities Done Target





### calendar.event


- Hereda de:

  - calendar.event




#### Campos
- **opportunity_id** (Many2one) → crm.lead





### res.config.settings


- Hereda de:

  - res.config.settings




#### Campos
- **group_use_lead** (Boolean)
- **group_use_recurring_revenues** (Boolean)
- **is_membership_multi** (Boolean)
- **crm_use_auto_assignment** (Boolean)
- **crm_auto_assignment_action** (Selection)
- **crm_auto_assignment_interval_type** (Selection)
- **crm_auto_assignment_interval_number** (Integer)
- **crm_auto_assignment_run_datetime** (Datetime)
- **module_crm_iap_mine** (Boolean) → Generate new leads based on their country, industries, size, etc.
- **module_crm_iap_enrich** (Boolean) → Enrich your leads automatically with company data based on their email address.
- **module_website_crm_iap_reveal** (Boolean) → Create Leads/Opportunities from your website's traffic
- **lead_enrich_auto** (Selection)
- **lead_mining_in_pipeline** (Boolean) → Create a lead mining request directly from the opportunity pipeline.
- **predictive_lead_scoring_start_date** (Date)
- **predictive_lead_scoring_start_date_str** (Char)
- **predictive_lead_scoring_fields** (Many2many) → crm.lead.scoring.frequency.field
- **predictive_lead_scoring_fields_str** (Char)
- **predictive_lead_scoring_field_labels** (Char)





### ir.config_parameter


- Hereda de:

  - ir.config_parameter




- No agrega campos




### crm.team


- Hereda de:


  - mail.alias.mixin

  - crm.team





#### Campos
- **use_leads** (Boolean) → Leads
- **use_opportunities** (Boolean) → Pipeline
- **alias_id** (Many2one)
- **assignment_enabled** (Boolean) → Lead Assign
- **assignment_auto_enabled** (Boolean) → Auto Assignment
- **assignment_optout** (Boolean) → Skip auto assignment
- **assignment_max** (Integer) → Lead Average Capacity
- **assignment_domain** (Char) → Assignment Domain
- **lead_unassigned_count** (Integer)
- **lead_all_assigned_month_count** (Integer)
- **lead_all_assigned_month_exceeded** (Boolean) → Exceed monthly lead assignement
- **opportunities_count** (Integer)
- **opportunities_amount** (Monetary)
- **opportunities_overdue_count** (Integer)
- **opportunities_overdue_amount** (Monetary)
- **lead_properties_definition** (PropertiesDefinition) → Lead Properties





### mail.activity


- Hereda de:

  - mail.activity




- No agrega campos




### crm.lead


- Hereda de:


  - mail.thread.cc

  - mail.thread.blacklist

  - mail.thread.phone

  - mail.activity.mixin

  - utm.mixin

  - format.address.mixin

  - mail.tracking.duration.mixin





#### Campos
- **name** (Char) → Opportunity
- **user_id** (Many2one) → res.users
- **user_company_ids** (Many2many) → res.company
- **team_id** (Many2one) → crm.team
- **lead_properties** (Properties) → Properties
- **company_id** (Many2one) → res.company
- **referred** (Char) → Referred By
- **description** (Html) → Notes
- **active** (Boolean) → Active
- **type** (Selection)
- **priority** (Selection)
- **stage_id** (Many2one) → crm.stage
- **tag_ids** (Many2many) → crm.tag
- **color** (Integer) → Color Index
- **expected_revenue** (Monetary) → Expected Revenue
- **prorated_revenue** (Monetary) → Prorated Revenue
- **recurring_revenue** (Monetary) → Recurring Revenues
- **recurring_plan** (Many2one) → crm.recurring.plan
- **recurring_revenue_monthly** (Monetary) → Expected MRR
- **recurring_revenue_monthly_prorated** (Monetary) → Prorated MRR
- **recurring_revenue_prorated** (Monetary) → Prorated Recurring Revenues
- **company_currency** (Many2one) → res.currency
- **date_closed** (Datetime) → Closed Date
- **date_automation_last** (Datetime) → Last Action
- **date_open** (Datetime) → Assignment Date
- **day_open** (Float) → Days to Assign
- **day_close** (Float) → Days to Close
- **date_last_stage_update** (Datetime) → Last Stage Update
- **date_conversion** (Datetime) → Conversion Date
- **date_deadline** (Date) → Expected Closing
- **partner_id** (Many2one) → res.partner
- **partner_is_blacklisted** (Boolean) → Partner is blacklisted
- **contact_name** (Char) → Contact Name
- **partner_name** (Char) → Company Name
- **function** (Char) → Job Position
- **title** (Many2one) → res.partner.title
- **email_from** (Char) → Email
- **email_normalized** (Char)
- **email_domain_criterion** (Char)
- **phone** (Char) → Phone
- **mobile** (Char) → Mobile
- **phone_sanitized** (Char)
- **phone_state** (Selection)
- **email_state** (Selection)
- **website** (Char) → Website
- **lang_id** (Many2one) → res.lang
- **lang_code** (Char)
- **lang_active_count** (Integer)
- **street** (Char) → Street
- **street2** (Char) → Street2
- **zip** (Char) → Zip
- **city** (Char) → City
- **state_id** (Many2one) → res.country.state
- **country_id** (Many2one) → res.country
- **probability** (Float) → Probability
- **automated_probability** (Float) → Automated Probability
- **is_automated_probability** (Boolean) → Is automated probability?
- **lost_reason_id** (Many2one) → crm.lost.reason
- **calendar_event_ids** (One2many) → calendar.event
- **duplicate_lead_ids** (Many2many) → crm.lead
- **duplicate_lead_count** (Integer)
- **meeting_display_date** (Date)
- **meeting_display_label** (Char)
- **partner_email_update** (Boolean) → Partner Email will Update
- **partner_phone_update** (Boolean) → Partner Phone will Update
- **is_partner_visible** (Boolean) → Is Partner Visible
- **campaign_id** (Many2one)
- **medium_id** (Many2one)
- **source_id** (Many2one)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | crm.lead.form | `crm.crm_lead_view_form` | - |
| list | crm.lead.list.lead | `crm.crm_case_tree_view_leads` | - |
| kanban | crm.lead.kanban | `crm.view_crm_lead_kanban` | - |
| calendar | crm.lead.calendar.lead | `crm.crm_case_calendar_view_leads` | - |
| form | crm.lead.form.quick_create | `crm.quick_create_opportunity_form` | - |
| activity | crm.lead.view.activity | `crm.crm_lead_view_activity` | - |
| kanban | crm.lead.kanban.lead | `crm.crm_case_kanban_view_leads` | - |
| search | crm.lead.search.lead | `crm.view_crm_case_leads_filter` | - |
| list | crm.lead.list.opportunity | `crm.crm_case_tree_view_oppor` | - |
| graph | crm.lead.view.graph | `crm.crm_lead_view_graph` | - |
| graph | crm.lead.view.graph.forecast | `crm.crm_lead_view_graph_forecast` | - |
| pivot | crm.lead.view.pivot | `crm.crm_lead_view_pivot` | - |
| pivot | crm.lead.view.pivot.forecast | `crm.crm_lead_view_pivot_forecast` | - |
| search | crm.lead.search.opportunity | `crm.view_crm_case_opportunities_filter` | - |
| pivot | crm.opportunity.report.pivot | `crm.crm_opportunity_report_view_pivot` | - |
| pivot | crm.opportunity.report.view.pivot.lead | `crm.crm_opportunity_report_view_pivot_lead` | - |
| graph | crm.opportunity.report.graph | `crm.crm_opportunity_report_view_graph` | - |
| graph | crm.opportunity.report.graph.lead | `crm.crm_opportunity_report_view_graph_lead` | - |
| search | crm.lead.search | `crm.crm_opportunity_report_view_search` | - |



**Botones (crm.crm_lead_view_form):**
- **Won** (object)
- **Lost** (action)
- **Convert to Opportunity** (action)
- **Restore** (object)
- **Lost** (action)
- **action_schedule_meeting** (object)
- **action_show_potential_duplicates** (object)
- **action_set_automated_probability** (object)
- **mail_action_blacklist_remove** (object) - Grupos: `base.group_user`
- **phone_action_blacklist_remove** (object) - Grupos: `base.group_user`
- **mail_action_blacklist_remove** (object) - Grupos: `base.group_user`
- **phone_action_blacklist_remove** (object) - Grupos: `base.group_user`
- **phone_action_blacklist_remove** (object) - Grupos: `base.group_user`
- **phone_action_blacklist_remove** (object) - Grupos: `base.group_user`


**Filtros de búsqueda (crm.view_crm_case_leads_filter):**

- **My Leads** (`[('user_id', '=', uid)]`)
- **Unassigned** (`[('user_id','=', False), ('type', '=', 'lead')]`)
- **Lost** (`['&', ('probability', '=', 0), ('active', '=', False)]`)
- **Creation Date**
- **filter_date_closed**
- **Late Activities** (`[('my_activity_date_deadline', '<', context_today().strftime('%Y-%m-%d'))]`)
- **Today Activities** (`[('my_activity_date_deadline', '=', context_today().strftime('%Y-%m-%d'))]`)
- **Future Activities** (`[('my_activity_date_deadline', '>', context_today().strftime('%Y-%m-%d'))]`)
- **Archived** (`[('active', '=', False)]`)


*Agrupar por:*
- Salesperson
- Sales Team
- City
- Country
- Company
- Campaign
- Medium
- Source
- Creation Date
- Closed Date
- Properties


**Filtros de búsqueda (crm.view_crm_case_opportunities_filter):**

- **My Pipeline** (`[('user_id', '=', uid)]`)
- **Unassigned** (`[('user_id', '=', False)]`)
- **Open Opportunities** (`[('probability', '<', 100), ('type', '=', 'opportunity'), ('active', '=', True)]`)
- **Unread Messages** (`[('message_needaction', '=', True)]`)
- **Creation Date**
- **Closed Date**
- **Won** (`['&', ('active', '=', True), ('stage_id.is_won', '=', True)]`)
- **Ongoing** (`['&', ('active', '=', True), ('stage_id.is_won', '=', False)]`)
- **Lost** (`['&', ('active', '=', False), ('probability', '=', 0)]`)
- **Overdue Opportunities** (`['&', ('date_closed', '=', False), ('date_deadline', '<', context_today().strftime('%Y-%m-%d'))]`)
- **Late Activities** (`[('my_activity_date_deadline', '<', context_today().strftime('%Y-%m-%d'))]`)
- **Today Activities** (`[('my_activity_date_deadline', '=', context_today().strftime('%Y-%m-%d'))]`)
- **Future Activities** (`[('my_activity_date_deadline', '>', context_today().strftime('%Y-%m-%d'))]`)


*Agrupar por:*
- Salesperson
- Sales Team
- Stage
- City
- Country
- Lost Reason
- Company
- Campaign
- Medium
- Source
- Creation Date
- Creation Date
- Conversion Date
- Expected Closing
- Closed Date
- Properties


**Filtros de búsqueda (crm.crm_opportunity_report_view_search):**

- **My Pipeline** (`[('user_id', '=', uid)]`)
- **Opportunities** (`[('type','=','opportunity')]`)
- **Leads** (`[('type','=', 'lead')]`)
- **Active** (`[('active', '=', True)]`)
- **Inactive** (`[('active', '=', False)]`)
- **Won** (`[('probability', '=', 100)]`)
- **Lost** (`[('probability', '=', 0), ('active', '=', False)]`)
- **filter_create_date**
- **Expected Closing**
- **Date Closed**
- **Archived** (`[('active', '=', False)]`)


*Agrupar por:*
- Salesperson
- Sales Team
- City
- Country
- Company
- Stage
- Campaign
- Medium
- Source
- Creation Date
- Conversion Date
- Expected Closing
- Closed Date
- Lost Reason



### res.partner


- Hereda de:

  - res.partner




#### Campos
- **opportunity_ids** (One2many) → crm.lead
- **opportunity_count** (Integer)





### crm.team.member


- Hereda de:

  - crm.team.member




#### Campos
- **assignment_enabled** (Boolean)
- **assignment_domain** (Char) → Assignment Domain
- **assignment_optout** (Boolean) → Skip auto assignment
- **assignment_max** (Integer) → Average Leads Capacity (on 30 days)
- **lead_day_count** (Integer) → Leads (last 24h)
- **lead_month_count** (Integer) → Leads (30 days)










## Vistas Adicionales


### crm.merge.opportunity

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | crm.merge.opportunity.form | `crm.merge_opportunity_form` | - |



**Botones (crm.merge_opportunity_form):**
- **Merge** (object)


### crm.lead.lost

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | crm.lead.lost.form | `crm.crm_lead_lost_view_form` | - |



**Botones (crm.crm_lead_lost_view_form):**
- **Mark as Lost** (object)


### crm.lead.pls.update

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | crm.lead.pls.update.view.form | `crm.crm_lead_pls_update_view_form` | - |



**Botones (crm.crm_lead_pls_update_view_form):**
- **Update** (object)


### crm.lead2opportunity.partner

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | crm.lead2opportunity.partner.form | `crm.view_crm_lead2opportunity_partner` | - |



**Botones (crm.view_crm_lead2opportunity_partner):**
- **Create Opportunity** (object)


### crm.lead2opportunity.partner.mass

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | crm.lead2opportunity.partner.mass.form | `crm.view_crm_lead2opportunity_partner_mass` | - |



**Botones (crm.view_crm_lead2opportunity_partner_mass):**
- **Convert to Opportunities** (object)


### crm.activity.report

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| graph | crm.activity.report.graph | `crm.crm_activity_report_view_graph` | - |
| pivot | crm.activity.report.pivot | `crm.crm_activity_report_view_pivot` | - |
| list | crm.activity.report.list | `crm.crm_activity_report_view_tree` | - |
| search | crm.activity.report.search | `crm.crm_activity_report_view_search` | - |



**Filtros de búsqueda (crm.crm_activity_report_view_search):**

- **Leads** (`[('lead_type', '=', 'lead')]`)
- **Opportunities** (`[('lead_type', '=', 'opportunity')]`)
- **Won** (`[('stage_id.is_won', '=', True)]`)
- **Trailing 12 months** (`[                         ('date', '>=', (datetime.datetime.combine(context_today() + relativedelta(days=-365), datetime.time(0,0,0)).to_utc()).strftime('%Y-%m-%d %H:%M:%S')),                         ('date', '<=', (datetime.datetime.combine(context_today(), datetime.time(23, 59, 59)).to_utc()).strftime('%Y-%m-%d %H:%M:%S'))]`)
- **filter_date**
- **Archived** (`[('active', '=', False)]`)


*Agrupar por:*
- Activity
- Type
- Assigned To
- Completion Date
- Salesperson
- Sales Team
- Stage
- Company
- Creation Date
- Expected Closing
- Closed Date



