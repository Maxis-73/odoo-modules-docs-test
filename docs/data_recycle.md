# Módulo: Data Recycle

## Información General
- **Nombre técnico:** data_recycle
- **Versión:** 1.3
- **Categoría:** Productivity/Data Cleaning
- **Dependencias:** mail


## Propósito
Find old records and archive/delete them



## Descripción
Find old records and archive/delete them



## Modelos

### data_recycle.record


- Hereda de: Base



- Campos:

  - **active** (Boolean) → Active


  - **name** (Char) → Record Name


  - **recycle_model_id** (Many2one) → data_recycle.model


  - **res_id** (Integer) → Record ID


  - **res_model_id** (Many2one)


  - **res_model_name** (Char)


  - **company_id** (Many2one) → res.company





### data_recycle.model


- Hereda de: Base



- Campos:

  - **active** (Boolean)


  - **name** (Char)


  - **res_model_id** (Many2one) → ir.model


  - **res_model_name** (Char)


  - **recycle_record_ids** (One2many) → data_recycle.record


  - **recycle_mode** (Selection)


  - **recycle_action** (Selection)


  - **domain** (Char)


  - **time_field_id** (Many2one) → ir.model.fields


  - **time_field_delta** (Integer)


  - **time_field_delta_unit** (Selection)


  - **include_archived** (Boolean)


  - **records_to_recycle_count** (Integer) → Records To Recycle


  - **notify_user_ids** (Many2many) → res.users


  - **notify_frequency** (Integer)


  - **notify_frequency_period** (Selection)


  - **last_notification** (Datetime)








## Vistas


### data_recycle.model

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | Field Recyle Model List | `data_recycle.view_data_recycle_model_list` | - |
| form | Field Recyle Model Form | `data_recycle.view_data_merge_model_form` | - |



#### Botones (data_recycle.view_data_merge_model_form)
- **Run Now** (object)
- **open_records** (object)


### data_recycle.record

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | Field Recycle Record List | `data_recycle.view_data_recycle_record_list` | - |
| search | Field Recycle Record Search | `data_recycle.view_data_recycle_record_search` | - |



#### Filtros de búsqueda (data_recycle.view_data_recycle_record_search)

**Filtros:**
- **Discarded** (`[('active', '=', False)]`)

