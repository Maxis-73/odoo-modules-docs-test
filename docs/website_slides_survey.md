# Módulo: Course Certifications

## Información General
- **Nombre técnico:** website_slides_survey
- **Versión:** 1.0
- **Categoría:** Website/eLearning
- **Dependencias:** website_slides, survey


## Propósito
Add certification capabilities to your courses



## Descripción
This module lets you use the full power of certifications within your courses.



## Modelos

### survey.user_input


- Hereda de:

  - survey.user_input




- Campos:

  - **slide_id** (Many2one) → slide.slide


  - **slide_partner_id** (Many2one) → slide.slide.partner





### survey.survey


- Hereda de:

  - survey.survey




- Campos:

  - **slide_ids** (One2many) → slide.slide


  - **slide_channel_ids** (One2many) → slide.channel


  - **slide_channel_count** (Integer) → Courses Count





### slide.slide.partner


- Hereda de:

  - slide.slide.partner




- Campos:

  - **user_input_ids** (One2many) → survey.user_input


  - **survey_scoring_success** (Boolean) → Certification Succeeded





### slide.slide


- Hereda de:

  - slide.slide




- Campos:

  - **name** (Char)


  - **slide_category** (Selection)


  - **slide_type** (Selection)


  - **survey_id** (Many2one) → survey.survey


  - **nbr_certification** (Integer) → Number of Certifications


  - **is_preview** (Boolean)





### slide.channel.partner


- Hereda de:

  - slide.channel.partner




- Campos:

  - **nbr_certification** (Integer)


  - **survey_certification_success** (Boolean) → Certified





### slide.channel


- Hereda de:

  - slide.channel




- Campos:

  - **members_certified_count** (Integer) → # Certified Attendees


  - **nbr_certification** (Integer) → Number of Certifications







