# Módulo: Project

## Información General
- **Nombre técnico:** project
- **Versión:** 1.3
- **Categoría:** Services/Project
- **Dependencias:** analytic, base_setup, mail, portal, rating, resource, web, web_tour, digest


## Propósito
Organize and plan your projects





## Modelos

### digest.digest


- Hereda de:

  - digest.digest




- Campos:

  - **kpi_project_task_opened** (Boolean) → Open Tasks


  - **kpi_project_task_opened_value** (Integer)





### project.collaborator


- Hereda de: Base



- Campos:

  - **project_id** (Many2one) → project.project


  - **partner_id** (Many2one) → res.partner


  - **partner_email** (Char)


  - **limited_access** (Boolean) → Limited Access





### project.project.stage


- Hereda de: Base



- Campos:

  - **active** (Boolean)


  - **sequence** (Integer)


  - **name** (Char)


  - **mail_template_id** (Many2one) → mail.template


  - **fold** (Boolean) → Folded in Kanban


  - **company_id** (Many2one) → res.company





### project.task.stage.personal


- Hereda de: Base



- Campos:

  - **task_id** (Many2one) → project.task


  - **user_id** (Many2one) → res.users


  - **stage_id** (Many2one) → project.task.type





### project.task.recurrence


- Hereda de: Base



- Campos:

  - **task_ids** (One2many) → project.task


  - **repeat_interval** (Integer)


  - **repeat_unit** (Selection)


  - **repeat_type** (Selection)


  - **repeat_until** (Date)





### project.task.type


- Hereda de: Base



- Campos:

  - **active** (Boolean) → Active


  - **name** (Char)


  - **sequence** (Integer)


  - **project_ids** (Many2many) → project.project


  - **mail_template_id** (Many2one) → mail.template


  - **fold** (Boolean)


  - **rating_template_id** (Many2one) → mail.template


  - **auto_validation_state** (Boolean) → Automatic Kanban Status


  - **disabled_rating_warning** (Text)


  - **user_id** (Many2one) → res.users





### project.tags


- Hereda de: Base



- Campos:

  - **name** (Char) → Name


  - **color** (Integer)


  - **project_ids** (Many2many) → project.project


  - **task_ids** (Many2many) → project.task





### project.project


- Hereda de:


  - portal.mixin

  - mail.alias.mixin

  - rating.parent.mixin

  - mail.thread

  - mail.activity.mixin

  - mail.tracking.duration.mixin

  - analytic.plan.fields.mixin





- Campos:

  - **name** (Char) → Name


  - **description** (Html)


  - **active** (Boolean)


  - **sequence** (Integer)


  - **partner_id** (Many2one) → res.partner


  - **company_id** (Many2one) → res.company


  - **currency_id** (Many2one) → res.currency


  - **analytic_account_balance** (Monetary)


  - **account_id** (Many2one) → account.analytic.account


  - **favorite_user_ids** (Many2many) → res.users


  - **is_favorite** (Boolean)


  - **label_tasks** (Char)


  - **tasks** (One2many) → project.task


  - **resource_calendar_id** (Many2one) → resource.calendar


  - **type_ids** (Many2many) → project.task.type


  - **task_count** (Integer)


  - **open_task_count** (Integer)


  - **task_ids** (One2many) → project.task


  - **color** (Integer)


  - **user_id** (Many2one) → res.users


  - **alias_id** (Many2one)


  - **privacy_visibility** (Selection)


  - **privacy_visibility_warning** (Char) → Privacy Visibility Warning


  - **access_instruction_message** (Char) → Access Instruction Message


  - **date_start** (Date)


  - **date** (Date)


  - **allow_task_dependencies** (Boolean) → Task Dependencies


  - **allow_milestones** (Boolean) → Milestones


  - **tag_ids** (Many2many) → project.tags


  - **task_properties_definition** (PropertiesDefinition) → Task Properties


  - **closed_task_count** (Integer)


  - **task_completion_percentage** (Float)


  - **collaborator_ids** (One2many) → project.collaborator


  - **collaborator_count** (Integer) → # Collaborators


  - **rating_request_deadline** (Datetime)


  - **rating_active** (Boolean) → Customer Ratings


  - **rating_status** (Selection)


  - **rating_status_period** (Selection)


  - **stage_id** (Many2one) → project.project.stage


  - **duration_tracking** (Json)


  - **update_ids** (One2many) → project.update


  - **update_count** (Integer)


  - **last_update_id** (Many2one) → project.update


  - **last_update_status** (Selection)


  - **last_update_color** (Integer)


  - **milestone_ids** (One2many) → project.milestone


  - **milestone_count** (Integer)


  - **milestone_count_reached** (Integer)


  - **is_milestone_exceeded** (Boolean)


  - **milestone_progress** (Integer) → Milestones Reached


  - **next_milestone_id** (Many2one) → project.milestone


  - **can_mark_milestone_as_done** (Boolean)


  - **is_milestone_deadline_exceeded** (Boolean)





### account.analytic.account


- Hereda de:

  - account.analytic.account




- Campos:

  - **project_ids** (One2many) → project.project


  - **project_count** (Integer) → Project Count





### mail.message


- Hereda de:

  - mail.message




- No agrega campos



### project.update


- Hereda de:


  - mail.thread.cc

  - mail.activity.mixin





- Campos:

  - **name** (Char) → Title


  - **status** (Selection)


  - **color** (Integer)


  - **progress** (Integer)


  - **progress_percentage** (Float)


  - **user_id** (Many2one) → res.users


  - **description** (Html)


  - **date** (Date)


  - **project_id** (Many2one) → project.project


  - **name_cropped** (Char)


  - **task_count** (Integer) → Task Count


  - **closed_task_count** (Integer) → Closed Task Count


  - **closed_task_percentage** (Integer) → Closed Task Percentage





### res.config.settings


- Hereda de:

  - res.config.settings




- Campos:

  - **module_hr_timesheet** (Boolean)


  - **group_project_rating** (Boolean) → Customer Ratings


  - **group_project_stages** (Boolean) → Project Stages


  - **group_project_recurring_tasks** (Boolean) → Recurring Tasks


  - **group_project_task_dependencies** (Boolean) → Task Dependencies


  - **group_project_milestone** (Boolean) → Milestones





### ir.ui.menu


- Hereda de:

  - ir.ui.menu




- No agrega campos



### res.partner


- Hereda de:

  - res.partner




- Campos:

  - **project_ids** (One2many) → project.project


  - **task_ids** (One2many) → project.task


  - **task_count** (Integer)





### project.milestone


- Hereda de:


  - mail.thread





- Campos:

  - **name** (Char)


  - **project_id** (Many2one) → project.project


  - **deadline** (Date)


  - **is_reached** (Boolean)


  - **reached_date** (Date)


  - **task_ids** (One2many) → project.task


  - **is_deadline_exceeded** (Boolean)


  - **is_deadline_future** (Boolean)


  - **task_count** (Integer) → # of Tasks


  - **done_task_count** (Integer) → # of Done Tasks


  - **can_be_marked_as_done** (Boolean)





### project.task


- Hereda de:


  - portal.mixin

  - mail.thread.cc

  - mail.activity.mixin

  - rating.mixin

  - mail.tracking.duration.mixin

  - html.field.history.mixin





- Campos:

  - **active** (Boolean)


  - **name** (Char)


  - **description** (Html)


  - **priority** (Selection)


  - **sequence** (Integer)


  - **stage_id** (Many2one) → project.task.type


  - **tag_ids** (Many2many) → project.tags


  - **state** (Selection)


  - **is_closed** (Boolean) → Closed state


  - **create_date** (Datetime) → Created On


  - **write_date** (Datetime) → Last Updated On


  - **date_end** (Datetime)


  - **date_assign** (Datetime)


  - **date_deadline** (Datetime)


  - **date_last_stage_update** (Datetime)


  - **project_id** (Many2one) → project.project


  - **display_in_project** (Boolean)


  - **show_display_in_project** (Boolean)


  - **task_properties** (Properties) → Properties


  - **allocated_hours** (Float) → Allocated Time


  - **subtask_allocated_hours** (Float) → Sub-tasks Allocated Time


  - **user_ids** (Many2many) → res.users


  - **portal_user_names** (Char)


  - **personal_stage_type_ids** (Many2many) → project.task.type


  - **personal_stage_id** (Many2one) → project.task.stage.personal


  - **personal_stage_type_id** (Many2one) → project.task.type


  - **partner_id** (Many2one) → res.partner


  - **email_cc** (Char)


  - **company_id** (Many2one) → res.company


  - **color** (Integer)


  - **rating_active** (Boolean)


  - **attachment_ids** (One2many) → ir.attachment


  - **displayed_image_id** (Many2one) → ir.attachment


  - **parent_id** (Many2one) → project.task


  - **child_ids** (One2many) → project.task


  - **subtask_count** (Integer) → Sub-task Count


  - **closed_subtask_count** (Integer) → Closed Sub-tasks Count


  - **project_privacy_visibility** (Selection)


  - **subtask_completion_percentage** (Float)


  - **working_hours_open** (Float)


  - **working_hours_close** (Float)


  - **working_days_open** (Float)


  - **working_days_close** (Float)


  - **website_message_ids** (One2many)


  - **allow_milestones** (Boolean)


  - **milestone_id** (Many2one) → project.milestone


  - **has_late_and_unreached_milestone** (Boolean)


  - **allow_task_dependencies** (Boolean)


  - **depend_on_ids** (Many2many) → project.task


  - **depend_on_count** (Integer)


  - **closed_depend_on_count** (Integer)


  - **dependent_ids** (Many2many) → project.task


  - **dependent_tasks_count** (Integer)


  - **display_parent_task_button** (Boolean)


  - **current_user_same_company_partner** (Boolean)


  - **display_follow_button** (Boolean)


  - **recurring_task** (Boolean)


  - **recurring_count** (Integer)


  - **recurrence_id** (Many2one) → project.task.recurrence


  - **repeat_interval** (Integer)


  - **repeat_unit** (Selection)


  - **repeat_type** (Selection)


  - **repeat_until** (Date)


  - **display_name** (Char)


  - **link_preview_name** (Char)








## Vistas


### project.update

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| search | project.update.view.search | `project.project_update_view_search` | - |
| form | project.update.view.form | `project.project_update_view_form` | - |
| kanban | project.update.view.kanban | `project.project_update_view_kanban` | - |
| list | project.update.view.list | `project.project_update_view_tree` | - |



#### Filtros de búsqueda (project.project_update_view_search)

**Filtros:**
- **My Updates** (`[('user_id', '=', uid)]`)
- **Followed Updates** (`[('message_is_follower', '=', True)]`)
- **On Track** (`[('status', '=', 'on_track')]`)
- **At Risk** (`[('status', '=', 'at_risk')]`)
- **Off Track** (`[('status', '=', 'off_track')]`)
- **On Hold** (`[('status', '=', 'on_hold')]`)
- **Date**


### project.milestone

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | project.milestone.view.form | `project.project_milestone_view_form` | - |
| list | project.milestone.view.list | `project.project_milestone_view_tree` | - |



#### Botones (project.project_milestone_view_form)
- **%(project.action_view_task_from_milestone)d** (action) - Grupos: `project.group_project_milestone`


### project.task.type

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| search | project.task.type.search | `project.task_type_search` | - |
| form | project.task.type.form | `project.task_type_edit` | - |
| list | project.task.type.list | `project.task_type_tree` | - |
| kanban | project.task.type.kanban | `project.view_project_task_type_kanban` | - |



#### Filtros de búsqueda (project.task_type_search)

**Filtros:**
- **Archived** (`[('active', '=', False)]`)


### project.task

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| search | project.task.search.form | `project.view_task_search_form_base` | - |
| graph | project.task.graph | `project.view_project_task_graph` | - |
| pivot | project.task.pivot | `project.view_project_task_pivot` | - |
| form | project.task.form | `project.view_task_form2` | - |
| form | project.task.form.quick_create | `project.quick_create_task_form` | - |
| form | project.task.convert.to.subtask.form | `project.project_task_convert_to_subtask_view_form` | - |
| kanban | project.task.kanban | `project.view_task_kanban` | - |
| list | project.task.view.list.main.base | `project.project_task_view_tree_main_base` | - |
| list | project.task.view.list.base | `project.project_task_view_tree_base` | project_task_view_tree_main_base |
| list | project.task.list | `project.view_task_tree2` | project_task_view_tree_base |
| calendar | project.task.calendar | `project.view_task_calendar` | - |
| activity | project.task.activity | `project.project_task_view_activity` | - |
| list | open.view.my.tasks.list.view | `project.open_view_my_tasks_list_view` | view_task_tree2 |
| list | open.view.all.tasks.list.view | `project.open_view_all_tasks_list_view` | view_task_tree2 |
| kanban | project.task.kanban.sale.order | `project.view_task_kanban_inherit_view_default_project` | view_task_kanban |
| form | project.task.form.quick_create | `project.project_sharing_quick_create_task_form` | - |
| kanban | project.sharing.project.task.view.kanban | `project.project_sharing_project_task_view_kanban` | - |
| list | project.sharing.project.task.list | `project.project_sharing_project_task_view_tree` | project_task_view_tree_main_base |
| form | project.sharing.project.task.view.form | `project.project_sharing_project_task_view_form` | - |
| list | open.view.blocked.by.list.view | `project.open_view_blocked_by_list_view` | project.open_view_all_tasks_list_view |



#### Filtros de búsqueda (project.view_task_search_form_base)

**Filtros:**
- **Followed** (`[('message_is_follower', '=', True)]`)
- **Unassigned** (`[('user_ids', '=', False)]`)
- **Favorite Projects** (`[('project_id.is_favorite', '=', True)]`)
- **Starred Tasks** (`[('priority', '=', '1')]`)
- **Blocked** (`[('state', '=', '04_waiting_normal')]`)
- **Blocking** (`[('is_closed', '=', False), ('dependent_ids', '!=', False)]`)
- **Last Stage Update**
- **Open Tasks** (`[('is_closed', '=', False)]`)
- **Closed Tasks** (`[('is_closed', '=', True)]`)
- **Closed On** (`[('is_closed', '=', True)]`)
- **Last 30 Days** (`[('date_last_stage_update', '>', datetime.datetime.combine(context_today() - relativedelta(days=30), datetime.time(23, 59, 59)).to_utc())]`)
- **Last 365 Days** (`[('date_last_stage_update', '>', datetime.datetime.combine(context_today() - relativedelta(days=365), datetime.time(23, 59, 59)).to_utc())]`)
- **Archived** (`[('active', '=', False)]`)


**Agrupar por:**
- Stage
- Milestone
- Tags
- Customer
- Company
- Creation Date
- Assignement Date
- Last Stage Update


#### Botones (project.view_task_form2)
- **action_open_ratings** (object) - Grupos: `project.group_project_rating`
- **action_open_parent_task** (object)
- **action_recurring_tasks** (object) - Grupos: `project.group_project_recurring_tasks`
- **%(project_task_action_sub_task)d** (action)
- **action_dependent_tasks** (object) - Grupos: `project.group_project_task_dependencies`


#### Botones (project.project_sharing_project_task_view_form)
- **action_project_sharing_view_parent_task** (object)
- **action_project_sharing_recurring_tasks** (object)
- **action_project_sharing_open_subtasks** (object)
- **action_project_sharing_open_blocking** (object)
- **View Task** (object)
- **View Task** (object)


### project.project.stage

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | project.project.stage.view.list | `project.project_project_stage_view_tree` | - |
| form | project.project.stage.view.form.quick.create | `project.project_project_stage_view_form_quick_create` | - |
| form | project.project.stage.view.form | `project.project_project_stage_view_form` | - |
| kanban | project.project.stage.view.kanban | `project.project_project_stage_view_kanban` | - |
| search | project.project.stage.view.search | `project.project_project_stage_view_search` | - |



#### Filtros de búsqueda (project.project_project_stage_view_search)

**Filtros:**
- **Archived** (`[('active', '=', False)]`)


**Agrupar por:**
- Company


### project.project

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| activity | project.project.view.activity | `project.project_project_view_activity` | - |
| form | project.project.form | `project.edit_project` | - |
| search | project.project.select | `project.view_project_project_filter` | - |
| list | project.project.list | `project.view_project` | - |
| list | project.project.list.group.stage | `project.project_list_view_group_stage` | view_project |
| list | project.project.list.config.group.stage | `project.view_project_config_group_stage` | view_project_config |
| form | project.form.quick_create | `project.quick_create_project_form` | - |
| kanban | project.project.kanban | `project.project_view_kanban` | - |
| form | project.project.view.form.simplified | `project.project_project_view_form_simplified` | - |
| kanban | project.project.kanban | `project.view_project_kanban` | - |
| calendar | project.project.calendar | `project.view_project_calendar` | - |



#### Botones (project.edit_project)
- **Share Project** (object) - Grupos: `project.group_project_manager`
- **action_view_tasks** (object)
- **project_update_all_action** (object) - Grupos: `project.group_project_user`
- **Set a Rating Email Template on Stages** (action)


#### Filtros de búsqueda (project.view_project_project_filter)

**Filtros:**
- **My Projects** (`[('user_id', '=', uid)]`)
- **My Favorites** (`[('favorite_user_ids', 'in', uid)]`)
- **Unassigned** (`[('user_id', '=', False)]`)
- **Late Milestones** (`[('is_milestone_exceeded', '=', True)]`)
- **Start Date**
- **End Date**
- **Archived** (`[('active', '=', False)]`)
- **Late Activities** (`[('my_activity_date_deadline', '<', context_today().strftime('%Y-%m-%d'))]`)
- **Today Activities** (`[('my_activity_date_deadline', '=', context_today().strftime('%Y-%m-%d'))]`)
- **Future Activities** (`[('my_activity_date_deadline', '>', context_today().strftime('%Y-%m-%d'))]`)


**Agrupar por:**
- Project Manager
- Stage
- Status
- Tags
- Company


### project.tags

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| search | Tags | `project.project_tags_search_view` | - |
| form | Tags | `project.project_tags_form_view` | - |
| list | Tags | `project.project_tags_tree_view` | - |



### project.project.stage.delete.wizard

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | project.project.stage.delete.wizard.form | `project.view_project_project_stage_delete_wizard` | - |
| form | project.project.stage.delete.wizard.form | `project.view_project_project_stage_unarchive_wizard` | - |



#### Botones (project.view_project_project_stage_delete_wizard)
- **Archive Stages** (object)
- **Delete** (object)


#### Botones (project.view_project_project_stage_unarchive_wizard)
- **Confirm** (object)


### project.share.wizard

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | project.share.wizard.view.form | `project.project_share_wizard_view_form` | - |
| form | project.share.wizard.view.form | `project.project_share_wizard_confirm_form` | - |



#### Botones (project.project_share_wizard_view_form)
- **Share Project** (object)


#### Botones (project.project_share_wizard_confirm_form)
- **Grant Portal Access** (object)


### project.task.type.delete.wizard

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | project.task.type.delete.wizard.form | `project.view_project_task_type_delete_wizard` | - |
| form | project.task.type.delete.wizard.form | `project.view_project_task_type_delete_confirmation_wizard` | - |
| form | project.task.type.delete.wizard.form | `project.view_project_task_type_unarchive_wizard` | - |



#### Botones (project.view_project_task_type_delete_wizard)
- **Archive Stages** (object)
- **Delete** (object)


#### Botones (project.view_project_task_type_delete_confirmation_wizard)
- **Confirm** (object)


#### Botones (project.view_project_task_type_unarchive_wizard)
- **Confirm** (object)


### project.task.burndown.chart.report

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| search | project.task.burndown.chart.report.view.search | `project.project_task_burndown_chart_report_view_search` | - |
| graph | project.task.burndown.chart.report.view.graph | `project.project_task_burndown_chart_report_view_graph` | - |



#### Filtros de búsqueda (project.project_task_burndown_chart_report_view_search)

**Filtros:**
- **My Tasks** (`[('user_ids', 'in', uid)]`)
- **Unassigned** (`[('user_ids', '=', False)]`)
- **Date**
- **filter_last_stage_update**
- **filter_date_deadline**
- **Last Month** (`[('date','>=', (context_today() - datetime.timedelta(days=30)).strftime('%Y-%m-%d'))]`)
- **Open Tasks** (`[('is_closed', '=', 'open')]`)
- **Closed Tasks** (`[('is_closed', '=', 'closed')]`)


**Agrupar por:**
- Date
- Stage (Burndown Chart)
- Is Closed (Burn-up Chart)


### report.project.task.user

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| pivot | report.project.task.user.pivot | `project.view_task_project_user_pivot` | - |
| pivot | report.project.task.user.pivot | `project.view_task_project_user_fsm_pivot_base` | view_task_project_user_pivot |
| graph | report.project.task.user.graph | `project.view_task_project_user_graph` | - |
| graph | report.project.task.user.graph | `project.view_task_project_user_fsm_graph_base` | view_task_project_user_graph |
| search | report.project.task.user.search | `project.view_task_project_user_search` | project.view_task_search_form_project_fsm_base |


