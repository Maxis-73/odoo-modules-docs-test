# Módulo: Partners Geolocation

## Información General
- **Nombre técnico:** base_geolocalize
- **Versión:** 2.1
- **Categoría:** Hidden/Tools
- **Dependencias:** base_setup




## Descripción

Partners Geolocation
========================
    



## Modelos

### res.config.settings


- Hereda de:

  - res.config.settings




#### Campos
- **geoloc_provider_id** (Many2one) → base.geo_provider
- **geoloc_provider_techname** (Char)
- **geoloc_provider_googlemap_key** (Char)





### base.geo_provider


- Hereda de: Base



#### Campos
- **tech_name** (Char)
- **name** (Char)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | base.geo_provider.form | `base_geolocalize.view_geo_provider_form` | - |




### base.geocoder


- Hereda de: Base



- No agrega campos




### res.partner


- Hereda de:

  - res.partner




#### Campos
- **date_localization** (Date)










