# Módulo: Sales Teams

## Información General
- **Nombre técnico:** sales_team
- **Versión:** 1.1
- **Categoría:** Sales/Sales
- **Dependencias:** base, mail


## Propósito
Sales Teams



## Descripción

Using this application you can manage Sales Teams with CRM and/or Sales
=======================================================================
 



## Modelos

### res.users


- Hereda de:

  - res.users




#### Campos
- **crm_team_ids** (Many2many) → crm.team
- **crm_team_member_ids** (One2many) → crm.team.member
- **sale_team_id** (Many2one) → crm.team





### crm.team


- Hereda de:


  - mail.thread





#### Campos
- **name** (Char) → Sales Team
- **sequence** (Integer) → Sequence
- **active** (Boolean)
- **company_id** (Many2one) → res.company
- **currency_id** (Many2one) → res.currency
- **user_id** (Many2one) → res.users
- **is_membership_multi** (Boolean) → Multiple Memberships Allowed
- **member_ids** (Many2many) → res.users
- **member_company_ids** (Many2many) → res.company
- **member_warning** (Text) → Membership Issue Warning
- **crm_team_member_ids** (One2many) → crm.team.member
- **crm_team_member_all_ids** (One2many) → crm.team.member
- **color** (Integer)
- **favorite_user_ids** (Many2many) → res.users
- **is_favorite** (Boolean)
- **dashboard_button_name** (Char)
- **dashboard_graph_data** (Text)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| search | crm.team.view.search | `sales_team.crm_team_view_search` | - |
| form | crm.team.form | `sales_team.crm_team_view_form` | - |
| list | crm.team.list | `sales_team.crm_team_view_tree` | - |
| kanban | crm.team.view.kanban | `sales_team.crm_team_view_kanban` | - |
| kanban | crm.team.view.kanban.dashboard | `sales_team.crm_team_view_kanban_dashboard` | - |



**Filtros de búsqueda (sales_team.crm_team_view_search):**

- **Archived** (`[('active','=',False)]`)


*Agrupar por:*
- Company
- Team Leader



### crm.tag


- Hereda de: Base



#### Campos
- **name** (Char) → Tag Name
- **color** (Integer) → Color





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | sales.team.crm.tag.view.form | `sales_team.sales_team_crm_tag_view_form` | - |
| list | sales.team.crm.tag.view.list | `sales_team.sales_team_crm_tag_view_tree` | - |




### crm.team.member


- Hereda de:


  - mail.thread





#### Campos
- **crm_team_id** (Many2one) → crm.team
- **user_id** (Many2one) → res.users
- **user_in_teams_ids** (Many2many) → res.users
- **user_company_ids** (Many2many) → res.company
- **active** (Boolean)
- **is_membership_multi** (Boolean) → Multiple Memberships Allowed
- **member_warning** (Text)
- **image_1920** (Image) → Image
- **image_128** (Image) → Image (128)
- **name** (Char)
- **email** (Char)
- **phone** (Char)
- **mobile** (Char)
- **company_id** (Many2one) → res.company





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| search | crm.team.member.view.search | `sales_team.crm_team_member_view_search` | - |
| list | crm.team.member.view.list | `sales_team.crm_team_member_view_tree` | - |
| kanban | crm.team.member.view.kanban | `sales_team.crm_team_member_view_kanban` | - |
| form | crm.team.member.view.form | `sales_team.crm_team_member_view_form` | - |



**Filtros de búsqueda (sales_team.crm_team_member_view_search):**

- **Archived** (`[('active', '=', False)]`)


*Agrupar por:*
- Sales Team








