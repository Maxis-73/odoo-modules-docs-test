# Módulo: Recruitment - Skills Management

## Información General
- **Nombre técnico:** hr_recruitment_skills
- **Versión:** 1.0
- **Categoría:** Human Resources/Recruitment
- **Dependencias:** hr_skills, hr_recruitment


## Propósito
Manage skills of your employees





## Modelos

### hr.applicant


- Hereda de:

  - hr.applicant




- Campos:

  - **candidate_skill_ids** (One2many)


  - **skill_ids** (Many2many)





### hr.candidate.skill


- Hereda de: Base



- Campos:

  - **candidate_id** (Many2one) → hr.candidate


  - **skill_id** (Many2one) → hr.skill


  - **skill_level_id** (Many2one) → hr.skill.level


  - **skill_type_id** (Many2one) → hr.skill.type


  - **level_progress** (Integer)





### hr.candidate


- Hereda de:

  - hr.candidate




- Campos:

  - **candidate_skill_ids** (One2many) → hr.candidate.skill


  - **skill_ids** (Many2many) → hr.skill


  - **matching_skill_ids** (Many2many) → hr.skill


  - **missing_skill_ids** (Many2many) → hr.skill


  - **matching_score** (Float)





### hr.job


- Hereda de:

  - hr.job




- Campos:

  - **skill_ids** (Many2many) → hr.skill








## Vistas


### hr.candidate.skill

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | hr.candidate.skill.view.form | `hr_recruitment_skills.hr_applicant_skill_view_form` | - |



### hr.applicant

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | hr.applicant.view.form.inherit.hr.recruitment.skills | `hr_recruitment_skills.hr_applicant_view_form` | hr_recruitment.hr_applicant_view_form |



### hr.candidate

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | hr.candidate.view.form.inherit.hr.recruitment.skills | `hr_recruitment_skills.hr_candidate_view_form` | hr_recruitment.hr_candidate_view_form |


