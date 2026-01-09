# Módulo: Cloud Storage Migration

## Información General
- **Nombre técnico:** cloud_storage_migration
- **Versión:** 1.0
- **Categoría:** Technical Settings
- **Dependencias:** cloud_storage


## Propósito
Migrate local attachments to cloud storage





## Modelos

### ir.attachment


- Hereda de:

  - ir.attachment




- No agrega campos




### res.config.settings


- Hereda de:

  - res.config.settings




#### Campos
- **cloud_storage_migration_progress** (Integer)
- **cloud_storage_migration_message_model_ids** (One2many) → ir.model
- **cloud_storage_migration_message_models** (Char)
- **cloud_storage_migration_all_model_ids** (One2many) → ir.model
- **cloud_storage_migration_all_models** (Char)





### cloud.storage.migration.report


- Hereda de: Base



#### Campos
- **res_model** (Char)
- **res_model_name** (Char)
- **message_sum_size** (Integer)
- **message_max_size** (Integer)
- **message_count** (Integer)
- **message_to_migrate** (Boolean)
- **all_sum_size** (Integer)
- **all_max_size** (Integer)
- **all_count** (Integer)
- **all_to_migrate** (Boolean)
- **has_attachment_rel** (Boolean)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | cloud.storage.migration.report.list | `cloud_storage_migration.view_cloud_storage_migration_report_list` | - |









