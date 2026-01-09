# Módulo: Cloud Storage Azure

## Información General
- **Nombre técnico:** cloud_storage_azure
- **Versión:** 1.0
- **Categoría:** Technical Settings
- **Dependencias:** cloud_storage


## Propósito
Store chatter attachments in the Azure cloud





## Modelos

### ir.attachment


- Hereda de:

  - ir.attachment




- No agrega campos




### res.config.settings


- Hereda de:

  - res.config.settings




#### Campos
- **cloud_storage_provider** (Selection)
- **cloud_storage_azure_account_name** (Char)
- **cloud_storage_azure_container_name** (Char)
- **cloud_storage_azure_tenant_id** (Char)
- **cloud_storage_azure_client_id** (Char)
- **cloud_storage_azure_client_secret** (Char)
- **cloud_storage_azure_invalidate_user_delegation_key** (Boolean)







