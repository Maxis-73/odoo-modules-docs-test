# Módulo: Test - Base Automation

## Información General
- **Nombre técnico:** test_base_automation
- **Versión:** 1.0
- **Categoría:** Hidden
- **Dependencias:** base_automation


## Propósito
Base Automation Tests: Ensure Flow Robustness



## Descripción
This module contains tests related to base automation. Those are
present in a separate module as it contains models used only to perform
tests independently to functional aspects of other models.



## Modelos

### base.automation.lead.test


- Hereda de: Base



- Campos:

  - **name** (Char)


  - **user_id** (Many2one) → res.users


  - **state** (Selection)


  - **active** (Boolean)


  - **tag_ids** (Many2many) → test_base_automation.tag


  - **partner_id** (Many2one) → res.partner


  - **date_automation_last** (Datetime)


  - **employee** (Boolean)


  - **line_ids** (One2many) → base.automation.line.test


  - **priority** (Boolean)


  - **deadline** (Boolean)


  - **is_assigned_to_admin** (Boolean)


  - **stage_id** (Many2one) → test_base_automation.stage





### base.automation.lead.thread.test


- Hereda de:


  - base.automation.lead.test

  - mail.thread





- No agrega campos



### base.automation.line.test


- Hereda de: Base



- Campos:

  - **name** (Char)


  - **lead_id** (Many2one) → base.automation.lead.test


  - **user_id** (Many2one) → res.users





### base.automation.link.test


- Hereda de: Base



- Campos:

  - **name** (Char)


  - **linked_id** (Many2one) → base.automation.linked.test





### base.automation.linked.test


- Hereda de: Base



- Campos:

  - **name** (Char)


  - **another_field** (Char)





### test_base_automation.project


- Hereda de: Base



- Campos:

  - **name** (Char)


  - **task_ids** (One2many) → test_base_automation.task


  - **stage_id** (Many2one) → test_base_automation.stage


  - **tag_ids** (Many2many) → test_base_automation.tag


  - **priority** (Selection)


  - **user_ids** (Many2many) → res.users





### test_base_automation.task


- Hereda de: Base



- Campos:

  - **name** (Char)


  - **parent_id** (Many2one) → test_base_automation.task


  - **project_id** (Many2one) → test_base_automation.project





### test_base_automation.stage


- Hereda de: Base



- Campos:

  - **name** (Char)





### test_base_automation.tag


- Hereda de: Base



- Campos:

  - **name** (Char)





### base.automation.lead.thread.test


- Hereda de:


  - base.automation.lead.test

  - mail.thread





- No agrega campos



### base.automation.model.with.recname.char


- Hereda de: Base



- Campos:

  - **description** (Char)


  - **user_id** (Many2one) → res.users





### base.automation.model.with.recname.m2o


- Hereda de: Base



- Campos:

  - **user_id** (Many2one) → base.automation.model.with.recname.char







