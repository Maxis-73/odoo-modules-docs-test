# Módulo: Blog

## Información General
- **Nombre técnico:** website_blog
- **Versión:** 1.1
- **Categoría:** Website/Website
- **Dependencias:** website_mail, website_partner


## Propósito
Publish blog posts, announces, news





## Modelos

### website


- Hereda de:

  - website




- No agrega campos




### blog.blog


- Hereda de:


  - mail.thread

  - website.seo.metadata

  - website.multi.mixin

  - website.cover_properties.mixin

  - website.searchable.mixin





#### Campos
- **name** (Char) → Blog Name
- **subtitle** (Char) → Blog Subtitle
- **active** (Boolean) → Active
- **content** (Html) → Content
- **blog_post_ids** (One2many) → blog.post
- **blog_post_count** (Integer) → Posts





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | blog.blog.list | `website_blog.view_blog_blog_list` | - |
| form | blog.blog.form | `website_blog.view_blog_blog_form` | - |
| search | blog.blog.search | `website_blog.blog_blog_view_search` | - |



**Filtros de búsqueda (website_blog.blog_blog_view_search):**

- **Archived** (`[('active','=',False)]`)



### blog.tag.category


- Hereda de: Base



#### Campos
- **name** (Char) → Name
- **tag_ids** (One2many) → blog.tag





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | blog_tag_category_form | `website_blog.blog_tag_category_form` | - |
| list | blog_tag_category.list | `website_blog.blog_tag_category_tree` | - |




### blog.tag


- Hereda de:


  - website.seo.metadata





#### Campos
- **name** (Char) → Name
- **category_id** (Many2one) → blog.tag.category
- **color** (Integer) → Color
- **post_ids** (Many2many) → blog.post





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | blog_tag.list | `website_blog.blog_tag_tree` | - |
| form | blog_tag_form | `website_blog.blog_tag_form` | - |




### blog.post


- Hereda de:


  - mail.thread

  - website.seo.metadata

  - website.published.multi.mixin

  - website.cover_properties.mixin

  - website.searchable.mixin





#### Campos
- **name** (Char) → Title
- **subtitle** (Char) → Sub Title
- **author_id** (Many2one) → res.partner
- **author_avatar** (Binary)
- **author_name** (Char)
- **active** (Boolean) → Active
- **blog_id** (Many2one) → blog.blog
- **tag_ids** (Many2many) → blog.tag
- **content** (Html) → Content
- **teaser** (Text) → Teaser
- **teaser_manual** (Text)
- **website_message_ids** (One2many)
- **create_date** (Datetime) → Created on
- **published_date** (Datetime) → Published Date
- **post_date** (Datetime) → Publishing date
- **create_uid** (Many2one) → res.users
- **write_date** (Datetime) → Last Updated on
- **write_uid** (Many2one) → res.users
- **visits** (Integer) → No of Views
- **website_id** (Many2one)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | blog.post.view.form.add | `website_blog.blog_post_view_form_add` | - |
| form | blog.post.form | `website_blog.view_blog_post_form` | - |
| kanban | blog.post.kanban | `website_blog.blog_post_view_kanban` | - |
| search | blog.post.search | `website_blog.view_blog_post_search` | - |
| list | Blog Post Pages List | `website_blog.view_blog_post_list` | - |



**Filtros de búsqueda (website_blog.view_blog_post_search):**

- **Archived** (`[('active','=',False)]`)


*Agrupar por:*
- Blog
- Author
- Last Contributor



### website.snippet.filter


- Hereda de:

  - website.snippet.filter




- No agrega campos









