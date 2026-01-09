# Módulo: Forum on Courses

## Información General
- **Nombre técnico:** website_slides_forum
- **Versión:** 1.0
- **Categoría:** Website/eLearning
- **Dependencias:** website_slides, website_forum


## Propósito
Allows to link forum on a course



## Descripción
A Slide channel can be linked to forum. Also, profiles from slide and forum are regrouped together



## Modelos

### forum.forum


- Hereda de:

  - forum.forum




#### Campos
- **slide_channel_ids** (One2many) → slide.channel
- **slide_channel_id** (Many2one) → slide.channel
- **visibility** (Selection)
- **image_1920** (Image) → Image





### slide.channel


- Hereda de:

  - slide.channel




#### Campos
- **forum_id** (Many2one) → forum.forum
- **forum_total_posts** (Integer) → Number of active forum posts










## Vistas Adicionales


### forum.post

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| graph | forum.post.view.graph.slides | `website_slides_forum.forum_post_view_graph_slides` | - |




