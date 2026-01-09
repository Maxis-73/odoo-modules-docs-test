# Módulo: Customer References

## Información General
- **Nombre técnico:** website_customer
- **Versión:** 1.0
- **Categoría:** Website/Website
- **Dependencias:** website_crm_partner_assign, website_partner, website_google_map


## Propósito
Publish your customer references



## Descripción

Publish your customers as business references on your website to attract new potential prospects.
    



## Modelos

### website


- Hereda de:

  - website




- No agrega campos



### res.partner


- Hereda de:

  - res.partner




- Campos:

  - **website_tag_ids** (Many2many) → res.partner.tag





### res.partner.tag


- Hereda de:

  - website.published.mixin




- Campos:

  - **name** (Char) → Category Name


  - **partner_ids** (Many2many) → res.partner


  - **classname** (Selection) → get_selection_class


  - **active** (Boolean) → Active








## Vistas


### res.partner.tag

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | Website Tags | `website_customer.view_partner_tag_form` | - |
| list | Website Tags | `website_customer.view_partner_tag_list` | - |
| search | res.partner.tag.view.search | `website_customer.res_partner_tag_view_search` | - |



#### Filtros de búsqueda (website_customer.res_partner_tag_view_search)

**Filtros:**
- **Archived** (`[('active', '=', False)]`)

