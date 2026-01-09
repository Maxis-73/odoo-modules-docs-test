# Módulo: Forum

## Información General
- **Nombre técnico:** website_forum
- **Versión:** 1.2
- **Categoría:** Website/Website
- **Dependencias:** auth_signup, website_mail, website_profile


## Propósito
Manage a forum with FAQ and Q&A



## Descripción

Ask questions, get answers, no distractions
        



## Modelos

### website


- Hereda de:

  - website




- Campos:

  - **forum_count** (Integer)





### gamification.challenge


- Hereda de:

  - gamification.challenge




- Campos:

  - **challenge_category** (Selection)





### forum.post


- Hereda de:


  - mail.thread

  - website.seo.metadata

  - website.searchable.mixin





- Campos:

  - **name** (Char) → Title


  - **forum_id** (Many2one) → forum.forum


  - **content** (Html) → Content


  - **plain_content** (Text) → Plain Content


  - **tag_ids** (Many2many) → forum.tag


  - **state** (Selection)


  - **views** (Integer) → Views


  - **active** (Boolean) → Active


  - **website_message_ids** (One2many)


  - **website_url** (Char) → Website URL


  - **website_id** (Many2one)


  - **create_date** (Datetime) → Asked on


  - **create_uid** (Many2one) → res.users


  - **write_date** (Datetime) → Updated on


  - **last_activity_date** (Datetime) → Last activity on


  - **write_uid** (Many2one) → res.users


  - **relevancy** (Float) → Relevance


  - **vote_ids** (One2many) → forum.post.vote


  - **user_vote** (Integer) → My Vote


  - **vote_count** (Integer) → Total Votes


  - **favourite_ids** (Many2many) → res.users


  - **user_favourite** (Boolean) → Is Favourite


  - **favourite_count** (Integer) → Favorite


  - **is_correct** (Boolean) → Correct


  - **parent_id** (Many2one) → forum.post


  - **self_reply** (Boolean) → Reply to own question


  - **child_ids** (One2many) → forum.post


  - **child_count** (Integer) → Answers


  - **uid_has_answered** (Boolean) → Has Answered


  - **has_validated_answer** (Boolean) → Is answered


  - **flag_user_id** (Many2one) → res.users


  - **moderator_id** (Many2one) → res.users


  - **closed_reason_id** (Many2one) → forum.post.reason


  - **closed_uid** (Many2one) → res.users


  - **closed_date** (Datetime) → Closed on


  - **karma_accept** (Integer) → Convert comment to answer


  - **karma_edit** (Integer) → Karma to edit


  - **karma_close** (Integer) → Karma to close


  - **karma_unlink** (Integer) → Karma to unlink


  - **karma_comment** (Integer) → Karma to comment


  - **karma_comment_convert** (Integer) → Karma to convert comment to answer


  - **karma_flag** (Integer) → Flag a post as offensive


  - **can_ask** (Boolean) → Can Ask


  - **can_answer** (Boolean) → Can Answer


  - **can_accept** (Boolean) → Can Accept


  - **can_edit** (Boolean) → Can Edit


  - **can_close** (Boolean) → Can Close


  - **can_unlink** (Boolean) → Can Unlink


  - **can_upvote** (Boolean) → Can Upvote


  - **can_downvote** (Boolean) → Can Downvote


  - **can_comment** (Boolean) → Can Comment


  - **can_comment_convert** (Boolean) → Can Convert to Comment


  - **can_view** (Boolean) → Can View


  - **can_display_biography** (Boolean) → Is the author's biography visible from his post


  - **can_post** (Boolean) → Can Automatically be Validated


  - **can_flag** (Boolean) → Can Flag


  - **can_moderate** (Boolean) → Can Moderate


  - **can_use_full_editor** (Boolean) → Can Use Full Editor





### forum.post.reason


- Hereda de: Base



- Campos:

  - **name** (Char)


  - **reason_type** (Selection)





### forum.forum


- Hereda de:


  - mail.thread

  - image.mixin

  - website.seo.metadata

  - website.multi.mixin

  - website.searchable.mixin





- Campos:

  - **name** (Char) → Forum Name


  - **sequence** (Integer) → Sequence


  - **mode** (Selection)


  - **privacy** (Selection)


  - **authorized_group_id** (Many2one) → res.groups


  - **active** (Boolean)


  - **faq** (Html) → Guidelines


  - **description** (Text) → Description


  - **teaser** (Text) → Teaser


  - **welcome_message** (Html) → Welcome Message


  - **default_order** (Selection)


  - **relevancy_post_vote** (Float) → First Relevance Parameter


  - **relevancy_time_decay** (Float) → Second Relevance Parameter


  - **allow_share** (Boolean) → Sharing Options


  - **post_ids** (One2many) → forum.post


  - **last_post_id** (Many2one) → forum.post


  - **total_posts** (Integer) → # Posts


  - **total_views** (Integer) → # Views


  - **total_answers** (Integer) → # Answers


  - **total_favorites** (Integer) → # Favorites


  - **count_posts_waiting_validation** (Integer)


  - **count_flagged_posts** (Integer)


  - **karma_gen_question_new** (Integer)


  - **karma_gen_question_upvote** (Integer)


  - **karma_gen_question_downvote** (Integer)


  - **karma_gen_answer_upvote** (Integer)


  - **karma_gen_answer_downvote** (Integer)


  - **karma_gen_answer_accept** (Integer)


  - **karma_gen_answer_accepted** (Integer)


  - **karma_gen_answer_flagged** (Integer)


  - **karma_ask** (Integer)


  - **karma_answer** (Integer)


  - **karma_edit_own** (Integer)


  - **karma_edit_all** (Integer)


  - **karma_edit_retag** (Integer)


  - **karma_close_own** (Integer)


  - **karma_close_all** (Integer)


  - **karma_unlink_own** (Integer)


  - **karma_unlink_all** (Integer)


  - **karma_tag_create** (Integer)


  - **karma_upvote** (Integer)


  - **karma_downvote** (Integer)


  - **karma_answer_accept_own** (Integer)


  - **karma_answer_accept_all** (Integer)


  - **karma_comment_own** (Integer)


  - **karma_comment_all** (Integer)


  - **karma_comment_convert_own** (Integer)


  - **karma_comment_convert_all** (Integer)


  - **karma_comment_unlink_own** (Integer)


  - **karma_comment_unlink_all** (Integer)


  - **karma_flag** (Integer)


  - **karma_dofollow** (Integer)


  - **karma_editor** (Integer)


  - **karma_user_bio** (Integer)


  - **karma_post** (Integer)


  - **karma_moderate** (Integer)


  - **has_pending_post** (Boolean)


  - **can_moderate** (Boolean)


  - **tag_ids** (One2many) → forum.tag


  - **tag_most_used_ids** (One2many) → forum.tag


  - **tag_unused_ids** (One2many) → forum.tag





### forum.post.vote


- Hereda de: Base



- Campos:

  - **post_id** (Many2one) → forum.post


  - **user_id** (Many2one) → res.users


  - **vote** (Selection)


  - **create_date** (Datetime) → Create Date


  - **forum_id** (Many2one) → forum.forum


  - **recipient_id** (Many2one) → res.users





### res.users


- Hereda de:

  - res.users




- Campos:

  - **create_date** (Datetime) → Create Date





### ir.attachment


- Hereda de:

  - ir.attachment




- No agrega campos



### gamification.karma.tracking


- Hereda de:

  - gamification.karma.tracking




- No agrega campos



### forum.tag


- Hereda de:


  - mail.thread

  - website.searchable.mixin

  - website.seo.metadata





- Campos:

  - **name** (Char) → Name


  - **color** (Integer) → Color


  - **forum_id** (Many2one) → forum.forum


  - **post_ids** (Many2many) → forum.post


  - **posts_count** (Integer) → Number of Posts


  - **website_url** (Char) → Link to questions with the tag








## Vistas


### forum.tag

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | forum.tag.view.list | `website_forum.forum_tag_view_list` | - |
| form | forum.tag.view.form | `website_forum.forum_tag_view_form` | - |



### forum.post

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | forum.post.view.form | `website_forum.forum_post_view_form` | - |
| search | forum.post.view.search | `website_forum.forum_post_view_search` | - |
| graph | forum.post.view.graph | `website_forum.forum_post_view_graph` | - |
| list | forum.post.view.list | `website_forum.forum_post_view_tree` | - |
| kanban | Forum Post Pages Kanban | `website_forum.forum_post_view_kanban` | - |



#### Botones (website_forum.forum_post_view_form)
- **go_to_website** (object)


#### Filtros de búsqueda (website_forum.forum_post_view_search)

**Filtros:**
- **Posts** (`[('parent_id', '=', False)]`)
- **Answers** (`[('parent_id', '!=', False)]`)
- **Accepted Answer** (`[('is_correct' , '!=', False), ('parent_id', '!=', False)]`)
- **Answered Posts** (`[('child_count', '!=', 0), ('parent_id', '=', False)]`)
- **filter_create_date**
- **filter_write_date**
- **Archived** (`[('active','=',False)]`)


**Agrupar por:**
- Forum
- Author
- Post


### forum.post.reason

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | forum.post.reason.list | `website_forum.forum_post_reason_view_list` | - |



### forum.forum

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | forum.forum.view.list | `website_forum.forum_forum_view_tree` | - |
| form | forum.forum.view.form | `website_forum.forum_forum_view_form` | - |
| form | forum.forum.view.form.add | `website_forum.forum_forum_view_form_add` | - |
| search | forum.forum.view.search | `website_forum.forum_forum_view_search` | - |



#### Botones (website_forum.forum_forum_view_form)
- **%(forum_post_action_forum_main)d** (action)
- **%(forum_post_action_favorites)d** (action)
- **go_to_website** (object)


#### Filtros de búsqueda (website_forum.forum_forum_view_search)

**Filtros:**
- **Archived** (`[('active','=',False)]`)

