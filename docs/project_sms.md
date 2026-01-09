# Módulo: Project - SMS

## Información General
- **Nombre técnico:** project_sms
- **Versión:** 1.1
- **Categoría:** Hidden
- **Dependencias:** project, sms


## Propósito
Send text messages when project/task stage move



## Descripción
Send text messages when project/task stage move



## Modelos

### project.task.type


- Hereda de:

  - project.task.type




#### Campos
- **sms_template_id** (Many2one) → sms.template





### project.project.stage


- Hereda de:

  - project.project.stage




#### Campos
- **sms_template_id** (Many2one) → sms.template





### project.project


- Hereda de:

  - project.project




- No agrega campos




### project.task


- Hereda de:

  - project.task




- No agrega campos






