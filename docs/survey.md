# Módulo: Surveys

## Información General
- **Nombre técnico:** survey
- **Versión:** 3.7
- **Categoría:** Marketing/Surveys
- **Dependencias:** auth_signup, http_routing, mail, web_tour, gamification


## Propósito
Send your surveys or share them live.



## Descripción

Create beautiful surveys and visualize answers

It depends on the answers or reviews of some questions by different users. A
survey may have multiple pages. Each page may contain multiple questions and
each question may have multiple answers. Different users may give different
answers of question and according to that survey is done. Partners are also
sent mails with personal token for the invitation of the survey.
    



## Modelos

### survey.user_input


- Hereda de:


  - mail.thread

  - mail.activity.mixin





- Campos:

  - **survey_id** (Many2one) → survey.survey


  - **scoring_type** (Selection)


  - **start_datetime** (Datetime) → Start date and time


  - **end_datetime** (Datetime) → End date and time


  - **deadline** (Datetime) → Deadline


  - **state** (Selection)


  - **test_entry** (Boolean)


  - **last_displayed_page_id** (Many2one) → survey.question


  - **is_attempts_limited** (Boolean) → Limited number of attempts


  - **attempts_limit** (Integer) → Number of attempts


  - **attempts_count** (Integer) → Attempts Count


  - **attempts_number** (Integer) → Attempt n°


  - **survey_time_limit_reached** (Boolean) → Survey Time Limit Reached


  - **access_token** (Char) → Identification token


  - **invite_token** (Char) → Invite token


  - **partner_id** (Many2one) → res.partner


  - **email** (Char) → Email


  - **nickname** (Char) → Nickname


  - **user_input_line_ids** (One2many) → survey.user_input.line


  - **predefined_question_ids** (Many2many) → survey.question


  - **scoring_percentage** (Float) → Score (%)


  - **scoring_total** (Float) → Total Score


  - **scoring_success** (Boolean) → Quizz Passed


  - **survey_first_submitted** (Boolean)


  - **is_session_answer** (Boolean) → Is in a Session


  - **question_time_limit_reached** (Boolean) → Question Time Limit Reached





### survey.user_input.line


- Hereda de: Base



- Campos:

  - **user_input_id** (Many2one) → survey.user_input


  - **survey_id** (Many2one)


  - **question_id** (Many2one) → survey.question


  - **page_id** (Many2one)


  - **question_sequence** (Integer) → Sequence


  - **skipped** (Boolean) → Skipped


  - **answer_type** (Selection)


  - **value_char_box** (Char) → Text answer


  - **value_numerical_box** (Float) → Numerical answer


  - **value_scale** (Integer) → Scale value


  - **value_date** (Date) → Date answer


  - **value_datetime** (Datetime) → Datetime answer


  - **value_text_box** (Text) → Free Text answer


  - **suggested_answer_id** (Many2one) → survey.question.answer


  - **matrix_row_id** (Many2one) → survey.question.answer


  - **answer_score** (Float) → Score


  - **answer_is_correct** (Boolean) → Correct





### survey.survey


- Hereda de:


  - mail.thread

  - mail.activity.mixin





- Campos:

  - **survey_type** (Selection)


  - **allowed_survey_types** (Json)


  - **title** (Char) → Survey Title


  - **color** (Integer) → Color Index


  - **description** (Html) → Description


  - **description_done** (Html) → End Message


  - **background_image** (Image) → Background Image


  - **background_image_url** (Char) → Background Url


  - **active** (Boolean) → Active


  - **user_id** (Many2one) → res.users


  - **restrict_user_ids** (Many2many) → res.users


  - **question_and_page_ids** (One2many) → survey.question


  - **page_ids** (One2many) → survey.question


  - **question_ids** (One2many) → survey.question


  - **question_count** (Integer) → # Questions


  - **questions_layout** (Selection)


  - **questions_selection** (Selection)


  - **progression_mode** (Selection)


  - **user_input_ids** (One2many) → survey.user_input


  - **access_mode** (Selection)


  - **access_token** (Char) → Access Token


  - **users_login_required** (Boolean) → Require Login


  - **users_can_go_back** (Boolean) → Users can go back


  - **users_can_signup** (Boolean) → Users can signup


  - **answer_count** (Integer) → Registered


  - **answer_done_count** (Integer) → Attempts


  - **answer_score_avg** (Float) → Avg Score (%)


  - **answer_duration_avg** (Float) → Average Duration


  - **success_count** (Integer) → Success


  - **success_ratio** (Integer) → Success Ratio (%)


  - **scoring_type** (Selection)


  - **scoring_success_min** (Float) → Required Score (%)


  - **scoring_max_obtainable** (Float) → Maximum obtainable score


  - **is_attempts_limited** (Boolean) → Limited number of attempts


  - **attempts_limit** (Integer) → Number of attempts


  - **is_time_limited** (Boolean) → The survey is limited in time


  - **time_limit** (Float) → Time limit (minutes)


  - **certification** (Boolean) → Is a Certification


  - **certification_mail_template_id** (Many2one) → mail.template


  - **certification_report_layout** (Selection)


  - **certification_give_badge** (Boolean) → Give Badge


  - **certification_badge_id** (Many2one) → gamification.badge


  - **certification_badge_id_dummy** (Many2one)


  - **session_available** (Boolean) → Live session available


  - **session_state** (Selection)


  - **session_code** (Char) → Session Code


  - **session_link** (Char) → Session Link


  - **session_question_id** (Many2one) → survey.question


  - **session_start_time** (Datetime) → Current Session Start Time


  - **session_question_start_time** (Datetime) → Current Question Start Time


  - **session_answer_count** (Integer) → Answers Count


  - **session_question_answer_count** (Integer) → Question Answers Count


  - **session_show_leaderboard** (Boolean) → Show Session Leaderboard


  - **session_speed_rating** (Boolean) → Reward quick answers


  - **session_speed_rating_time_limit** (Integer) → Time limit (seconds)


  - **has_conditional_questions** (Boolean) → Contains conditional questions





### gamification.badge


- Hereda de:

  - gamification.badge




- Campos:

  - **survey_ids** (One2many) → survey.survey


  - **survey_id** (Many2one) → survey.survey





### survey.question


- Hereda de: Base



- Campos:

  - **title** (Char) → Title


  - **description** (Html) → Description


  - **question_placeholder** (Char) → Placeholder


  - **background_image** (Image) → Background Image


  - **background_image_url** (Char) → Background Url


  - **survey_id** (Many2one) → survey.survey


  - **scoring_type** (Selection)


  - **sequence** (Integer) → Sequence


  - **session_available** (Boolean)


  - **survey_session_speed_rating** (Boolean)


  - **survey_session_speed_rating_time_limit** (Integer)


  - **is_page** (Boolean) → Is a page?


  - **question_ids** (One2many) → survey.question


  - **questions_selection** (Selection)


  - **random_questions_count** (Integer) → # Questions Randomly Picked


  - **page_id** (Many2one) → survey.question


  - **question_type** (Selection)


  - **is_scored_question** (Boolean) → Scored


  - **has_image_only_suggested_answer** (Boolean) → Has image only suggested answer


  - **answer_numerical_box** (Float) → Correct numerical answer


  - **answer_date** (Date) → Correct date answer


  - **answer_datetime** (Datetime) → Correct datetime answer


  - **answer_score** (Float) → Score


  - **save_as_email** (Boolean) → Save as user email


  - **save_as_nickname** (Boolean) → Save as user nickname


  - **suggested_answer_ids** (One2many) → survey.question.answer


  - **matrix_subtype** (Selection)


  - **matrix_row_ids** (One2many) → survey.question.answer


  - **scale_min** (Integer) → Scale Minimum Value


  - **scale_max** (Integer) → Scale Maximum Value


  - **scale_min_label** (Char) → Scale Minimum Label


  - **scale_mid_label** (Char) → Scale Middle Label


  - **scale_max_label** (Char) → Scale Maximum Label


  - **is_time_limited** (Boolean) → The question is limited in time


  - **is_time_customized** (Boolean) → Customized speed rewards


  - **time_limit** (Integer) → Time limit (seconds)


  - **comments_allowed** (Boolean) → Show Comments Field


  - **comments_message** (Char) → Comment Message


  - **comment_count_as_answer** (Boolean) → Comment is an answer


  - **validation_required** (Boolean) → Validate entry


  - **validation_email** (Boolean) → Input must be an email


  - **validation_length_min** (Integer) → Minimum Text Length


  - **validation_length_max** (Integer) → Maximum Text Length


  - **validation_min_float_value** (Float) → Minimum value


  - **validation_max_float_value** (Float) → Maximum value


  - **validation_min_date** (Date) → Minimum Date


  - **validation_max_date** (Date) → Maximum Date


  - **validation_min_datetime** (Datetime) → Minimum Datetime


  - **validation_max_datetime** (Datetime) → Maximum Datetime


  - **validation_error_msg** (Char) → Validation Error


  - **constr_mandatory** (Boolean) → Mandatory Answer


  - **constr_error_msg** (Char) → Error message


  - **user_input_line_ids** (One2many) → survey.user_input.line


  - **triggering_question_ids** (Many2many) → survey.question


  - **allowed_triggering_question_ids** (Many2many) → survey.question


  - **is_placed_before_trigger** (Boolean)


  - **triggering_answer_ids** (Many2many) → survey.question.answer





### survey.question.answer


- Hereda de: Base



- Campos:

  - **question_id** (Many2one) → survey.question


  - **matrix_question_id** (Many2one) → survey.question


  - **question_type** (Selection)


  - **sequence** (Integer) → Label Sequence order


  - **scoring_type** (Selection)


  - **value** (Char) → Suggested value


  - **value_image** (Image) → Image


  - **value_image_filename** (Char) → Image Filename


  - **value_label** (Char) → Value Label


  - **is_correct** (Boolean) → Correct


  - **answer_score** (Float) → Score





### gamification.challenge


- Hereda de:

  - gamification.challenge




- Campos:

  - **challenge_category** (Selection)





### survey.survey


- Hereda de:

  - survey.survey




- No agrega campos



### ['ir.http']


- Hereda de:


  - ir.http





- No agrega campos



### res.partner


- Hereda de:

  - res.partner




- Campos:

  - **certifications_count** (Integer) → Certifications Count


  - **certifications_company_count** (Integer) → Company Certifications Count








## Vistas


### survey.user_input

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| search | survey.user_input.view.search | `survey.survey_user_input_view_search` | - |
| form | survey.user_input.view.form | `survey.survey_user_input_view_form` | - |
| list | survey.user_input.view.list | `survey.survey_user_input_view_tree` | - |
| kanban | survey.user_input.view.kanban | `survey.survey_user_input_viuew_kanban` | - |



#### Filtros de búsqueda (survey.survey_user_input_view_search)

**Filtros:**
- **New** (`[('state', '=', 'new')]`)
- **In Progress** (`[('state', '=', 'in_progress')]`)
- **Completed** (`[('state', '=', 'done')]`)
- **Quizz passed** (`[('scoring_success','=', True)]`)
- **Tests Only** (`[('test_entry','=', True)]`)
- **Exclude Tests** (`[('test_entry','=', False)]`)


**Agrupar por:**
- Survey
- Email
- Partner


#### Botones (survey.survey_user_input_view_form)
- **Resend Invitation** (object)
- **Print** (object)
- **action_redirect_to_attempts** (object)


### survey.user_input.line

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | survey.user_input.line.view.form | `survey.survey_user_input_line_view_form` | - |
| list | survey.user_input.line.view.list | `survey.survey_response_line_view_tree` | - |
| search | survey.user_input.line.view.search | `survey.survey_user_input_line_view_search` | - |



#### Filtros de búsqueda (survey.survey_user_input_line_view_search)


**Agrupar por:**
- Survey
- User Input


### survey.survey

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | survey.survey.view.form | `survey.survey_survey_view_form` | - |
| list | survey.survey.view.list | `survey.survey_survey_view_tree` | - |
| kanban | survey.survey.view.kanban | `survey.survey_survey_view_kanban` | - |
| activity | survey.survey.view.activity | `survey.survey_survey_view_activity` | - |
| search | survey.survey.search | `survey.survey_survey_view_search` | - |
| graph | survey.survey.view.graph | `survey.survey_survey_view_graph` | - |
| pivot | survey.survey.view.pivot | `survey.survey_survey_view_pivot` | - |



#### Botones (survey.survey_survey_view_form)
- **Share** (object)
- **See results** (object)
- **Create Live Session** (object)
- **Open Session Manager** (object)
- **Close Live Session** (object)
- **Test** (object)
- **Reopen** (object)
- **Close** (object)
- **action_survey_user_input** (object)
- **action_survey_user_input_certified** (object)
- **action_survey_user_input_completed** (object)
- **copy** (object)
- **Preview** (object)


#### Filtros de búsqueda (survey.survey_survey_view_search)

**Filtros:**
- **Is a Certification** (`[('certification', '=', True)]`)
- **Is not a Certification** (`[('certification', '=', False)]`)
- **Archived** (`[('active', '=', False)]`)
- **Late Activities** (`[('my_activity_date_deadline', '<', context_today().strftime('%Y-%m-%d'))]`)
- **Today Activities** (`[('my_activity_date_deadline', '=', context_today().strftime('%Y-%m-%d'))]`)
- **Upcoming Activities** (`[('my_activity_date_deadline', '>', context_today().strftime('%Y-%m-%d'))]`)


**Agrupar por:**
- Responsible
- group_by_restrict_user_ids


### gamification.badge

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | gamification.badge.form.view.simplified | `survey.gamification_badge_form_view_simplified` | - |



### survey.question

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | Form view for survey question | `survey.survey_question_form` | - |
| list | List view for survey question | `survey.survey_question_tree` | - |
| search | Search view for survey question | `survey.survey_question_search` | - |



#### Filtros de búsqueda (survey.survey_question_search)


**Agrupar por:**
- Type
- Survey


### survey.question.answer

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | survey.question.answer.view.list | `survey.survey_question_answer_view_tree` | - |
| form | survey.question.answer.view.form | `survey.survey_question_answer_view_form` | - |
| search | survey.question.answer.view.search | `survey.survey_question_answer_view_search` | - |



#### Filtros de búsqueda (survey.survey_question_answer_view_search)


**Agrupar por:**
- Question


### survey.invite

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | survey.invite.view.form | `survey.survey_invite_view_form` | - |



#### Botones (survey.survey_invite_view_form)
- **Send** (object)

