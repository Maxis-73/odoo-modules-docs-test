# Módulo: Website Test

## Información General
- **Nombre técnico:** test_website
- **Versión:** 1.0
- **Categoría:** Hidden
- **Dependencias:** web_unsplash, website, theme_default


## Propósito
Website Test, mainly for module install/uninstall tests



## Descripción
This module contains tests related to website. Those are
present in a separate module as we are testing module install/uninstall/upgrade
and we don't want to reload the website module every time, including it's possible
dependencies. Neither we want to add in website module some routes, views and
models which only purpose is to run tests.



## Modelos

### website


- Hereda de:

  - website




#### Campos
- **some_translatable_field** (Char)





### website


- Hereda de:

  - website




#### Campos
- **name_translated** (Char)





### test.model


- Hereda de:


  - website.seo.metadata

  - website.published.mixin

  - website.searchable.mixin





#### Campos
- **name** (Char)
- **submodel_ids** (One2many) → test.submodel
- **website_description** (Html)
- **tag_id** (Many2one) → test.tag





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| kanban | test.model.kanban | `test_website.test_model_view_kanban` | - |
| list | Test Model Pages List | `test_website.test_model_view_list` | - |
| form | test.model.form | `test_website.view_test_model_form` | - |




### test.submodel


- Hereda de: Base



#### Campos
- **name** (Char)
- **test_model_id** (Many2one) → test.model
- **tag_id** (Many2one) → test.tag





### test.tag


- Hereda de: Base



#### Campos
- **name** (Char)





### test.model.multi.website


- Hereda de:


  - website.published.multi.mixin





#### Campos
- **name** (Char)
- **website_id** (Many2one) → website





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| kanban | test.model.multi.website.kanban | `test_website.test_model_multi_website_view_kanban` | - |
| list | Test Multi Model Pages List | `test_website.test_model_multi_website_view_list` | - |
| list | Test Multi Model Pages list js_class bug | `test_website.test_model_multi_website_view_list_js_class_bug` | - |




### test.model.exposed


- Hereda de:


  - website.seo.metadata

  - website.published.mixin





#### Campos
- **name** (Char)





### res.config.settings


- Hereda de:

  - res.config.settings




- No agrega campos









