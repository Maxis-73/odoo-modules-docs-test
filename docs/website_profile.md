# Módulo: Website profile

## Información General
- **Nombre técnico:** website_profile
- **Versión:** 1.0
- **Categoría:** Hidden
- **Dependencias:** website_partner, gamification


## Propósito
Access the website profile of the users



## Descripción
Allows to access the website profile of the users and see their statistics (karma, badges, etc..)



## Modelos

### website


- Hereda de:

  - website




#### Campos
- **karma_profile_min** (Integer)





### res.users


- Hereda de:

  - res.users




- No agrega campos




### gamification.badge


- Hereda de:


  - gamification.badge

  - website.published.mixin





- No agrega campos






