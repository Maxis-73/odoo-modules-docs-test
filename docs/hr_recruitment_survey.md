# Módulo: Hr Recruitment Interview Forms

## Información General
- **Nombre técnico:** hr_recruitment_survey
- **Versión:** 1.0
- **Categoría:** Human Resources
- **Dependencias:** survey, hr_recruitment


## Propósito
Surveys



## Descripción

Use interview forms during recruitment process.
This module is integrated with the survey module
to allow you to define interviews for different jobs.
    



## Modelos

### hr.applicant


- Hereda de:

  - hr.applicant




- Campos:

  - **survey_id** (Many2one) → survey.survey


  - **response_ids** (One2many) → survey.user_input





### survey.user_input


- Hereda de:

  - survey.user_input




- Campos:

  - **applicant_id** (Many2one) → hr.applicant





### survey.survey


- Hereda de:

  - survey.survey




- Campos:

  - **survey_type** (Selection)


  - **hr_job_ids** (One2many) → hr.job





### hr.job


- Hereda de:

  - hr.job




- Campos:

  - **survey_id** (Many2one) → survey.survey







