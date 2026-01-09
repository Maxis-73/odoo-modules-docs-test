# Módulo: Customer Rating

## Información General
- **Nombre técnico:** rating
- **Versión:** 1.1
- **Categoría:** Productivity
- **Dependencias:** mail




## Descripción

This module allows a customer to give rating.




## Modelos

### rating.parent.mixin


- Hereda de: Base



#### Campos
- **rating_ids** (One2many) → rating.rating
- **rating_percentage_satisfaction** (Integer) → Rating Satisfaction
- **rating_count** (Integer)
- **rating_avg** (Float) → Average Rating
- **rating_avg_percentage** (Float) → Average Rating (%)





### mail.thread


- Hereda de:

  - mail.thread




#### Campos
- **rating_ids** (One2many) → rating.rating





### rating.rating


- Hereda de: Base



#### Campos
- **create_date** (Datetime)
- **res_name** (Char)
- **res_model_id** (Many2one) → ir.model
- **res_model** (Char)
- **res_id** (Many2oneReference)
- **resource_ref** (Reference)
- **parent_res_name** (Char) → Parent Document Name
- **parent_res_model_id** (Many2one) → ir.model
- **parent_res_model** (Char) → Parent Document Model
- **parent_res_id** (Integer) → Parent Document
- **parent_ref** (Reference)
- **rated_partner_id** (Many2one) → res.partner
- **rated_partner_name** (Char)
- **partner_id** (Many2one) → res.partner
- **rating** (Float)
- **rating_image** (Binary) → Image
- **rating_image_url** (Char) → Image URL
- **rating_text** (Selection)
- **feedback** (Text) → Comment
- **message_id** (Many2one) → mail.message
- **is_internal** (Boolean) → Visible Internally Only
- **access_token** (Char) → Security Token
- **consumed** (Boolean)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | rating.rating.list | `rating.rating_rating_view_tree` | - |
| form | rating.rating.form | `rating.rating_rating_view_form` | - |
| kanban | rating.rating.kanban | `rating.rating_rating_view_kanban` | - |
| kanban | rating.rating.view.kanban.stars | `rating.rating_rating_view_kanban_stars` | - |
| pivot | rating.rating.pivot | `rating.rating_rating_view_pivot` | - |
| graph | rating.rating.graph | `rating.rating_rating_view_graph` | - |
| search | rating.rating.search | `rating.rating_rating_view_search` | - |



**Filtros de búsqueda (rating.rating_rating_view_search):**

- **My Ratings** (`[('rated_partner_id.user_ids', 'in', [uid])]`)
- **Satisfied** (`[('rating_text', '=', 'top')]`)
- **Okay** (`[('rating_text', '=', 'ok')]`)
- **Dissatisfied** (`[('rating_text', '=', 'ko')]`)
- **filter_create_date**
- **Last 7 Days** (`[('create_date', '>', datetime.datetime.combine(context_today() - datetime.timedelta(days=7), datetime.time(23, 59, 59)).to_utc())]`)
- **Last 30 Days** (`[('create_date', '>', datetime.datetime.combine(context_today() - datetime.timedelta(days=30), datetime.time(23, 59, 59)).to_utc())]`)
- **Last 365 Days** (`[('create_date', '>', datetime.datetime.combine(context_today() - datetime.timedelta(days=365), datetime.time(23, 59, 59)).to_utc())]`)


*Agrupar por:*
- Rated Operator
- Customer
- Rating
- Resource
- Submitted on



### rating.mixin


- Hereda de:

  - mail.thread




#### Campos
- **rating_last_value** (Float) → Rating Last Value
- **rating_last_feedback** (Text) → Rating Last Feedback
- **rating_last_image** (Binary) → Rating Last Image
- **rating_count** (Integer) → Rating count
- **rating_avg** (Float) → Average Rating
- **rating_avg_text** (Selection)
- **rating_percentage_satisfaction** (Float) → Rating Satisfaction
- **rating_last_text** (Selection)





### mail.message


- Hereda de:

  - mail.message




#### Campos
- **rating_ids** (One2many) → rating.rating
- **rating_id** (Many2one) → rating.rating
- **rating_value** (Float) → Rating Value










