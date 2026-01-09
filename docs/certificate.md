# Módulo: Certificate

## Información General
- **Nombre técnico:** certificate
- **Versión:** 0.1
- **Categoría:** Hidden/Tools
- **Dependencias:** base_setup


## Propósito
Manage certificate





## Modelos

### certificate.key


- Hereda de: Base



#### Campos
- **name** (Char)
- **content** (Binary)
- **password** (Char)
- **pem_key** (Binary)
- **public** (Boolean)
- **loading_error** (Text)
- **active** (Boolean)
- **company_id** (Many2one) → res.company





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | certificate.key.form | `certificate.certificate_key_view_form` | - |
| list | certificate.key.list | `certificate.certificate_key_view_list` | - |
| search | certificate.key.search | `certificate.certificate_key_view_search` | - |



**Filtros de búsqueda (certificate.certificate_key_view_search):**

- **Archived** (`[('active','=',False)]`)
- **Private** (`[('pem_key', '!=', False), ('public','=',False)]`)
- **Public** (`[('pem_key', '!=', False), ('public','=',True)]`)
- **Invalid** (`[('pem_key', '=', False)]`)



### certificate.certificate


- Hereda de: Base



#### Campos
- **name** (Char)
- **content** (Binary)
- **pkcs12_password** (Char)
- **private_key_id** (Many2one) → certificate.key
- **public_key_id** (Many2one) → certificate.key
- **scope** (Selection)
- **content_format** (Selection)
- **pem_certificate** (Binary)
- **subject_common_name** (Char)
- **serial_number** (Char)
- **date_start** (Datetime)
- **date_end** (Datetime)
- **loading_error** (Text)
- **is_valid** (Boolean)
- **active** (Boolean)
- **company_id** (Many2one) → res.company
- **country_code** (Char)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | certificate.certificate.form | `certificate.certificate_certificate_view_form` | - |
| list | certificate.certificate.list | `certificate.certificate_certificate_view_list` | - |
| search | certificate.certificate.search | `certificate.certificate_certificate_view_search` | - |



**Filtros de búsqueda (certificate.certificate_certificate_view_search):**

- **General** (`[('scope','=','general')]`)
- **Valid** (`[('is_valid','=',True)]`)
- **Invalid** (`[('is_valid','=',False)]`)
- **Archived** (`[('active','=',False)]`)








