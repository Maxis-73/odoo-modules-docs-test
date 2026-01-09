# Módulo: Portal Rating

## Información General
- **Nombre técnico:** portal_rating
- **Versión:** 1.0
- **Categoría:** Hidden
- **Dependencias:** portal, rating




## Descripción

Bridge module adding rating capabilities on portal. It includes notably
inclusion of rating directly within the customer portal discuss widget.
        



## Modelos

### mail.thread


- Hereda de:

  - mail.thread




- No agrega campos



### mail.message


- Hereda de:

  - mail.message




- No agrega campos



### rating.rating


- Hereda de:

  - rating.rating




- Campos:

  - **publisher_comment** (Text) → Publisher comment


  - **publisher_id** (Many2one) → res.partner


  - **publisher_datetime** (Datetime) → Commented on





### ir.http


- Hereda de:

  - ir.http




- No agrega campos





