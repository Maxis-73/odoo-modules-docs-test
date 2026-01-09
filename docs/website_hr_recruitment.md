# Módulo: Online Jobs

## Información General
- **Nombre técnico:** website_hr_recruitment
- **Versión:** 1.1
- **Categoría:** Website/Website
- **Dependencias:** hr_recruitment, website_mail


## Propósito
Manage your online hiring process



## Descripción
This module allows to publish your available job positions on your website and keep track of application submissions easily. It comes as an add-on of *Recruitment* app.



## Modelos

### website


- Hereda de:

  - website




- No agrega campos




### hr.applicant


- Hereda de:

  - hr.applicant




- No agrega campos




### hr.department


- Hereda de:

  - hr.department




#### Campos
- **display_name** (Char)





### hr.job


- Hereda de:


  - hr.job

  - website.seo.metadata

  - website.published.multi.mixin

  - website.searchable.mixin





#### Campos
- **description** (Html) → Job Description
- **website_published** (Boolean)
- **website_description** (Html) → Website description
- **job_details** (Html) → Process Details
- **published_date** (Date)
- **full_url** (Char) → job URL





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| kanban | Job Pages Kanban | `website_hr_recruitment.job_pages_kanban_view` | hr_job_website_inherit |




### hr.recruitment.source


- Hereda de:

  - hr.recruitment.source




#### Campos
- **url** (Char)










