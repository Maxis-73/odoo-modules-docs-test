# Módulo: Privacy

## Información General
- **Nombre técnico:** privacy_lookup
- **Versión:** 1.0
- **Categoría:** Hidden
- **Dependencias:** mail






## Modelos

### res.partner


- Hereda de:

  - res.partner




- No agrega campos



### privacy.log


- Hereda de: Base



- Campos:

  - **date** (Datetime)


  - **anonymized_name** (Char)


  - **anonymized_email** (Char)


  - **user_id** (Many2one) → res.users


  - **execution_details** (Text)


  - **records_description** (Text)


  - **additional_note** (Text)








## Vistas


### privacy.log

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | privacy.log.view.list | `privacy_lookup.privacy_log_view_list` | - |
| form | privacy.log.view.form | `privacy_lookup.privacy_log_view_form` | - |



### privacy.lookup.wizard

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | privacy.lookup.wizard.view.form | `privacy_lookup.privacy_lookup_wizard_view_form` | - |



#### Botones (privacy_lookup.privacy_lookup_wizard_view_form)
- **Lookup** (object)
- **action_open_lines** (object)


### privacy.lookup.wizard.line

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | privacy.lookup.wizard.line.view.list | `privacy_lookup.privacy_lookup_wizard_line_view_tree` | - |
| search | privacy.lookup.wizard.line.view.search | `privacy_lookup.privacy_lookup_wizard_line_view_search` | - |



#### Filtros de búsqueda (privacy_lookup.privacy_lookup_wizard_line_view_search)

**Filtros:**
- **Can be archived** (`[('has_active', '=', True)]`)
- **Archived** (`[('is_active', '=', False)]`)


**Agrupar por:**
- Model

