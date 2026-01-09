# Módulo: Spreadsheet dashboard

## Información General
- **Nombre técnico:** spreadsheet_dashboard
- **Versión:** 1.0
- **Categoría:** Productivity/Dashboard
- **Dependencias:** spreadsheet


## Propósito
Spreadsheet



## Descripción
Spreadsheet



## Modelos

### spreadsheet.dashboard.share


- Hereda de:

  - spreadsheet.mixin




#### Campos
- **dashboard_id** (Many2one) → spreadsheet.dashboard
- **excel_export** (Binary)
- **access_token** (Char)
- **full_url** (Char)
- **name** (Char)





### spreadsheet.dashboard


- Hereda de:

  - spreadsheet.mixin




#### Campos
- **name** (Char)
- **dashboard_group_id** (Many2one) → spreadsheet.dashboard.group
- **sequence** (Integer)
- **sample_dashboard_file_path** (Char)
- **is_published** (Boolean)
- **company_id** (Many2one) → res.company
- **group_ids** (Many2many) → res.groups
- **main_data_model_ids** (Many2many) → ir.model





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | spreadsheet.dashboard.view.list | `spreadsheet_dashboard.spreadsheet_dashboard_view_list` | - |
| form | spreadsheet.dashboard.view.form | `spreadsheet_dashboard.spreadsheet_dashboard_view_form` | - |




### spreadsheet.dashboard.group


- Hereda de: Base



#### Campos
- **name** (Char)
- **dashboard_ids** (One2many) → spreadsheet.dashboard
- **published_dashboard_ids** (One2many) → spreadsheet.dashboard
- **sequence** (Integer)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | spreadsheet.dashboard.group.view.list | `spreadsheet_dashboard.spreadsheet_dashboard_container_view_list` | - |
| form | spreadsheet.dashboard.group.view.form | `spreadsheet_dashboard.spreadsheet_dashboard_container_view_form` | - |









