# Módulo: eLearning

## Información General
- **Nombre técnico:** website_slides
- **Versión:** 2.7
- **Categoría:** Website/eLearning
- **Dependencias:** portal_rating, website, website_mail, website_profile


## Propósito
Manage and publish an eLearning platform



## Descripción

Create Online Courses
=====================

Featuring

 * Integrated course and lesson management
 * Fullscreen navigation
 * Support Youtube videos, Google documents, PDF, images, articles
 * Test knowledge with quizzes
 * Filter and Tag
 * Statistics




## Modelos

### website


- Hereda de:

  - website




#### Campos
- **website_slide_google_app_key** (Char) → Google Doc Key





### gamification.challenge


- Hereda de:

  - gamification.challenge




#### Campos
- **challenge_category** (Selection)





### slide.slide.resource


- Hereda de: Base



#### Campos
- **slide_id** (Many2one) → slide.slide
- **resource_type** (Selection)
- **name** (Char) → Name
- **data** (Binary) → Resource
- **file_name** (Char)
- **link** (Char) → Link
- **download_url** (Char) → Download URL
- **sequence** (Integer)





### slide.channel.tag.group


- Hereda de:

  - website.published.mixin




#### Campos
- **name** (Char) → Group Name
- **sequence** (Integer) → Sequence
- **tag_ids** (One2many) → slide.channel.tag





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| search | slide.channel.tag.group.view.search | `website_slides.slide_channel_tag_group_view_search` | - |
| form | slide.channel.tag.group.view.form | `website_slides.slide_channel_tag_group_view_form` | - |
| list | slide.channel.tag.group.view.list | `website_slides.slide_channel_tag_group_view_tree` | - |



**Filtros de búsqueda (website_slides.slide_channel_tag_group_view_search):**

- **Has Menu Entry** (`[('is_published', '=', True)]`)



### slide.channel.tag


- Hereda de: Base



#### Campos
- **name** (Char) → Name
- **sequence** (Integer) → Sequence
- **group_id** (Many2one) → slide.channel.tag.group
- **group_sequence** (Integer) → Group sequence
- **channel_ids** (Many2many) → slide.channel
- **color** (Integer)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| search | slide.channel.tag.view.search | `website_slides.slide_channel_tag_view_search` | - |
| form | slide.channel.tag.view.form | `website_slides.slide_channel_tag_view_form` | - |
| list | slide.channel.tag.view.list | `website_slides.slide_channel_tag_view_tree` | - |




### ir.binary


- Hereda de:

  - ir.binary




- No agrega campos




### res.groups


- Hereda de:

  - res.groups




- No agrega campos




### slide.question


- Hereda de: Base



#### Campos
- **sequence** (Integer) → Sequence
- **question** (Char) → Question Name
- **slide_id** (Many2one) → slide.slide
- **answer_ids** (One2many) → slide.answer
- **answers_validation_error** (Char) → Error on Answers
- **attempts_count** (Integer)
- **attempts_avg** (Float)
- **done_count** (Integer)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | slide.question.view.form | `website_slides.slide_question_view_form` | - |
| list | slide.question.view.list | `website_slides.slide_question_view_tree` | - |
| list | slide.question.view.list.report | `website_slides.slide_question_view_tree_report` | - |
| search | slide.question.view.search | `website_slides.slide_question_view_search` | - |




### slide.answer


- Hereda de: Base



#### Campos
- **sequence** (Integer) → Sequence
- **question_id** (Many2one) → slide.question
- **text_value** (Char) → Answer
- **is_correct** (Boolean) → Is correct answer
- **comment** (Text) → Comment





### slide.slide.partner


- Hereda de: Base



#### Campos
- **slide_id** (Many2one) → slide.slide
- **slide_category** (Selection)
- **channel_id** (Many2one) → slide.channel
- **partner_id** (Many2one) → res.partner
- **vote** (Integer) → Vote
- **completed** (Boolean) → Completed
- **quiz_attempts_count** (Integer) → Quiz attempts count





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| search | slide.slide.partner.view.search | `website_slides.slide_slide_partner_view_search` | - |
| list | slide.slide.partner.view.list | `website_slides.slide_slide_partner_view_tree` | - |
| form | slide.slide.partner.view.form | `website_slides.slide_slide_partner_view_form` | - |



**Filtros de búsqueda (website_slides.slide_slide_partner_view_search):**

- **Completed** (`[('completed', '=', True)]`)


*Agrupar por:*
- Content



### slide.tag


- Hereda de: Base



#### Campos
- **name** (Char) → Name





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | slide.tag.form | `website_slides.view_slide_tag_form` | - |
| list | slide.tag.list | `website_slides.view_slide_tag_tree` | - |




### slide.slide


- Hereda de:


  - mail.thread

  - image.mixin

  - website.seo.metadata

  - website.published.mixin

  - website.searchable.mixin





#### Campos
- **name** (Char) → Title
- **image_1920** (Image)
- **active** (Boolean)
- **sequence** (Integer) → Sequence
- **user_id** (Many2one) → res.users
- **description** (Html) → Description
- **channel_id** (Many2one) → slide.channel
- **tag_ids** (Many2many) → slide.tag
- **is_preview** (Boolean) → Allow Preview
- **is_new_slide** (Boolean) → Is New Slide
- **completion_time** (Float) → Duration
- **is_category** (Boolean) → Is a category
- **category_id** (Many2one) → slide.slide
- **slide_ids** (One2many) → slide.slide
- **partner_ids** (Many2many) → res.partner
- **slide_partner_ids** (One2many) → slide.slide.partner
- **user_membership_id** (Many2one) → slide.slide.partner
- **user_vote** (Integer) → User vote
- **user_has_completed** (Boolean) → Is Member
- **user_has_completed_category** (Boolean) → Is Category Completed
- **question_ids** (One2many) → slide.question
- **questions_count** (Integer)
- **quiz_first_attempt_reward** (Integer) → Reward: first attempt
- **quiz_second_attempt_reward** (Integer) → Reward: second attempt
- **quiz_third_attempt_reward** (Integer) → Reward: third attempt
- **quiz_fourth_attempt_reward** (Integer) → Reward: every attempt after the third try
- **can_self_mark_completed** (Boolean) → Can Mark Completed
- **can_self_mark_uncompleted** (Boolean) → Can Mark Uncompleted
- **slide_category** (Selection)
- **source_type** (Selection)
- **url** (Char) → External URL
- **binary_content** (Binary) → File
- **slide_resource_ids** (One2many) → slide.slide.resource
- **slide_resource_downloadable** (Boolean) → Allow Download
- **google_drive_id** (Char) → Google Drive ID of the external URL
- **html_content** (Html) → HTML Content
- **image_binary_content** (Binary) → Image Content
- **image_google_url** (Char) → Image Link
- **slide_icon_class** (Char) → Slide Icon fa-class
- **slide_type** (Selection)
- **document_google_url** (Char) → Document Link
- **document_binary_content** (Binary) → PDF Content
- **video_url** (Char) → Video Link
- **video_source_type** (Selection)
- **youtube_id** (Char) → Video YouTube ID
- **vimeo_id** (Char) → Video Vimeo ID
- **website_id** (Many2one)
- **date_published** (Datetime) → Publish Date
- **likes** (Integer) → Likes
- **dislikes** (Integer) → Dislikes
- **embed_code** (Html) → Embed Code
- **embed_code_external** (Html) → External Embed Code
- **website_share_url** (Char) → Share URL
- **embed_ids** (One2many) → slide.embed
- **embed_count** (Integer) → # of Embeds
- **slide_views** (Integer) → # of Website Views
- **public_views** (Integer) → # of Public Views
- **total_views** (Integer) → # Total Views
- **comments_count** (Integer) → Number of comments
- **channel_type** (Selection)
- **channel_allow_comment** (Boolean)
- **nbr_document** (Integer) → Number of Documents
- **nbr_video** (Integer) → Number of Videos
- **nbr_infographic** (Integer) → Number of Images
- **nbr_article** (Integer) → Number of Articles
- **nbr_quiz** (Integer) → Number of Quizs
- **total_slides** (Integer)
- **is_published** (Boolean)
- **website_published** (Boolean)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | slide.slide.form | `website_slides.view_slide_slide_form` | - |
| kanban | slide.slide.view.kanban | `website_slides.slide_slide_view_kanban` | - |
| list | slide.slide.list | `website_slides.view_slide_slide_tree` | - |
| list | slide.slide.view.list.report | `website_slides.slide_slide_view_tree_report` | - |
| search | slide.slide.filter | `website_slides.view_slide_slide_search` | - |
| graph | slide.slide.view.graph | `website_slides.slide_slide_view_graph` | - |
| pivot | slide.slide.view.pivot | `website_slides.slide_slide_view_pivot` | - |



**Botones (website_slides.view_slide_slide_form):**
- **%(slide_slide_partner_action_from_slide)d** (action)
- **action_view_embeds** (object)


**Filtros de búsqueda (website_slides.view_slide_slide_search):**

- **My Content** (`[('user_id', '=', uid)]`)
- **Published** (`[('is_published', '=', True)]`)
- **Waiting for validation** (`[('is_published', '=', False)]`)
- **Archived** (`[('active','=',False)]`)


*Agrupar por:*
- Course
- Category
- Type



### slide.embed


- Hereda de: Base



#### Campos
- **slide_id** (Many2one) → slide.slide
- **url** (Char) → Third Party Website URL
- **website_name** (Char) → Website
- **count_views** (Integer) → # Views





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | slide.embed.view.list | `website_slides.slide_embed_view_tree` | - |
| search | slide.embed.view.search | `website_slides.slide_embed_view_search` | - |




### res.users


- Hereda de:

  - res.users




- No agrega campos




### res.config.settings


- Hereda de:

  - res.config.settings




#### Campos
- **website_slide_google_app_key** (Char)
- **module_website_sale_slides** (Boolean)
- **module_website_slides_forum** (Boolean)
- **module_website_slides_survey** (Boolean)
- **module_mass_mailing_slides** (Boolean)





### gamification.karma.tracking


- Hereda de:

  - gamification.karma.tracking




- No agrega campos




### res.partner


- Hereda de:

  - res.partner




#### Campos
- **slide_channel_ids** (Many2many) → slide.channel
- **slide_channel_completed_ids** (One2many) → slide.channel
- **slide_channel_count** (Integer) → Course Count
- **slide_channel_company_count** (Integer) → Company Course Count





### slide.channel.partner


- Hereda de: Base



#### Campos
- **active** (Boolean)
- **channel_id** (Many2one) → slide.channel
- **member_status** (Selection)
- **completion** (Integer) → % Completed Contents
- **completed_slides_count** (Integer) → # Completed Contents
- **partner_id** (Many2one) → res.partner
- **partner_email** (Char)
- **channel_user_id** (Many2one) → res.users
- **channel_type** (Selection)
- **channel_visibility** (Selection)
- **channel_enroll** (Selection)
- **channel_website_id** (Many2one) → website
- **next_slide_id** (Many2one) → slide.slide
- **invitation_link** (Char) → Invitation Link
- **last_invitation_date** (Datetime) → Last Invitation Date





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| search | slide.channel.partner.search | `website_slides.slide_channel_partner_view_search` | - |
| list | slide.channel.partner.list | `website_slides.slide_channel_partner_view_tree` | - |
| kanban | slide.channel.partner.view.kanban | `website_slides.slide_channel_partner_view_kanban` | - |
| graph | slide.channel.partner.view.graph | `website_slides.slide_channel_partner_view_graph` | - |
| pivot | slide.channel.partner.view.pivot | `website_slides.slide_channel_partner_view_pivot` | - |



**Filtros de búsqueda (website_slides.slide_channel_partner_view_search):**

- **Archived** (`[('active', '=', False)]`)
- **Invite Sent** (`[('member_status', '=', 'invited')]`)
- **Joined** (`[('member_status', '=', 'joined')]`)
- **Ongoing** (`[('member_status', '=', 'ongoing')]`)
- **Completed** (`[('member_status', '=', 'completed')]`)


*Agrupar por:*
- Course
- Status



### slide.channel


- Hereda de:


  - rating.mixin

  - mail.activity.mixin

  - image.mixin

  - website.cover_properties.mixin

  - website.seo.metadata

  - website.published.multi.mixin

  - website.searchable.mixin





#### Campos
- **name** (Char) → Name
- **active** (Boolean)
- **description** (Html) → Description
- **description_short** (Html) → Short Description
- **description_html** (Html) → Detailed Description
- **channel_type** (Selection)
- **sequence** (Integer)
- **user_id** (Many2one) → res.users
- **color** (Integer) → Color Index
- **tag_ids** (Many2many) → slide.channel.tag
- **slide_ids** (One2many) → slide.slide
- **slide_content_ids** (One2many) → slide.slide
- **slide_category_ids** (One2many) → slide.slide
- **slide_last_update** (Date) → Last Update
- **slide_partner_ids** (One2many) → slide.slide.partner
- **promote_strategy** (Selection)
- **promoted_slide_id** (Many2one) → slide.slide
- **access_token** (Char) → Security Token
- **nbr_document** (Integer) → Documents
- **nbr_video** (Integer) → Videos
- **nbr_infographic** (Integer) → Infographics
- **nbr_article** (Integer) → Articles
- **nbr_quiz** (Integer) → Number of Quizs
- **total_slides** (Integer) → Number of Contents
- **total_views** (Integer) → Visits
- **total_votes** (Integer) → Votes
- **total_time** (Float) → Duration
- **rating_avg_stars** (Float) → Rating Average (Stars)
- **allow_comment** (Boolean) → Allow rating on Course
- **publish_template_id** (Many2one) → mail.template
- **share_channel_template_id** (Many2one) → mail.template
- **share_slide_template_id** (Many2one) → mail.template
- **completed_template_id** (Many2one) → mail.template
- **enroll** (Selection)
- **enroll_msg** (Html) → Enroll Message
- **enroll_group_ids** (Many2many) → res.groups
- **visibility** (Selection)
- **upload_group_ids** (Many2many) → res.groups
- **website_default_background_image_url** (Char) → Background image URL
- **channel_partner_ids** (One2many) → slide.channel.partner
- **channel_partner_all_ids** (One2many) → slide.channel.partner
- **members_count** (Integer) → # Enrolled Attendees
- **members_all_count** (Integer) → # Enrolled or Invited Attendees
- **members_engaged_count** (Integer) → # Active Attendees
- **members_completed_count** (Integer) → # Completed Attendees
- **members_invited_count** (Integer) → # Invited Attendees
- **partner_ids** (Many2many) → res.partner
- **completed** (Boolean) → Done
- **completion** (Integer) → Completion
- **can_upload** (Boolean) → Can Upload
- **has_requested_access** (Boolean)
- **is_member** (Boolean)
- **is_member_invited** (Boolean)
- **partner_has_new_content** (Boolean)
- **karma_gen_channel_rank** (Integer)
- **karma_gen_channel_finish** (Integer)
- **karma_review** (Integer) → Add Review
- **karma_slide_comment** (Integer) → Add Comment
- **karma_slide_vote** (Integer) → Vote
- **can_review** (Boolean) → Can Review
- **can_comment** (Boolean) → Can Comment
- **can_vote** (Boolean) → Can Vote
- **prerequisite_channel_ids** (Many2many) → slide.channel
- **prerequisite_of_channel_ids** (Many2many) → slide.channel
- **prerequisite_user_has_completed** (Boolean) → Has Completed Prerequisite





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | slide.channel.view.form.add | `website_slides.slide_channel_view_form_add` | - |
| form | slide.channel.view.form | `website_slides.view_slide_channel_form` | - |
| list | slide.channel.view.list | `website_slides.slide_channel_view_tree` | - |
| list | slide.channel.view.list.report | `website_slides.slide_channel_view_tree_report` | - |
| search | slide.channel.view.search | `website_slides.slide_channel_view_search` | - |
| graph | slide.channel.view.graph | `website_slides.slide_channel_view_graph` | - |
| pivot | slide.channel.view.pivot | `website_slides.slide_channel_view_pivot` | - |
| kanban | slide.channel.view.kanban | `website_slides.slide_channel_view_kanban` | - |



**Botones (website_slides.view_slide_channel_form):**
- **Add Attendees** (object)
- **Invite** (object)
- **action_view_slides** (object) - Grupos: `website_slides.group_website_slides_officer`
- **action_redirect_to_completed_members** (object) - Grupos: `website_slides.group_website_slides_officer`
- **action_redirect_to_members** (object) - Grupos: `website_slides.group_website_slides_officer`
- **action_view_ratings** (object) - Grupos: `website_slides.group_website_slides_officer`


**Filtros de búsqueda (website_slides.slide_channel_view_search):**

- **Published** (`[('is_published', '=', True)]`)
- **Archived** (`[('active','=',False)]`)








## Vistas Adicionales


### rating.rating

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| graph | rating.rating.view.graph.slides | `website_slides.rating_rating_view_graph_slide_channel` | - |
| pivot | rating.rating.view.pivot.slides | `website_slides.rating_rating_view_pivot_slide_channel` | - |
| list | rating.rating.view.list.slides | `website_slides.rating_rating_view_tree_slide_channel` | - |
| form | rating.rating.view.form.slides | `website_slides.rating_rating_view_form_slides` | - |



### slide.channel.invite

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | slide.channel.invite.view.form | `website_slides.slide_channel_invite_view_form` | - |



**Botones (website_slides.slide_channel_invite_view_form):**
- **Send** (object)



