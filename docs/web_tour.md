# Módulo: Tours

## Información General
- **Nombre técnico:** web_tour
- **Versión:** 1.0
- **Categoría:** Hidden
- **Dependencias:** web




## Descripción

Odoo Web tours.
========================





## Modelos

### res.users


- Hereda de:

  - res.users




#### Campos
- **tour_enabled** (Boolean)





### web_tour.tour


- Hereda de: Base



#### Campos
- **name** (Char)
- **step_ids** (One2many) → web_tour.tour.step
- **url** (Char)
- **sharing_url** (Char)
- **rainbow_man_message** (Html)
- **sequence** (Integer)
- **custom** (Boolean)
- **user_consumed_ids** (Many2many) → res.users





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | - | `web_tour.tour_form` | - |
| list | - | `web_tour.tour_list` | - |
| search | tour.search | `web_tour.tour_search` | - |




### web_tour.tour.step


- Hereda de: Base



#### Campos
- **trigger** (Char)
- **content** (Char)
- **tour_id** (Many2one) → web_tour.tour
- **run** (Char)
- **sequence** (Integer)





### ir.http


- Hereda de:

  - ir.http




- No agrega campos









