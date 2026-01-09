# Módulo: Gamification

## Información General
- **Nombre técnico:** gamification
- **Versión:** 1.0
- **Categoría:** Human Resources
- **Dependencias:** mail




## Descripción

Gamification process
The Gamification module provides ways to evaluate and motivate the users of Odoo.

The users can be evaluated using goals and numerical objectives to reach.
**Goals** are assigned through **challenges** to evaluate and compare members of a team with each others and through time.

For non-numerical achievements, **badges** can be granted to users. From a simple "thank you" to an exceptional achievement, a badge is an easy way to exprimate gratitude to a user for their good work.

Both goals and badges are flexibles and can be adapted to a large range of modules and actions. When installed, this module creates easy goals to help new users to discover Odoo and configure their user profile.




## Modelos

### gamification.challenge


- Hereda de:

  - mail.thread




- Campos:

  - **name** (Char) → Challenge Name


  - **description** (Text) → Description


  - **state** (Selection)


  - **manager_id** (Many2one) → res.users


  - **user_ids** (Many2many) → res.users


  - **user_domain** (Char) → User domain


  - **user_count** (Integer) → # Users


  - **period** (Selection)


  - **start_date** (Date) → Start Date


  - **end_date** (Date) → End Date


  - **invited_user_ids** (Many2many) → res.users


  - **line_ids** (One2many) → gamification.challenge.line


  - **reward_id** (Many2one) → gamification.badge


  - **reward_first_id** (Many2one) → gamification.badge


  - **reward_second_id** (Many2one) → gamification.badge


  - **reward_third_id** (Many2one) → gamification.badge


  - **reward_failure** (Boolean) → Reward Bests if not Succeeded?


  - **reward_realtime** (Boolean) → Reward as soon as every goal is reached


  - **visibility_mode** (Selection)


  - **report_message_frequency** (Selection)


  - **report_message_group_id** (Many2one) → discuss.channel


  - **report_template_id** (Many2one) → mail.template


  - **remind_update_delay** (Integer) → Non-updated manual goals will be reminded after


  - **last_report_date** (Date) → Last Report Date


  - **next_report_date** (Date) → Next Report Date


  - **challenge_category** (Selection)





### gamification.goal


- Hereda de: Base



- Campos:

  - **definition_id** (Many2one) → gamification.goal.definition


  - **user_id** (Many2one) → res.users


  - **line_id** (Many2one) → gamification.challenge.line


  - **challenge_id** (Many2one)


  - **start_date** (Date) → Start Date


  - **end_date** (Date) → End Date


  - **target_goal** (Float) → To Reach


  - **current** (Float) → Current Value


  - **completeness** (Float) → Completeness


  - **state** (Selection)


  - **to_update** (Boolean) → To update


  - **closed** (Boolean) → Closed goal


  - **computation_mode** (Selection)


  - **color** (Integer) → Color Index


  - **remind_update_delay** (Integer) → Remind delay


  - **last_update** (Date) → Last Update


  - **definition_description** (Text) → Definition Description


  - **definition_condition** (Selection)


  - **definition_suffix** (Char) → Suffix


  - **definition_display** (Selection)





### gamification.badge.user


- Hereda de: Base



- Campos:

  - **user_id** (Many2one) → res.users


  - **sender_id** (Many2one) → res.users


  - **badge_id** (Many2one) → gamification.badge


  - **challenge_id** (Many2one) → gamification.challenge


  - **comment** (Text) → Comment


  - **badge_name** (Char)


  - **level** (Selection)





### gamification.karma.rank


- Hereda de:

  - image.mixin




- Campos:

  - **name** (Text)


  - **description** (Html)


  - **description_motivational** (Html)


  - **karma_min** (Integer)


  - **user_ids** (One2many) → res.users


  - **rank_users_count** (Integer) → # Users





### gamification.goal.definition


- Hereda de: Base



- Campos:

  - **name** (Char) → Goal Definition


  - **description** (Text) → Goal Description


  - **monetary** (Boolean) → Monetary Value


  - **suffix** (Char) → Suffix


  - **full_suffix** (Char) → Full Suffix


  - **computation_mode** (Selection)


  - **display_mode** (Selection)


  - **model_id** (Many2one) → ir.model


  - **model_inherited_ids** (Many2many) → ir.model


  - **field_id** (Many2one) → ir.model.fields


  - **field_date_id** (Many2one) → ir.model.fields


  - **domain** (Char) → Filter Domain


  - **batch_mode** (Boolean) → Batch Mode


  - **batch_distinctive_field** (Many2one) → ir.model.fields


  - **batch_user_expression** (Char) → Evaluated expression for batch mode


  - **compute_code** (Text) → Python Code


  - **condition** (Selection)


  - **action_id** (Many2one) → ir.actions.act_window


  - **res_id_field** (Char) → ID Field of user





### res.users


- Hereda de:

  - res.users




- Campos:

  - **karma** (Integer) → Karma


  - **karma_tracking_ids** (One2many) → gamification.karma.tracking


  - **badge_ids** (One2many) → gamification.badge.user


  - **gold_badge** (Integer) → Gold badges count


  - **silver_badge** (Integer) → Silver badges count


  - **bronze_badge** (Integer) → Bronze badges count


  - **rank_id** (Many2one) → gamification.karma.rank


  - **next_rank_id** (Many2one) → gamification.karma.rank





### gamification.badge


- Hereda de:


  - mail.thread

  - image.mixin





- Campos:

  - **name** (Char) → Badge


  - **active** (Boolean) → Active


  - **description** (Html) → Description


  - **level** (Selection)


  - **rule_auth** (Selection)


  - **rule_auth_user_ids** (Many2many) → res.users


  - **rule_auth_badge_ids** (Many2many) → gamification.badge


  - **rule_max** (Boolean) → Monthly Limited Sending


  - **rule_max_number** (Integer) → Limitation Number


  - **challenge_ids** (One2many) → gamification.challenge


  - **goal_definition_ids** (Many2many) → gamification.goal.definition


  - **owner_ids** (One2many) → gamification.badge.user


  - **granted_count** (Integer) → Total


  - **granted_users_count** (Integer) → Number of users


  - **unique_owner_ids** (Many2many) → res.users


  - **stat_this_month** (Integer) → Monthly total


  - **stat_my** (Integer) → My Total


  - **stat_my_this_month** (Integer) → My Monthly Total


  - **stat_my_monthly_sending** (Integer) → My Monthly Sending Total


  - **remaining_sending** (Integer) → Remaining Sending Allowed





### gamification.challenge.line


- Hereda de: Base



- Campos:

  - **challenge_id** (Many2one) → gamification.challenge


  - **definition_id** (Many2one) → gamification.goal.definition


  - **sequence** (Integer) → Sequence


  - **target_goal** (Float) → Target Value to Reach


  - **name** (Char) → Name


  - **condition** (Selection)


  - **definition_suffix** (Char) → Unit


  - **definition_monetary** (Boolean) → Monetary


  - **definition_full_suffix** (Char) → Suffix





### gamification.karma.tracking


- Hereda de: Base



- Campos:

  - **user_id** (Many2one) → res.users


  - **old_value** (Integer) → Old Karma Value


  - **new_value** (Integer) → New Karma Value


  - **gain** (Integer) → Gain


  - **consolidated** (Boolean) → Consolidated


  - **tracking_date** (Datetime)


  - **reason** (Text)


  - **origin_ref** (Reference)


  - **origin_ref_model_name** (Selection)








## Vistas


### gamification.goal.definition

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | Goal Definitions List | `gamification.goal_definition_list_view` | - |
| form | Goal Definitions Form | `gamification.goal_definition_form_view` | - |
| search | Goal Definition Search | `gamification.goal_definition_search_view` | - |



#### Filtros de búsqueda (gamification.goal_definition_search_view)


**Agrupar por:**
- Model
- Computation Mode


### gamification.badge

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| search | gamification.badge.view.search | `gamification.gamification_badge_view_search` | - |
| list | Badge List | `gamification.badge_list_view` | - |
| form | Badge Form | `gamification.badge_form_view` | - |
| kanban | Badge Kanban View | `gamification.badge_kanban_view` | - |



#### Filtros de búsqueda (gamification.gamification_badge_view_search)

**Filtros:**
- **Archived** (`[('active', '=', False)]`)


#### Botones (gamification.badge_form_view)
- **Grant this Badge** (action)


### gamification.karma.tracking

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| search | gamification.karma.tracking.view.search | `gamification.gamification_karma_tracking_view_search` | - |
| list | gamification.karma.tracking.view.list | `gamification.gamification_karma_tracking_view_tree` | - |
| form | gamification.karma.tracking.view.form | `gamification.gamification_karma_tracking_view_form` | - |



#### Filtros de búsqueda (gamification.gamification_karma_tracking_view_search)

**Filtros:**
- **Consolidated** (`[('consolidated', '=', True)]`)
- **My Karma** (`[('user_id', '=', uid)]`)
- **Manual** (`[('origin_ref', 'ilike', 'res.users,')]`)


**Agrupar por:**
- Granted By
- Source Type
- Karma Owner


### gamification.challenge

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | Challenges List | `gamification.challenge_list_view` | - |
| form | Challenge Form | `gamification.challenge_form_view` | - |
| kanban | Challenge Kanban | `gamification.view_challenge_kanban` | - |
| search | Challenge Search | `gamification.challenge_search_view` | - |



#### Botones (gamification.challenge_form_view)
- **Start Challenge** (object)
- **Refresh Challenge** (object)
- **Send Report** (object) - Grupos: `base.group_no_one`
- **action_view_users** (object)
- **%(goals_from_challenge_act)d** (action)


#### Filtros de búsqueda (gamification.challenge_search_view)

**Filtros:**
- **Running Challenges** (`[('state', '=', 'inprogress')]`)
- **HR Challenges** (`[('challenge_category', '=', 'hr')]`)


**Agrupar por:**
- State
- Period


### gamification.goal

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | Goal List | `gamification.goal_list_view` | - |
| form | Goal Form | `gamification.goal_form_view` | - |
| search | Goal Search | `gamification.goal_search_view` | - |
| kanban | Goal Kanban View | `gamification.goal_kanban_view` | - |



#### Botones (gamification.goal_form_view)
- **Start goal** (object)
- **Goal Reached** (object)
- **Goal Failed** (object)
- **Reset Completion** (object) - Grupos: `base.group_no_one`
- **refresh** (object)


#### Filtros de búsqueda (gamification.goal_search_view)

**Filtros:**
- **My Goals** (`[('user_id', '=', uid)]`)
- **Draft** (`[('state', '=', 'draft')]`)
- **Running** (`[                         '|',                             ('state', '=', 'inprogress'),                             '&',                                 ('state', 'in', ('done', 'failed')),                                 ('end_date', '>=', context_today().strftime('%Y-%m-%d'))                     ]`)
- **Done** (`[                         ('state', 'in', ('reached', 'failed')),                         '|',                             ('end_date', '=', False),                             ('end_date', '<', context_today().strftime('%Y-%m-%d'))                     ]`)


**Agrupar por:**
- User
- Goal Definition
- State
- End Date


### gamification.challenge.line

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | Challenge line list | `gamification.challenge_line_list_view` | - |



### gamification.badge.user

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| kanban | Badge User Kanban View | `gamification.badge_user_kanban_view` | - |



### gamification.karma.rank

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| search | gamification.karma.ranks.view.search | `gamification.gamification_karma_ranks_view_search` | - |
| list | gamification.karma.ranks.view.list | `gamification.gamification_karma_ranks_view_tree` | - |
| form | gamification.karma.rank.view.form | `gamification.gamification_karma_rank_view_form` | - |



#### Botones (gamification.gamification_karma_rank_view_form)
- **%(action_current_rank_users)d** (action)


### gamification.goal.wizard

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | Update the current value of the Goal | `gamification.view_goal_wizard_update_current` | - |



#### Botones (gamification.view_goal_wizard_update_current)
- **Update** (object)


### gamification.badge.user.wizard

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | Grant Badge User Form | `gamification.view_badge_wizard_grant` | - |



#### Botones (gamification.view_badge_wizard_grant)
- **Grant Badge** (object)

