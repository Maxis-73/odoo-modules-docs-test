# Módulo: Mail Group

## Información General
- **Nombre técnico:** mail_group
- **Versión:** 1.1
- **Categoría:** N/A
- **Dependencias:** mail, portal


## Propósito
Manage your mailing lists



## Descripción

Manage your mailing lists from Odoo.
    



## Modelos

### mail.group


- Hereda de:


  - mail.alias.mixin





#### Campos
- **active** (Boolean) → Active
- **name** (Char) → Name
- **description** (Text) → Description
- **image_128** (Image) → Image
- **mail_group_message_ids** (One2many) → mail.group.message
- **mail_group_message_last_month_count** (Integer) → Messages Per Month
- **mail_group_message_count** (Integer) → Messages Count
- **mail_group_message_moderation_count** (Integer) → Pending Messages Count
- **is_member** (Boolean) → Is Member
- **member_ids** (One2many) → mail.group.member
- **member_partner_ids** (Many2many) → res.partner
- **member_count** (Integer) → Members Count
- **is_moderator** (Boolean)
- **moderation** (Boolean)
- **moderation_rule_count** (Integer)
- **moderation_rule_ids** (One2many) → mail.group.moderation
- **moderator_ids** (Many2many) → res.users
- **moderation_notify** (Boolean)
- **moderation_notify_msg** (Html)
- **moderation_guidelines** (Boolean)
- **moderation_guidelines_msg** (Html)
- **access_mode** (Selection)
- **access_group_id** (Many2one) → res.groups
- **can_manage_group** (Boolean) → Can Manage





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | mail.group.view.list | `mail_group.mail_group_view_list` | - |
| kanban | mail.group.view.kanban | `mail_group.mail_group_view_kanban` | - |
| form | mail.group.view.form | `mail_group.mail_group_view_form` | - |
| search | mail.group.view.search | `mail_group.mail_group_view_search` | - |



**Botones (mail_group.mail_group_view_form):**
- **Join** (object)
- **Leave** (object)
- **Send Guidelines** (object)
- **%(mail_group.mail_group_member_action)d** (action)
- **%(mail_group.mail_group_message_action)d** (action)
- **%(mail_group.mail_group_message_action)d** (action)
- **%(mail_group.mail_group_moderation_action)d** (action)
- **Choose or configure a custom domain** (action)


**Filtros de búsqueda (mail_group.mail_group_view_search):**

- **Archived** (`[('active', '=', False)]`)
- **Moderated** (`[('moderation', '=', True)]`)


*Agrupar por:*
- Moderation



### mail.group.message


- Hereda de: Base



#### Campos
- **attachment_ids** (Many2many)
- **author_id** (Many2one)
- **email_from** (Char)
- **email_from_normalized** (Char) → Normalized From
- **body** (Html)
- **subject** (Char)
- **mail_group_id** (Many2one) → mail.group
- **mail_message_id** (Many2one) → mail.message
- **group_message_parent_id** (Many2one) → mail.group.message
- **group_message_child_ids** (One2many) → mail.group.message
- **author_moderation** (Selection)
- **is_group_moderated** (Boolean) → Is Group Moderated
- **moderation_status** (Selection)
- **moderator_id** (Many2one) → res.users
- **create_date** (Datetime)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | mail.group.message.view.list | `mail_group.mail_group_message_view_list` | - |
| form | mail.group.message.view.form | `mail_group.mail_group_message_view_form` | - |
| search | mail.group.message.view.search | `mail_group.mail_group_message_view_search` | - |



**Botones (mail_group.mail_group_message_view_form):**
- **Accept** (object)
- **Reject** (action)
- **Whitelist** (object)
- **Ban** (action)
- **Send** (object)


**Filtros de búsqueda (mail_group.mail_group_message_view_search):**


*Agrupar por:*
- group



### mail.group.member


- Hereda de: Base



#### Campos
- **email** (Char)
- **email_normalized** (Char)
- **mail_group_id** (Many2one) → mail.group
- **partner_id** (Many2one) → res.partner





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | mail.group.member.view.list | `mail_group.mail_group_member_view_tree` | - |
| search | mail.group.member.view.search | `mail_group.mail_group_member_view_search` | - |




### mail.group.moderation


- Hereda de: Base



#### Campos
- **email** (Char)
- **status** (Selection)
- **mail_group_id** (Many2one) → mail.group





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | mail.group.moderation.view.list | `mail_group.mail_group_moderation_view_tree` | - |
| search | mail.group.moderation.view.search | `mail_group.mail_group_moderation_view_search` | - |



**Filtros de búsqueda (mail_group.mail_group_moderation_view_search):**

- **Is Banned** (`[('status', '=', 'ban')]`)
- **Is Allowed** (`[('status', '=', 'allow')]`)


*Agrupar por:*
- Status








## Vistas Adicionales


### mail.group.message.reject

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | mail.group.message.reject.form | `mail_group.mail_group_message_reject_form` | - |



**Botones (mail_group.mail_group_message_reject_form):**
- **Reject Silently** (object)
- **Send & Reject** (object)
- **Ban** (object)
- **Send & Ban** (object)



