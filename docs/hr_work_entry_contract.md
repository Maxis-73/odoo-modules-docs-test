# Módulo: Work Entries - Contract

## Información General
- **Nombre técnico:** hr_work_entry_contract
- **Versión:** N/A
- **Categoría:** Human Resources/Employees
- **Dependencias:** hr_work_entry, hr_contract


## Propósito
Manage work entries





## Modelos

### hr.contract


- Hereda de:

  - hr.contract




#### Campos
- **date_generated_from** (Datetime)
- **date_generated_to** (Datetime)
- **last_generation_date** (Date)
- **work_entry_source** (Selection)
- **work_entry_source_calendar_invalid** (Boolean)





### hr.employee


- Hereda de:

  - hr.employee




- No agrega campos




### resource.calendar


- Hereda de:

  - resource.calendar




- No agrega campos




### hr.work.entry


- Hereda de:

  - hr.work.entry




#### Campos
- **contract_id** (Many2one) → hr.contract
- **employee_id** (Many2one)
- **work_entry_source** (Selection)





### hr.work.entry.type


- Hereda de:

  - hr.work.entry.type




#### Campos
- **is_leave** (Boolean)










## Vistas Adicionales


### hr.work.entry.regeneration.wizard

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | hr_work_entry_regeneration_wizard | `hr_work_entry_contract.hr_work_entry_regeneration_wizard` | - |



**Botones (hr_work_entry_contract.hr_work_entry_regeneration_wizard):**
- **Regenerate Work Entries** (object)
- **Regenerate Work Entries**
- **Cancel**



