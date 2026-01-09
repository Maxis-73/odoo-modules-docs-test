# Módulo: Employees

## Información General
- **Nombre técnico:** hr
- **Versión:** 1.1
- **Categoría:** Human Resources/Employees
- **Dependencias:** base_setup, digest, phone_validation, resource_mail, web


## Propósito
Centralize employee information





## Modelos

### hr.department


- Hereda de:


  - mail.thread

  - mail.activity.mixin





- Campos:

  - **name** (Char) → Department Name


  - **complete_name** (Char) → Complete Name


  - **active** (Boolean) → Active


  - **company_id** (Many2one) → res.company


  - **parent_id** (Many2one) → hr.department


  - **child_ids** (One2many) → hr.department


  - **manager_id** (Many2one) → hr.employee


  - **member_ids** (One2many) → hr.employee


  - **has_read_access** (Boolean)


  - **total_employee** (Integer)


  - **jobs_ids** (One2many) → hr.job


  - **plan_ids** (One2many) → mail.activity.plan


  - **plans_count** (Integer)


  - **note** (Text) → Note


  - **color** (Integer) → Color Index


  - **parent_path** (Char)


  - **master_department_id** (Many2one) → hr.department





### hr.employee.category


- Hereda de: Base



- Campos:

  - **name** (Char)


  - **color** (Integer)


  - **employee_ids** (Many2many) → hr.employee





### hr.departure.reason


- Hereda de: Base



- Campos:

  - **sequence** (Integer) → Sequence


  - **name** (Char)


  - **reason_code** (Integer)





### mail.activity.plan


- Hereda de:

  - mail.activity.plan




- Campos:

  - **department_id** (Many2one) → hr.department


  - **department_assignable** (Boolean)





### hr.employee


- Hereda de:


  - hr.employee.base

  - mail.thread.main.attachment

  - mail.activity.mixin

  - resource.mixin

  - avatar.mixin





- Campos:

  - **name** (Char)


  - **user_id** (Many2one) → res.users


  - **user_partner_id** (Many2one)


  - **active** (Boolean) → Active


  - **resource_calendar_id** (Many2one)


  - **department_id** (Many2one)


  - **company_id** (Many2one) → res.company


  - **company_country_id** (Many2one) → res.country


  - **company_country_code** (Char)


  - **private_street** (Char)


  - **private_street2** (Char)


  - **private_city** (Char)


  - **private_state_id** (Many2one) → res.country.state


  - **private_zip** (Char)


  - **private_country_id** (Many2one) → res.country


  - **private_phone** (Char)


  - **private_email** (Char)


  - **lang** (Selection)


  - **country_id** (Many2one) → res.country


  - **gender** (Selection)


  - **marital** (Selection)


  - **spouse_complete_name** (Char)


  - **spouse_birthdate** (Date)


  - **children** (Integer)


  - **place_of_birth** (Char) → Place of Birth


  - **country_of_birth** (Many2one) → res.country


  - **birthday** (Date) → Date of Birth


  - **ssnid** (Char) → SSN No


  - **sinid** (Char) → SIN No


  - **identification_id** (Char)


  - **passport_id** (Char) → Passport No


  - **bank_account_id** (Many2one) → res.partner.bank


  - **permit_no** (Char) → Work Permit No


  - **visa_no** (Char) → Visa No


  - **visa_expire** (Date) → Visa Expiration Date


  - **work_permit_expiration_date** (Date) → Work Permit Expiration Date


  - **has_work_permit** (Binary)


  - **work_permit_scheduled_activity** (Boolean)


  - **work_permit_name** (Char) → work_permit_name


  - **additional_note** (Text)


  - **certificate** (Selection)


  - **study_field** (Char) → Field of Study


  - **study_school** (Char) → School


  - **emergency_contact** (Char) → Contact Name


  - **emergency_phone** (Char) → Contact Phone


  - **distance_home_work** (Integer)


  - **km_home_work** (Integer)


  - **distance_home_work_unit** (Selection)


  - **employee_type** (Selection)


  - **job_id** (Many2one)


  - **child_ids** (One2many) → hr.employee


  - **category_ids** (Many2many) → hr.employee.category


  - **notes** (Text) → Notes


  - **color** (Integer) → Color Index


  - **barcode** (Char)


  - **pin** (Char)


  - **departure_reason_id** (Many2one) → hr.departure.reason


  - **departure_description** (Html)


  - **departure_date** (Date)


  - **message_main_attachment_id** (Many2one)


  - **id_card** (Binary)


  - **driving_license** (Binary)


  - **private_car_plate** (Char)


  - **currency_id** (Many2one) → res.currency


  - **related_partners_count** (Integer)


  - **employee_properties** (Properties) → Properties


  - **activity_ids** (One2many)


  - **activity_state** (Selection)


  - **activity_user_id** (Many2one)


  - **activity_type_id** (Many2one)


  - **activity_type_icon** (Char)


  - **activity_date_deadline** (Date)


  - **my_activity_date_deadline** (Date)


  - **activity_summary** (Char)


  - **activity_exception_decoration** (Selection)


  - **activity_exception_icon** (Char)


  - **message_is_follower** (Boolean)


  - **message_follower_ids** (One2many)


  - **message_partner_ids** (Many2many)


  - **message_ids** (One2many)


  - **has_message** (Boolean)


  - **message_needaction** (Boolean)


  - **message_needaction_counter** (Integer)


  - **message_has_error** (Boolean)


  - **message_has_error_counter** (Integer)


  - **message_attachment_count** (Integer)





### hr.job


- Hereda de:


  - mail.thread





- Campos:

  - **active** (Boolean)


  - **name** (Char)


  - **sequence** (Integer)


  - **expected_employees** (Integer)


  - **no_of_employee** (Integer)


  - **no_of_recruitment** (Integer)


  - **employee_ids** (One2many) → hr.employee


  - **description** (Html)


  - **requirements** (Text) → Requirements


  - **department_id** (Many2one) → hr.department


  - **company_id** (Many2one) → res.company


  - **contract_type_id** (Many2one) → hr.contract.type





### resource.calendar


- Hereda de:

  - resource.calendar




- No agrega campos



### discuss.channel


- Hereda de:

  - discuss.channel




- Campos:

  - **subscription_department_ids** (Many2many) → hr.department





### hr.contract.type


- Hereda de: Base



- Campos:

  - **name** (Char)


  - **code** (Char)


  - **sequence** (Integer)


  - **country_id** (Many2one) → res.country





### ['res.users']


- Hereda de:


  - res.users





- Campos:

  - **employee_ids** (One2many) → hr.employee


  - **employee_id** (Many2one) → hr.employee


  - **job_title** (Char)


  - **work_phone** (Char)


  - **mobile_phone** (Char)


  - **work_email** (Char)


  - **category_ids** (Many2many)


  - **department_id** (Many2one)


  - **address_id** (Many2one)


  - **work_contact_id** (Many2one)


  - **work_location_id** (Many2one)


  - **work_location_name** (Char)


  - **work_location_type** (Selection)


  - **employee_parent_id** (Many2one)


  - **coach_id** (Many2one)


  - **private_street** (Char)


  - **private_street2** (Char)


  - **private_city** (Char)


  - **private_state_id** (Many2one)


  - **private_zip** (Char)


  - **private_country_id** (Many2one)


  - **private_phone** (Char)


  - **private_email** (Char)


  - **private_lang** (Selection)


  - **km_home_work** (Integer)


  - **distance_home_work** (Integer)


  - **distance_home_work_unit** (Selection)


  - **employee_bank_account_id** (Many2one)


  - **employee_country_id** (Many2one)


  - **identification_id** (Char)


  - **ssnid** (Char)


  - **passport_id** (Char)


  - **gender** (Selection)


  - **birthday** (Date)


  - **place_of_birth** (Char)


  - **country_of_birth** (Many2one)


  - **marital** (Selection)


  - **spouse_complete_name** (Char)


  - **spouse_birthdate** (Date)


  - **children** (Integer)


  - **emergency_contact** (Char)


  - **emergency_phone** (Char)


  - **visa_no** (Char)


  - **permit_no** (Char)


  - **visa_expire** (Date)


  - **additional_note** (Text)


  - **barcode** (Char)


  - **pin** (Char)


  - **certificate** (Selection)


  - **study_field** (Char)


  - **study_school** (Char)


  - **employee_count** (Integer)


  - **hr_presence_state** (Selection)


  - **last_activity** (Date)


  - **last_activity_time** (Char)


  - **employee_type** (Selection)


  - **employee_resource_calendar_id** (Many2one)


  - **create_employee** (Boolean)


  - **create_employee_id** (Many2one) → hr.employee


  - **can_edit** (Boolean)


  - **is_system** (Boolean)





### mail.activity.plan.template


- Hereda de:

  - mail.activity.plan.template




- Campos:

  - **responsible_type** (Selection)





### res.config.settings


- Hereda de:

  - res.config.settings




- Campos:

  - **resource_calendar_id** (Many2one) → resource.calendar


  - **module_hr_presence** (Boolean)


  - **module_hr_skills** (Boolean)


  - **module_hr_homeworking** (Boolean)


  - **hr_presence_control_login** (Boolean)


  - **hr_presence_control_email** (Boolean)


  - **hr_presence_control_ip** (Boolean)


  - **module_hr_attendance** (Boolean)


  - **hr_presence_control_email_amount** (Integer)


  - **hr_presence_control_ip_list** (Char)


  - **hr_employee_self_edit** (Boolean)





### hr.work.location


- Hereda de: Base



- Campos:

  - **active** (Boolean)


  - **name** (Char)


  - **company_id** (Many2one) → res.company


  - **location_type** (Selection)


  - **address_id** (Many2one) → res.partner


  - **location_number** (Char)





### resource.resource


- Hereda de:

  - resource.resource




- Campos:

  - **user_id** (Many2one)


  - **employee_id** (One2many) → hr.employee


  - **job_title** (Char)


  - **department_id** (Many2one)


  - **work_email** (Char)


  - **work_phone** (Char)


  - **show_hr_icon_display** (Boolean)


  - **hr_icon_display** (Selection)





### ir.ui.menu


- Hereda de:

  - ir.ui.menu




- No agrega campos



### res.company


- Hereda de:

  - res.company




- Campos:

  - **hr_presence_control_email_amount** (Integer)


  - **hr_presence_control_ip_list** (Char)


  - **employee_properties_definition** (PropertiesDefinition) → Employee Properties


  - **hr_presence_control_login** (Boolean)


  - **hr_presence_control_email** (Boolean)


  - **hr_presence_control_ip** (Boolean)


  - **hr_presence_control_attendance** (Boolean)





### hr.employee.base


- Hereda de: Base



- Campos:

  - **name** (Char)


  - **active** (Boolean) → Active


  - **color** (Integer) → Color Index


  - **department_id** (Many2one) → hr.department


  - **member_of_department** (Boolean) → Member of department


  - **job_id** (Many2one) → hr.job


  - **job_title** (Char) → Job Title


  - **company_id** (Many2one) → res.company


  - **address_id** (Many2one) → res.partner


  - **work_phone** (Char) → Work Phone


  - **phone** (Char)


  - **mobile_phone** (Char) → Work Mobile


  - **work_email** (Char) → Work Email


  - **email** (Char)


  - **work_contact_id** (Many2one) → res.partner


  - **work_location_id** (Many2one) → hr.work.location


  - **work_location_name** (Char) → Work Location Name


  - **work_location_type** (Selection)


  - **user_id** (Many2one) → res.users


  - **share** (Boolean)


  - **resource_id** (Many2one) → resource.resource


  - **resource_calendar_id** (Many2one) → resource.calendar


  - **is_flexible** (Boolean)


  - **is_fully_flexible** (Boolean)


  - **parent_id** (Many2one) → hr.employee


  - **coach_id** (Many2one) → hr.employee


  - **tz** (Selection)


  - **hr_presence_state** (Selection)


  - **last_activity** (Date)


  - **last_activity_time** (Char)


  - **hr_icon_display** (Selection)


  - **show_hr_icon_display** (Boolean)


  - **im_status** (Char)


  - **newly_hired** (Boolean) → Newly Hired





### mail.alias


- Hereda de:

  - mail.alias




- Campos:

  - **alias_contact** (Selection)





### hr.employee.public


- Hereda de:


  - hr.employee.base





- Campos:

  - **create_date** (Datetime)


  - **name** (Char)


  - **active** (Boolean)


  - **department_id** (Many2one)


  - **job_id** (Many2one)


  - **job_title** (Char)


  - **company_id** (Many2one)


  - **address_id** (Many2one)


  - **mobile_phone** (Char)


  - **work_phone** (Char)


  - **work_email** (Char)


  - **work_contact_id** (Many2one)


  - **work_location_id** (Many2one)


  - **user_id** (Many2one)


  - **resource_id** (Many2one)


  - **tz** (Selection)


  - **color** (Integer)


  - **is_manager** (Boolean)


  - **employee_id** (Many2one) → hr.employee


  - **child_ids** (One2many) → hr.employee.public


  - **image_1920** (Image) → Image


  - **image_1024** (Image) → Image 1024


  - **image_512** (Image) → Image 512


  - **image_256** (Image) → Image 256


  - **image_128** (Image) → Image 128


  - **avatar_1920** (Image) → Avatar


  - **avatar_1024** (Image) → Avatar 1024


  - **avatar_512** (Image) → Avatar 512


  - **avatar_256** (Image) → Avatar 256


  - **avatar_128** (Image) → Avatar 128


  - **parent_id** (Many2one) → hr.employee.public


  - **coach_id** (Many2one) → hr.employee.public


  - **user_partner_id** (Many2one)





### ['res.partner']


- Hereda de:


  - res.partner





- Campos:

  - **employee_ids** (One2many) → hr.employee


  - **employees_count** (Integer)





### ['res.partner.bank']


- Hereda de:


  - res.partner.bank





- No agrega campos



### base


- Hereda de:

  - base




- No agrega campos






## Vistas


### hr.employee

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| search | hr.employee.search | `hr.view_employee_filter` | - |
| form | hr.employee.form | `hr.view_employee_form` | - |
| graph | hr.employee.view.graph | `hr.hr_employee_view_graph` | - |
| pivot | hr.employee.view.pivot | `hr.hr_employee_view_pivot` | - |
| list | hr.employee.list | `hr.view_employee_tree` | - |
| kanban | hr.employee.kanban | `hr.hr_kanban_view_employees` | - |
| activity | hr.employee.activity | `hr.hr_employee_view_activity` | - |



#### Filtros de búsqueda (hr.view_employee_filter)

**Filtros:**
- **Unread Messages** (`[('message_needaction', '=', True)]`)
- **Late Activities** (`[('my_activity_date_deadline', '<', context_today().strftime('%Y-%m-%d'))]`)
- **Today Activities** (`[('my_activity_date_deadline', '=', context_today().strftime('%Y-%m-%d'))]`)
- **Future Activities** (`[('my_activity_date_deadline', '>', context_today().strftime('%Y-%m-%d'))]`)
- **My Team** (`[('parent_id.user_id', '=', uid)]`)
- **My Department** (`[('member_of_department', '=', True)]`)
- **Newly Hired** (`[('newly_hired', '=', True)]`)
- **Archived** (`[('active', '=', False)]`)


**Agrupar por:**
- Manager
- Department
- Job Position
- Start Date
- Tags


#### Botones (hr.view_employee_form)
- **Launch Plan** (action) - Grupos: `hr.group_hr_user`
- **Create User** (object)
- **Generate** (object)
- **Print Badge** (action)


### hr.work.location

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | hr.work.location.view.list | `hr.hr_work_location_tree_view` | - |
| form | hr.work.location.view.form | `hr.hr_work_location_form_view` | - |



### hr.contract.type

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | - | `hr.hr_contract_type_view_tree` | - |
| form | - | `hr.hr_contract_type_view_form` | - |



### res.users

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | res.users.preferences.form.inherit | `hr.res_users_view_form_profile` | res_users_view_form_simple_modif |



### hr.job

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | hr.job.form | `hr.view_hr_job_form` | - |
| list | hr.job.list | `hr.view_hr_job_tree` | - |
| kanban | hr.job.kanban | `hr.hr_job_view_kanban` | - |
| search | hr.job.search | `hr.view_job_filter` | - |



#### Filtros de búsqueda (hr.view_job_filter)

**Filtros:**
- **Unread Messages** (`[('message_needaction', '=', True)]`)
- **Archived** (`[('active', '=', False)]`)


**Agrupar por:**
- Department
- Company
- Employment Type


### hr.employee.public

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| search | hr.employee.search | `hr.hr_employee_public_view_search` | - |
| form | hr.employee.public.form | `hr.hr_employee_public_view_form` | - |
| list | hr.employee.list | `hr.hr_employee_public_view_tree` | - |
| kanban | hr.employee.kanban | `hr.hr_employee_public_view_kanban` | - |



#### Filtros de búsqueda (hr.hr_employee_public_view_search)

**Filtros:**
- **My Team** (`[('parent_id.user_id', '=', uid)]`)
- **My Department** (`[('member_of_department', '=', True)]`)
- **Newly Hired** (`[('newly_hired', '=', True)]`)
- **Archived** (`[('active', '=', False)]`)


**Agrupar por:**
- Manager
- Department
- Company


### hr.departure.reason

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | - | `hr.hr_departure_reason_view_list` | - |
| form | - | `hr.hr_departure_reason_view_form` | - |



### hr.department

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | hr.department.form | `hr.view_department_form` | - |
| list | hr.department.list | `hr.view_department_tree` | - |
| search | hr.department.search | `hr.view_department_filter` | - |
| kanban | hr.department.kanban | `hr.hr_department_view_kanban` | - |



#### Botones (hr.view_department_form)
- **action_employee_from_department** (object)
- **action_plan_from_department** (object)


#### Filtros de búsqueda (hr.view_department_filter)

**Filtros:**
- **Unread Messages** (`[('message_needaction','=',True)]`)
- **Archived** (`[('active','=',False)]`)


### hr.employee.category

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | hr.employee.category.form | `hr.view_employee_category_form` | - |
| list | hr.employee.category.list | `hr.view_employee_category_list` | - |



### hr.departure.wizard

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | hr.departure.wizard.view.form | `hr.hr_departure_wizard_view_form` | - |



#### Botones (hr.hr_departure_wizard_view_form)
- **Apply** (object)

