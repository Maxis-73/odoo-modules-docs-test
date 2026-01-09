# Módulo: Onboarding Toolbox

## Información General
- **Nombre técnico:** onboarding
- **Versión:** 1.2
- **Categoría:** Hidden
- **Dependencias:** web




## Descripción

This module allows to manage onboardings and their progress
    



## Modelos

### onboarding.progress


- Hereda de: Base



- Campos:

  - **onboarding_state** (Selection)


  - **is_onboarding_closed** (Boolean) → Was panel closed?


  - **company_id** (Many2one) → res.company


  - **onboarding_id** (Many2one) → onboarding.onboarding


  - **progress_step_ids** (Many2many) → onboarding.progress.step





### onboarding.onboarding.step


- Hereda de: Base



- Campos:

  - **onboarding_ids** (Many2many) → onboarding.onboarding


  - **title** (Char) → Title


  - **description** (Char) → Description


  - **button_text** (Char) → Button text


  - **done_icon** (Char) → Font Awesome Icon when completed


  - **done_text** (Char) → Text to show when step is completed


  - **step_image** (Binary) → Step Image


  - **step_image_filename** (Char) → Step Image Filename


  - **step_image_alt** (Char) → Alt Text for the Step Image


  - **panel_step_open_action_name** (Char)


  - **current_progress_step_id** (Many2one) → onboarding.progress.step


  - **current_step_state** (Selection)


  - **progress_ids** (One2many) → onboarding.progress.step


  - **is_per_company** (Boolean) → Is per company


  - **sequence** (Integer)





### onboarding.progress.step


- Hereda de: Base



- Campos:

  - **progress_ids** (Many2many) → onboarding.progress


  - **step_state** (Selection)


  - **step_id** (Many2one) → onboarding.onboarding.step


  - **company_id** (Many2one) → res.company





### onboarding.onboarding


- Hereda de: Base



- Campos:

  - **name** (Char) → Name of the onboarding


  - **route_name** (Char) → One word name


  - **step_ids** (Many2many) → onboarding.onboarding.step


  - **text_completed** (Char) → Message at completion


  - **is_per_company** (Boolean) → Should be done per company?


  - **panel_close_action_name** (Char) → Closing action


  - **current_progress_id** (Many2one) → onboarding.progress


  - **current_onboarding_state** (Selection)


  - **is_onboarding_closed** (Boolean)


  - **progress_ids** (One2many) → onboarding.progress


  - **sequence** (Integer)








## Vistas


### onboarding.onboarding

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | onboarding.onboarding.view.list | `onboarding.onboarding_onboarding_view_tree` | - |
| form | onboarding.onboarding.view.form | `onboarding.onboarding_onboarding_view_form` | - |



#### Botones (onboarding.onboarding_onboarding_view_form)
- **Toggle visibility** (object)


### onboarding.onboarding.step

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | onboarding.onboarding.step.view.list | `onboarding.onboarding_onboarding_step_view_tree` | - |
| form | onboarding.onboarding.step.view.form | `onboarding.onboarding_onboarding_step_view_form` | - |


