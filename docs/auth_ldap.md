# Módulo: Authentication via LDAP

## Información General
- **Nombre técnico:** auth_ldap
- **Versión:** N/A
- **Categoría:** Hidden/Tools
- **Dependencias:** base, base_setup






## Modelos

### res.company.ldap


- Hereda de: Base



- Campos:

  - **sequence** (Integer)


  - **company** (Many2one) → res.company


  - **ldap_server** (Char)


  - **ldap_server_port** (Integer)


  - **ldap_binddn** (Char) → LDAP binddn


  - **ldap_password** (Char)


  - **ldap_filter** (Char)


  - **ldap_base** (Char)


  - **user** (Many2one) → res.users


  - **create_user** (Boolean)


  - **ldap_tls** (Boolean)





### res.users


- Hereda de:

  - res.users




- No agrega campos



### res.config.settings


- Hereda de:

  - res.config.settings




- Campos:

  - **ldaps** (One2many)





### res.company


- Hereda de:

  - res.company




- Campos:

  - **ldaps** (One2many) → res.company.ldap








## Vistas


### res.company.ldap

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | res.company.ldap.form | `auth_ldap.view_ldap_installer_form` | - |
| list | res.company.ldap.list | `auth_ldap.res_company_ldap_view_tree` | - |


