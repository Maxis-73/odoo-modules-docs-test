# Módulo: Sales PDF Quotation Builder

## Información General
- **Nombre técnico:** sale_pdf_quote_builder
- **Versión:** N/A
- **Categoría:** Sales/Sales
- **Dependencias:** sale_management




## Descripción
Build nice quotations



## Modelos

### sale.order


- Hereda de:

  - sale.order




#### Campos
- **available_product_document_ids** (Many2many) → quotation.document
- **is_pdf_quote_builder_available** (Boolean)
- **quotation_document_ids** (Many2many) → quotation.document
- **customizable_pdf_form_fields** (Json)





### product.document


- Hereda de:

  - product.document




#### Campos
- **attached_on_sale** (Selection)
- **form_field_ids** (Many2many) → sale.pdf.form.field





### sale.order.line


- Hereda de:

  - sale.order.line




#### Campos
- **available_product_document_ids** (Many2many) → product.document
- **product_document_ids** (Many2many) → product.document





### quotation.document


- Hereda de: Base



#### Campos
- **ir_attachment_id** (Many2one) → ir.attachment
- **document_type** (Selection)
- **active** (Boolean)
- **sequence** (Integer)
- **quotation_template_ids** (Many2many) → sale.order.template
- **form_field_ids** (Many2many) → sale.pdf.form.field





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | quotation.document.form | `sale_pdf_quote_builder.quotation_document_form` | - |
| kanban | quotation.document.kanban | `sale_pdf_quote_builder.quotation_document_kanban` | - |
| list | quotation.document.list | `sale_pdf_quote_builder.quotation_document_list` | - |
| search | quotation.document.search | `sale_pdf_quote_builder.quotation_document_search_view` | - |



**Botones (sale_pdf_quote_builder.quotation_document_form):**
- **Configure dynamic fields** (object) - Grupos: `base.group_system,base.group_no_one`


**Filtros de búsqueda (sale_pdf_quote_builder.quotation_document_search_view):**

- **All**
- **Archived** (`[('active', '=', False)]`)


*Agrupar por:*
- Document type
- Quotation Template



### ir.actions.report


- Hereda de:

  - ir.actions.report




- No agrega campos




### sale.pdf.form.field


- Hereda de: Base



#### Campos
- **name** (Char)
- **document_type** (Selection)
- **path** (Char)
- **product_document_ids** (Many2many) → product.document
- **quotation_document_ids** (Many2many) → quotation.document





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | sale.pdf.form.field.list | `sale_pdf_quote_builder.sale_pdf_form_field_list` | - |
| search | sale.pdf.form.field.search | `sale_pdf_quote_builder.quotation_document_search` | - |



**Filtros de búsqueda (sale_pdf_quote_builder.quotation_document_search):**

- **Customizable** (`[('path', '=', False)]`)
- **This document** (`[                         ('document_type', '=', context.get('default_document_type')),                         ('product_document_ids', '=', context.get('default_product_document_ids')),                         ('quotation_document_ids', '=', context.get('default_quotation_document_ids'))                     ]`)



### sale.order.template


- Hereda de:

  - sale.order.template




#### Campos
- **quotation_document_ids** (Many2many) → quotation.document










