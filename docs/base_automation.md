# Módulo: Automation Rules

## Información General
- **Nombre técnico:** base_automation
- **Versión:** 1.0
- **Categoría:** Sales/Sales
- **Dependencias:** base, digest, resource, mail, sms




## Descripción

This module allows to implement automation rules for any object.
================================================================

Use automation rules to automatically trigger actions for various screens.

**Example:** A lead created by a specific user may be automatically set to a specific
Sales Team, or an opportunity which still has status pending after 14 days might
trigger an automatic reminder email.
    



## Modelos

### ir.actions.server


- Hereda de:

  - ir.actions.server




#### Campos
- **name** (Char)
- **usage** (Selection)
- **base_automation_id** (Many2one) → base.automation





### base.automation


- Hereda de: Base



#### Campos
- **name** (Char)
- **description** (Html)
- **model_id** (Many2one) → ir.model
- **model_name** (Char)
- **model_is_mail_thread** (Boolean)
- **action_server_ids** (One2many) → ir.actions.server
- **url** (Char)
- **webhook_uuid** (Char)
- **record_getter** (Char)
- **log_webhook_calls** (Boolean)
- **active** (Boolean)
- **trigger** (Selection)
- **trg_selection_field_id** (Many2one) → ir.model.fields.selection
- **trg_field_ref_model_name** (Char)
- **trg_field_ref** (Many2oneReference)
- **trg_date_id** (Many2one) → ir.model.fields
- **trg_date_range** (Integer)
- **trg_date_range_type** (Selection)
- **trg_date_calendar_id** (Many2one) → resource.calendar
- **filter_pre_domain** (Char)
- **filter_domain** (Char)
- **last_run** (Datetime)
- **on_change_field_ids** (Many2many) → ir.model.fields
- **trigger_field_ids** (Many2many) → ir.model.fields
- **least_delay_msg** (Char)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | Automations | `base_automation.view_base_automation_form` | - |
| list | base.automation.list | `base_automation.view_base_automation_tree` | - |
| kanban | base.automation.kanban | `base_automation.view_base_automation_kanban` | - |
| search | base.automation.search | `base_automation.view_base_automation_search` | - |



**Botones (base_automation.view_base_automation_form):**
- **Logs** (object)
- **Rotate Secret** (object)
- **delete** (delete)


**Filtros de búsqueda (base_automation.view_base_automation_search):**

- **Include Archived** (`[('active', 'in', [False, True])]`)








