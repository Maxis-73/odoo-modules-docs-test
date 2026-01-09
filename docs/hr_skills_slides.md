# Módulo: Skills e-learning

## Información General
- **Nombre técnico:** hr_skills_slides
- **Versión:** 1.0
- **Categoría:** Hidden
- **Dependencias:** hr_skills, website_slides


## Propósito
Add completed courses to resume of your employees



## Descripción

E-learning and Skills for HR
============================

This module add completed courses to resume for employees.
        



## Modelos

### hr.employee


- Hereda de:

  - hr.employee




#### Campos
- **subscribed_courses** (Many2many) → slide.channel
- **has_subscribed_courses** (Boolean)
- **courses_completion_text** (Char)





### hr.resume.line


- Hereda de:

  - hr.resume.line




#### Campos
- **display_type** (Selection)
- **channel_id** (Many2one) → slide.channel
- **course_url** (Char)





### slide.channel.partner


- Hereda de:

  - slide.channel.partner




- No agrega campos




### slide.channel


- Hereda de:

  - slide.channel




- No agrega campos






