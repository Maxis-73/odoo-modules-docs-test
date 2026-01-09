# Módulo: KPI Digests

## Información General
- **Nombre técnico:** digest
- **Versión:** 1.1
- **Categoría:** Marketing
- **Dependencias:** mail, portal, resource




## Descripción

Send KPI Digests periodically
=============================




## Modelos

### digest.tip


- Hereda de: Base



#### Campos
- **sequence** (Integer) → Sequence
- **name** (Char) → Name
- **user_ids** (Many2many) → res.users
- **tip_description** (Html) → Tip description
- **group_id** (Many2one) → res.groups





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | digest.tip.view.list | `digest.digest_tip_view_tree` | - |
| form | digest.tip.view.form | `digest.digest_tip_view_form` | - |
| search | digest.tip.view.search | `digest.digest_tip_view_search` | - |




### digest.digest


- Hereda de: Base



#### Campos
- **name** (Char)
- **user_ids** (Many2many) → res.users
- **periodicity** (Selection)
- **next_run_date** (Date)
- **currency_id** (Many2one)
- **company_id** (Many2one) → res.company
- **available_fields** (Char)
- **is_subscribed** (Boolean) → Is user subscribed
- **state** (Selection)
- **kpi_res_users_connected** (Boolean) → Connected Users
- **kpi_res_users_connected_value** (Integer)
- **kpi_mail_message_total** (Boolean) → Messages Sent
- **kpi_mail_message_total_value** (Integer)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | digest.digest.view.list | `digest.digest_digest_view_tree` | - |
| form | digest.digest.view.form | `digest.digest_digest_view_form` | - |
| search | digest.digest.view.search | `digest.digest_digest_view_search` | - |



**Botones (digest.digest_digest_view_form):**
- **Send Now** (object) - Grupos: `base.group_system`
- **Deactivate** (object) - Grupos: `base.group_system`
- **Activate** (object) - Grupos: `base.group_system`


**Filtros de búsqueda (digest.digest_digest_view_search):**

- **Activated** (`[('state', '=', 'activated')]`)
- **Deactivated** (`[('state', '=', 'deactivated')]`)


*Agrupar por:*
- Periodicity



### res.users


- Hereda de:

  - res.users




- No agrega campos




### res.config.settings


- Hereda de:

  - res.config.settings




#### Campos
- **digest_emails** (Boolean)
- **digest_id** (Many2one) → digest.digest










