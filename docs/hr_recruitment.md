# Módulo: Recruitment

## Información General
- **Nombre técnico:** hr_recruitment
- **Versión:** 1.1
- **Categoría:** Human Resources/Recruitment
- **Dependencias:** hr, calendar, utm, attachment_indexation, web_tour, digest


## Propósito
Track your recruitment pipeline





## Modelos

### hr.applicant


- Hereda de:


  - mail.thread.cc

  - mail.thread.main.attachment

  - mail.activity.mixin

  - utm.mixin

  - mail.tracking.duration.mixin





- Campos:

  - **active** (Boolean) → Active


  - **candidate_id** (Many2one) → hr.candidate


  - **partner_id** (Many2one)


  - **partner_name** (Char)


  - **email_from** (Char)


  - **email_normalized** (Char)


  - **partner_phone** (Char)


  - **partner_phone_sanitized** (Char)


  - **linkedin_profile** (Char)


  - **type_id** (Many2one)


  - **availability** (Date)


  - **color** (Integer)


  - **employee_id** (Many2one)


  - **emp_is_active** (Boolean)


  - **employee_name** (Char)


  - **probability** (Float) → Probability


  - **create_date** (Datetime) → Applied on


  - **stage_id** (Many2one) → hr.recruitment.stage


  - **last_stage_id** (Many2one) → hr.recruitment.stage


  - **categ_ids** (Many2many) → hr.applicant.category


  - **company_id** (Many2one) → res.company


  - **user_id** (Many2one) → res.users


  - **date_closed** (Datetime) → Hire Date


  - **date_open** (Datetime) → Assigned


  - **date_last_stage_update** (Datetime) → Last Stage Update


  - **priority** (Selection)


  - **job_id** (Many2one) → hr.job


  - **salary_proposed_extra** (Char) → Proposed Salary Extra


  - **salary_expected_extra** (Char) → Expected Salary Extra


  - **salary_proposed** (Float) → Proposed


  - **salary_expected** (Float) → Expected


  - **department_id** (Many2one) → hr.department


  - **day_open** (Float)


  - **day_close** (Float)


  - **delay_close** (Float)


  - **user_email** (Char)


  - **attachment_number** (Integer)


  - **attachment_ids** (One2many) → ir.attachment


  - **kanban_state** (Selection)


  - **legend_blocked** (Char)


  - **legend_done** (Char)


  - **legend_normal** (Char)


  - **refuse_reason_id** (Many2one) → hr.applicant.refuse.reason


  - **meeting_ids** (One2many) → calendar.event


  - **meeting_display_text** (Char)


  - **meeting_display_date** (Date)


  - **campaign_id** (Many2one)


  - **medium_id** (Many2one)


  - **source_id** (Many2one)


  - **interviewer_ids** (Many2many) → res.users


  - **application_status** (Selection)


  - **other_applications_count** (Integer)


  - **applicant_properties** (Properties) → Properties


  - **applicant_notes** (Html)


  - **refuse_date** (Datetime) → Refuse Date





### hr.department


- Hereda de:

  - hr.department




- Campos:

  - **new_applicant_count** (Integer)


  - **new_hired_employee** (Integer)


  - **expected_employee** (Integer)





### hr.recruitment.stage


- Hereda de: Base



- Campos:

  - **name** (Char) → Stage Name


  - **sequence** (Integer) → Sequence


  - **job_ids** (Many2many) → hr.job


  - **requirements** (Text) → Requirements


  - **template_id** (Many2one) → mail.template


  - **fold** (Boolean) → Folded in Kanban


  - **hired_stage** (Boolean) → Hired Stage


  - **legend_blocked** (Char) → Red Kanban Label


  - **legend_done** (Char) → Green Kanban Label


  - **legend_normal** (Char) → Grey Kanban Label


  - **is_warning_visible** (Boolean)





### hr.job.platform


- Hereda de: Base



- Campos:

  - **name** (Char)


  - **email** (Char)


  - **regex** (Char)





### utm.campaign


- Hereda de:

  - utm.campaign




- No agrega campos



### hr.candidate


- Hereda de:


  - mail.thread.cc

  - mail.thread.main.attachment

  - mail.thread.blacklist

  - mail.thread.phone

  - mail.activity.mixin





- Campos:

  - **active** (Boolean) → Active


  - **company_id** (Many2one) → res.company


  - **applicant_ids** (One2many) → hr.applicant


  - **application_count** (Integer)


  - **partner_id** (Many2one) → res.partner


  - **partner_name** (Char) → Candidates's Name


  - **email_from** (Char)


  - **email_normalized** (Char)


  - **partner_phone** (Char)


  - **partner_phone_sanitized** (Char)


  - **linkedin_profile** (Char) → LinkedIn Profile


  - **type_id** (Many2one) → hr.recruitment.degree


  - **availability** (Date) → Availability


  - **categ_ids** (Many2many) → hr.applicant.category


  - **color** (Integer) → Color Index


  - **priority** (Selection)


  - **user_id** (Many2one) → res.users


  - **employee_id** (Many2one) → hr.employee


  - **emp_is_active** (Boolean)


  - **employee_name** (Char)


  - **similar_candidates_count** (Integer)


  - **applications_count** (Integer)


  - **refused_applications_count** (Integer)


  - **accepted_applications_count** (Integer)


  - **meeting_ids** (One2many) → calendar.event


  - **meeting_display_text** (Char)


  - **meeting_display_date** (Date)


  - **attachment_count** (Integer)


  - **candidate_properties** (Properties) → Properties


  - **attachment_ids** (One2many) → ir.attachment





### hr.applicant.refuse.reason


- Hereda de: Base



- Campos:

  - **sequence** (Integer)


  - **name** (Char) → Description


  - **template_id** (Many2one) → mail.template


  - **active** (Boolean) → Active





### mail.activity.plan


- Hereda de:

  - mail.activity.plan




- No agrega campos



### hr.recruitment.degree


- Hereda de: Base



- Campos:

  - **name** (Char) → Degree Name


  - **sequence** (Integer) → Sequence





### hr.employee


- Hereda de:

  - hr.employee




- Campos:

  - **candidate_id** (One2many) → hr.candidate





### digest.digest


- Hereda de:

  - digest.digest




- Campos:

  - **kpi_hr_recruitment_new_colleagues** (Boolean) → New Employees


  - **kpi_hr_recruitment_new_colleagues_value** (Integer)





### hr.job


- Hereda de:


  - mail.alias.mixin

  - hr.job





- Campos:

  - **address_id** (Many2one) → res.partner


  - **application_ids** (One2many) → hr.applicant


  - **application_count** (Integer)


  - **all_application_count** (Integer)


  - **new_application_count** (Integer)


  - **old_application_count** (Integer)


  - **applicant_hired** (Integer)


  - **manager_id** (Many2one) → hr.employee


  - **user_id** (Many2one) → res.users


  - **allowed_user_ids** (Many2many) → res.users


  - **document_ids** (One2many) → ir.attachment


  - **documents_count** (Integer)


  - **alias_id** (Many2one)


  - **color** (Integer) → Color Index


  - **is_favorite** (Boolean)


  - **favorite_user_ids** (Many2many) → res.users


  - **interviewer_ids** (Many2many) → res.users


  - **extended_interviewer_ids** (Many2many) → res.users


  - **industry_id** (Many2one) → res.partner.industry


  - **date_from** (Date)


  - **date_to** (Date)


  - **activities_overdue** (Integer)


  - **activities_today** (Integer)


  - **job_properties** (Properties) → Properties


  - **applicant_properties_definition** (PropertiesDefinition) → Applicant Properties


  - **no_of_hired_employee** (Integer)





### utm.source


- Hereda de:

  - utm.source




- No agrega campos



### res.users


- Hereda de:

  - res.users




- No agrega campos



### calendar.event


- Hereda de:

  - calendar.event




- Campos:

  - **applicant_id** (Many2one) → hr.applicant


  - **candidate_id** (Many2one) → hr.candidate





### ['res.config.settings']


- Hereda de:


  - res.config.settings





- Campos:

  - **module_website_hr_recruitment** (Boolean)


  - **module_hr_recruitment_survey** (Boolean)


  - **group_applicant_cv_display** (Boolean)


  - **module_hr_recruitment_extract** (Boolean)





### ir.ui.menu


- Hereda de:

  - ir.ui.menu




- No agrega campos



### hr.recruitment.source


- Hereda de:


  - utm.source.mixin





- Campos:

  - **email** (Char)


  - **has_domain** (Char)


  - **job_id** (Many2one) → hr.job


  - **alias_id** (Many2one) → mail.alias


  - **medium_id** (Many2one) → utm.medium





### res.company


- Hereda de:

  - res.company




- Campos:

  - **candidate_properties_definition** (PropertiesDefinition) → Candidate Properties


  - **job_properties_definition** (PropertiesDefinition) → Job Properties





### hr.applicant.category


- Hereda de: Base



- Campos:

  - **name** (Char) → Tag Name


  - **color** (Integer)








## Vistas


### hr.recruitment.stage

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | hr.recruitment.stage.list | `hr_recruitment.hr_recruitment_stage_tree` | - |
| kanban | hr.recruitment.stage.kanban | `hr_recruitment.view_hr_recruitment_stage_kanban` | - |
| form | hr.recruitment.stage.form | `hr_recruitment.hr_recruitment_stage_form` | - |



### hr.applicant.category

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | hr.applicant.category.form | `hr_recruitment.hr_applicant_category_view_form` | - |
| list | hr.applicant.category.list | `hr_recruitment.hr_applicant_category_view_tree` | - |



### hr.applicant

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | Applicants | `hr_recruitment.crm_case_tree_view_job` | - |
| list | hr.applicant.view.list.activity | `hr_recruitment.hr_applicant_view_tree_activity` | - |
| form | Jobs - Recruitment Form | `hr_recruitment.hr_applicant_view_form` | - |
| pivot | Jobs - Recruitment | `hr_recruitment.crm_case_pivot_view_job` | - |
| graph | Jobs - Recruitment Graph | `hr_recruitment.crm_case_graph_view_job` | - |
| search | hr.applicant.view.search | `hr_recruitment.hr_applicant_view_search_bis` | - |
| calendar | Hr Applicants Calendar | `hr_recruitment.hr_applicant_calendar_view` | - |
| form | hr.applicant.form.quick_create | `hr_recruitment.quick_create_applicant_form` | - |
| kanban | Hr Applicants kanban | `hr_recruitment.hr_kanban_view_applicant` | - |
| activity | hr.applicant.activity | `hr_recruitment.hr_applicant_view_activity` | - |
| pivot | hr.applicant.pivot | `hr_recruitment.hr_applicant_view_pivot` | - |
| graph | hr.applicant.graph | `hr_recruitment.hr_applicant_view_graph` | - |
| search | hr.applicant.search | `hr_recruitment.hr_applicant_view_search` | - |



#### Botones (hr_recruitment.hr_applicant_view_form)
- **Create Employee** (object) - Grupos: `hr.group_hr_user`
- **Refuse** (object)
- **Restore** (object)
- **action_open_employee** (object) - Grupos: `hr.group_hr_user`
- **action_open_other_applications** (object)
- **action_create_meeting** (object)


#### Filtros de búsqueda (hr_recruitment.hr_applicant_view_search_bis)

**Filtros:**
- **My Applications** (`[('user_id', '=', uid)]`)
- **Unassigned** (`[('user_id', '=', False)]`)
- **In Progress** (`[('date_closed', '=', False), ('active', '=', True), ('refuse_reason_id', '=', False)]`)
- **Hired** (`[('date_closed', '!=', False)]`)
- **Ready for Next Stage** (`[('kanban_state', '=', 'done')]`)
- **Blocked** (`[('kanban_state', '=', 'blocked')]`)
- **Directly Available** (`['|',('availability', '<=', context_today().strftime('%Y-%m-%d')),('availability','=', False)]`)
- **Creation Date**
- **Last Stage Update**
- **Unread Messages** (`[('message_needaction', '=', True)]`)
- **Archived** (`[('active', '=', False), ('refuse_reason_id', '=', False)]`)
- **Refused** (`[('active', '=', False), ('refuse_reason_id', '!=', False)]`)
- **Late Activities** (`[('my_activity_date_deadline', '<', context_today().strftime('%Y-%m-%d'))]`)
- **Today Activities** (`[('my_activity_date_deadline', '=', context_today().strftime('%Y-%m-%d'))]`)
- **Future Activities** (`[('my_activity_date_deadline', '>', context_today().strftime('%Y-%m-%d'))]`)
- **Running Applicants** (`[('stage_id.hired_stage', '=', False)]`)


**Agrupar por:**
- Job
- Stage
- Candidate
- Responsible
- Creation Date
- Hiring Date
- Last Stage Update
- Refuse Reason
- Company


#### Filtros de búsqueda (hr_recruitment.hr_applicant_view_search)

**Filtros:**
- **Creation Date**
- **Unassigned** (`[('user_id', '=', False)]`)
- **New** (`[('stage_id.sequence', '=', 1)]`)
- **Ongoing** (`[('active', '=', True)]`)
- **Refused** (`[('active', '=', False)]`)
- **Archived** (`[('active', '=', False)]`)


**Agrupar por:**
- Responsible
- Company
- Jobs
- Department
- Tags
- Stage
- Creation Date


### hr.applicant.refuse.reason

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | Applicant refuse reason form | `hr_recruitment.hr_applicant_refuse_reason_view_form` | - |
| list | Applicant refuse reason list | `hr_recruitment.hr_applicant_refuse_reason_view_tree` | - |



### hr.recruitment.degree

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | hr.recruitment.degree.list | `hr_recruitment.hr_recruitment_degree_tree` | - |
| form | hr.recruitment.degree.form | `hr_recruitment.hr_recruitment_degree_form` | - |



### hr.job

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| kanban | hr.job.kanban | `hr_recruitment.view_hr_job_kanban` | - |
| form | hr.job.simple.form | `hr_recruitment.hr_job_simple_form` | - |
| list | - | `hr_recruitment.hr_job_view_tree_inherit` | hr.view_hr_job_tree |



#### Botones (hr_recruitment.hr_job_simple_form)
- **Create** (action)


### hr.job.platform

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | hr.job.platform.form | `hr_recruitment.hr_job_platform_form` | - |
| list | hr.job.platform.list | `hr_recruitment.hr_job_platform_tree` | - |



### ir.attachment

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | - | `hr_recruitment.ir_attachment_hr_recruitment_list_view` | - |



### hr.recruitment.source

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | hr.recruitment.source.list | `hr_recruitment.hr_recruitment_source_tree` | - |
| search | hr.recruitment.source.view.search | `hr_recruitment.hr_recruitment_source_view_search` | - |



### hr.candidate

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | hr.candidate.view.form | `hr_recruitment.hr_candidate_view_form` | - |
| list | hr.candidate.view.list | `hr_recruitment.hr_candidate_view_tree` | - |
| kanban | hr.candidate.view.kanban | `hr_recruitment.hr_candidate_view_kanban` | - |
| calendar | hr.candidate.view.calendar | `hr_recruitment.hr_candidate_view_calendar` | - |
| search | hr.candidate.view.search | `hr_recruitment.hr_candidate_view_search` | - |



#### Botones (hr_recruitment.hr_candidate_view_form)
- **Create Employee** (object) - Grupos: `hr.group_hr_user`
- **action_open_employee** (object) - Grupos: `hr.group_hr_user`
- **action_open_applications** (object)
- **action_open_similar_candidates** (object)
- **action_create_meeting** (object)


#### Filtros de búsqueda (hr_recruitment.hr_candidate_view_search)

**Filtros:**
- **My Candidates** (`[('user_id', '=', uid)]`)
- **Unassigned** (`[('user_id', '=', False)]`)
- **Application in Progress** (`[('applicant_ids.application_status', '=', 'ongoing')]`)
- **Waiting** (`[('applicant_ids', '=', False)]`)
- **Hired** (`[('applicant_ids.application_status', '=', 'hired')]`)
- **Directly Available** (`                 [                     '&',                         '|',                             ('availability', '<=', context_today().strftime('%Y-%m-%d')),                             ('availability', '=', False),                         '!',                             ('applicant_ids', 'any',                                 [                                     '&',                                         ('application_status', '=', 'hired'),                                     '|',                                         ('availability', '>=', context_today().strftime('%Y-%m-%d')),                                         ('availability', '=', False),                                 ]                             )                 ]`)
- **Creation Date**
- **Refused** (`[('applicant_ids.application_status', '=', 'refused')]`)
- **Archived** (`[('active', '=', False)]`)


**Agrupar por:**
- Manager


### candidate.send.mail

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | - | `hr_recruitment.candidate_send_mail_view_form` | - |



#### Botones (hr_recruitment.candidate_send_mail_view_form)
- **Send** (object)


### applicant.get.refuse.reason

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | applicant.get.refuse.reason.form | `hr_recruitment.applicant_get_refuse_reason_view_form` | - |



#### Botones (hr_recruitment.applicant_get_refuse_reason_view_form)
- **Refuse** (object)


### applicant.send.mail

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | - | `hr_recruitment.applicant_send_mail_view_form` | - |



#### Botones (hr_recruitment.applicant_send_mail_view_form)
- **Send** (object)

