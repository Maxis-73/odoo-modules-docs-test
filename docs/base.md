---
sidebar_position: 2
---

# Módulo: Base

## Información General
- **Nombre técnico:** base
- **Versión:** 1.3
- **Categoría:** Hidden
- **Dependencias:** 




## Descripción

The kernel of Odoo, needed for all installation.




## Modelos

### res.config


- Hereda de: Base



- No agrega campos



### res.config.settings


- Hereda de: Base



- No agrega campos



### ir.mail_server


- Hereda de: Base



- Campos:

  - **name** (Char)


  - **from_filter** (Char) → FROM Filtering


  - **smtp_host** (Char)


  - **smtp_port** (Integer)


  - **smtp_authentication** (Selection)


  - **smtp_authentication_info** (Text) → Authentication Info


  - **smtp_user** (Char)


  - **smtp_pass** (Char)


  - **smtp_encryption** (Selection)


  - **smtp_ssl_certificate** (Binary) → SSL Certificate


  - **smtp_ssl_private_key** (Binary) → SSL Private Key


  - **smtp_debug** (Boolean)


  - **max_email_size** (Float)


  - **sequence** (Integer)


  - **active** (Boolean)





### res.lang


- Hereda de: Base



- Campos:

  - **name** (Char)


  - **code** (Char)


  - **iso_code** (Char)


  - **url_code** (Char) → URL Code


  - **active** (Boolean)


  - **direction** (Selection)


  - **date_format** (Char)


  - **time_format** (Char)


  - **short_time_format** (Char)


  - **week_start** (Selection)


  - **grouping** (Char)


  - **decimal_point** (Char)


  - **thousands_sep** (Char)


  - **flag_image** (Image) → Image


  - **flag_image_url** (Char)





### res.currency


- Hereda de: Base



- Campos:

  - **name** (Char)


  - **iso_numeric** (Integer)


  - **full_name** (Char)


  - **symbol** (Char)


  - **rate** (Float)


  - **inverse_rate** (Float)


  - **rate_string** (Char)


  - **rate_ids** (One2many) → res.currency.rate


  - **rounding** (Float)


  - **decimal_places** (Integer)


  - **active** (Boolean)


  - **position** (Selection)


  - **date** (Date)


  - **currency_unit_label** (Char)


  - **currency_subunit_label** (Char)


  - **is_current_company_currency** (Boolean)





### res.currency.rate


- Hereda de: Base



- Campos:

  - **name** (Date)


  - **rate** (Float)


  - **company_rate** (Float)


  - **inverse_company_rate** (Float)


  - **currency_id** (Many2one) → res.currency


  - **company_id** (Many2one) → res.company





### ir.default


- Hereda de: Base



- Campos:

  - **field_id** (Many2one) → ir.model.fields


  - **user_id** (Many2one) → res.users


  - **company_id** (Many2one) → res.company


  - **condition** (Char) → Condition


  - **json_value** (Char) → Default Value (JSON format)





### res.country


- Hereda de: Base



- Campos:

  - **name** (Char)


  - **code** (Char)


  - **address_format** (Text)


  - **address_view_id** (Many2one) → ir.ui.view


  - **currency_id** (Many2one) → res.currency


  - **image_url** (Char)


  - **phone_code** (Integer)


  - **country_group_ids** (Many2many) → res.country.group


  - **state_ids** (One2many) → res.country.state


  - **name_position** (Selection)


  - **vat_label** (Char)


  - **state_required** (Boolean)


  - **zip_required** (Boolean)





### res.country.group


- Hereda de: Base



- Campos:

  - **name** (Char)


  - **country_ids** (Many2many) → res.country





### res.country.state


- Hereda de: Base



- Campos:

  - **country_id** (Many2one) → res.country


  - **name** (Char)


  - **code** (Char)





### ir.module.category


- Hereda de: Base



- Campos:

  - **name** (Char)


  - **parent_id** (Many2one) → ir.module.category


  - **child_ids** (One2many) → ir.module.category


  - **module_ids** (One2many) → ir.module.module


  - **description** (Text)


  - **sequence** (Integer)


  - **visible** (Boolean)


  - **exclusive** (Boolean)


  - **xml_id** (Char)





### ir.module.module


- Hereda de: Base



- Campos:

  - **name** (Char) → Technical Name


  - **category_id** (Many2one) → ir.module.category


  - **shortdesc** (Char) → Module Name


  - **summary** (Char) → Summary


  - **description** (Text) → Description


  - **description_html** (Html) → Description HTML


  - **author** (Char) → Author


  - **maintainer** (Char) → Maintainer


  - **contributors** (Text) → Contributors


  - **website** (Char) → Website


  - **installed_version** (Char) → Latest Version


  - **latest_version** (Char) → Installed Version


  - **published_version** (Char) → Published Version


  - **url** (Char) → URL


  - **sequence** (Integer) → Sequence


  - **dependencies_id** (One2many) → ir.module.module.dependency


  - **country_ids** (Many2many) → res.country


  - **exclusion_ids** (One2many) → ir.module.module.exclusion


  - **auto_install** (Boolean) → Automatic Installation


  - **state** (Selection)


  - **demo** (Boolean) → Demo Data


  - **license** (Selection)


  - **menus_by_module** (Text)


  - **reports_by_module** (Text)


  - **views_by_module** (Text)


  - **application** (Boolean) → Application


  - **icon** (Char) → Icon URL


  - **icon_image** (Binary)


  - **icon_flag** (Char)


  - **to_buy** (Boolean) → Odoo Enterprise Module


  - **has_iap** (Boolean)





### ir.module.module.dependency


- Hereda de: Base



- Campos:

  - **name** (Char)


  - **module_id** (Many2one) → ir.module.module


  - **depend_id** (Many2one) → ir.module.module


  - **state** (Selection)


  - **auto_install_required** (Boolean)





### ir.module.module.exclusion


- Hereda de: Base



- Campos:

  - **name** (Char)


  - **module_id** (Many2one) → ir.module.module


  - **exclusion_id** (Many2one) → ir.module.module


  - **state** (Selection)





### ir.ui.view.custom


- Hereda de: Base



- Campos:

  - **ref_id** (Many2one) → ir.ui.view


  - **user_id** (Many2one) → res.users


  - **arch** (Text)





### ir.ui.view


- Hereda de: Base



- Campos:

  - **name** (Char)


  - **model** (Char)


  - **key** (Char)


  - **priority** (Integer)


  - **type** (Selection)


  - **arch** (Text)


  - **arch_base** (Text)


  - **arch_db** (Text)


  - **arch_fs** (Char)


  - **arch_updated** (Boolean)


  - **arch_prev** (Text)


  - **inherit_id** (Many2one) → ir.ui.view


  - **inherit_children_ids** (One2many) → ir.ui.view


  - **model_data_id** (Many2one) → ir.model.data


  - **xml_id** (Char)


  - **groups_id** (Many2many) → res.groups


  - **mode** (Selection)


  - **warning_info** (Html)


  - **active** (Boolean)


  - **model_id** (Many2one) → ir.model





### reset.view.arch.wizard


- Hereda de: Base



- Campos:

  - **view_id** (Many2one) → ir.ui.view


  - **view_name** (Char)


  - **has_diff** (Boolean)


  - **arch_diff** (Html)


  - **reset_mode** (Selection)


  - **compare_view_id** (Many2one) → ir.ui.view


  - **arch_to_compare** (Text) → Arch To Compare To





### base


- Hereda de:

  - base




- No agrega campos



### ir.embedded.actions


- Hereda de: Base



- Campos:

  - **name** (Char)


  - **sequence** (Integer)


  - **parent_action_id** (Many2one) → ir.actions.act_window


  - **parent_res_id** (Integer)


  - **parent_res_model** (Char)


  - **action_id** (Many2one) → ir.actions.actions


  - **python_method** (Char)


  - **user_id** (Many2one) → res.users


  - **is_deletable** (Boolean)


  - **default_view_mode** (Char)


  - **filter_ids** (One2many) → ir.filters


  - **is_visible** (Boolean)


  - **domain** (Char)


  - **context** (Char)


  - **groups_ids** (Many2many) → res.groups





### report.layout


- Hereda de: Base



- Campos:

  - **view_id** (Many2one) → ir.ui.view


  - **image** (Char)


  - **pdf** (Char)


  - **sequence** (Integer)


  - **name** (Char)





### avatar.mixin


- Hereda de:


  - image.mixin





- Campos:

  - **avatar_1920** (Image) → Avatar


  - **avatar_1024** (Image) → Avatar 1024


  - **avatar_512** (Image) → Avatar 512


  - **avatar_256** (Image) → Avatar 256


  - **avatar_128** (Image) → Avatar 128





### ir.autovacuum


- Hereda de: Base



- No agrega campos



### ir.demo_failure


- Hereda de: Base



- Campos:

  - **module_id** (Many2one) → ir.module.module


  - **error** (Char)


  - **wizard_id** (Many2one) → ir.demo_failure.wizard





### ir.demo_failure.wizard


- Hereda de: Base



- Campos:

  - **failure_ids** (One2many) → ir.demo_failure


  - **failures_count** (Integer)





### ir.filters


- Hereda de: Base



- Campos:

  - **name** (Char)


  - **user_id** (Many2one) → res.users


  - **domain** (Text)


  - **context** (Text)


  - **sort** (Char)


  - **model_id** (Selection)


  - **is_default** (Boolean)


  - **action_id** (Many2one) → ir.actions.actions


  - **embedded_action_id** (Many2one) → ir.embedded.actions


  - **embedded_parent_res_id** (Integer)


  - **active** (Boolean)





### ir.rule


- Hereda de: Base



- Campos:

  - **name** (Char)


  - **active** (Boolean)


  - **model_id** (Many2one) → ir.model


  - **groups** (Many2many) → res.groups


  - **domain_force** (Text)


  - **perm_read** (Boolean)


  - **perm_write** (Boolean)


  - **perm_create** (Boolean)


  - **perm_unlink** (Boolean)





### ir.actions.actions


- Hereda de: Base



- Campos:

  - **name** (Char)


  - **type** (Char)


  - **xml_id** (Char)


  - **path** (Char)


  - **help** (Html)


  - **binding_model_id** (Many2one) → ir.model


  - **binding_type** (Selection)


  - **binding_view_types** (Char)





### ir.actions.act_window


- Hereda de:

  - ir.actions.actions




- Campos:

  - **type** (Char)


  - **view_id** (Many2one) → ir.ui.view


  - **domain** (Char)


  - **context** (Char)


  - **res_id** (Integer)


  - **res_model** (Char)


  - **target** (Selection)


  - **view_mode** (Char)


  - **mobile_view_mode** (Char)


  - **usage** (Char)


  - **view_ids** (One2many) → ir.actions.act_window.view


  - **views** (Binary)


  - **limit** (Integer)


  - **groups_id** (Many2many) → res.groups


  - **search_view_id** (Many2one) → ir.ui.view


  - **embedded_action_ids** (One2many) → ir.embedded.actions


  - **filter** (Boolean)





### ir.actions.act_window.view


- Hereda de: Base



- Campos:

  - **sequence** (Integer)


  - **view_id** (Many2one) → ir.ui.view


  - **view_mode** (Selection)


  - **act_window_id** (Many2one) → ir.actions.act_window


  - **multi** (Boolean)





### ir.actions.act_window_close


- Hereda de:

  - ir.actions.actions




- Campos:

  - **type** (Char)





### ir.actions.act_url


- Hereda de:

  - ir.actions.actions




- Campos:

  - **type** (Char)


  - **url** (Text)


  - **target** (Selection)





### ir.actions.server


- Hereda de:

  - ir.actions.actions




- Campos:

  - **name** (Char)


  - **type** (Char)


  - **usage** (Selection)


  - **state** (Selection)


  - **sequence** (Integer)


  - **model_id** (Many2one) → ir.model


  - **available_model_ids** (Many2many) → ir.model


  - **model_name** (Char)


  - **code** (Text)


  - **child_ids** (Many2many) → ir.actions.server


  - **crud_model_id** (Many2one) → ir.model


  - **crud_model_name** (Char)


  - **link_field_id** (Many2one) → ir.model.fields


  - **groups_id** (Many2many) → res.groups


  - **update_field_id** (Many2one) → ir.model.fields


  - **update_path** (Char)


  - **update_related_model_id** (Many2one) → ir.model


  - **update_field_type** (Selection)


  - **update_m2m_operation** (Selection)


  - **update_boolean_value** (Selection)


  - **value** (Text)


  - **evaluation_type** (Selection)


  - **resource_ref** (Reference)


  - **selection_value** (Many2one) → ir.model.fields.selection


  - **value_field_to_show** (Selection)


  - **webhook_url** (Char)


  - **webhook_field_ids** (Many2many) → ir.model.fields


  - **webhook_sample_payload** (Text)





### ir.actions.todo


- Hereda de: Base



- Campos:

  - **action_id** (Many2one) → ir.actions.actions


  - **sequence** (Integer)


  - **state** (Selection)


  - **name** (Char)





### ir.actions.client


- Hereda de:

  - ir.actions.actions




- Campos:

  - **type** (Char)


  - **tag** (Char)


  - **target** (Selection)


  - **res_model** (Char)


  - **context** (Char)


  - **params** (Binary)


  - **params_store** (Binary)





### ir.sequence


- Hereda de: Base



- Campos:

  - **name** (Char)


  - **code** (Char)


  - **implementation** (Selection)


  - **active** (Boolean)


  - **prefix** (Char)


  - **suffix** (Char)


  - **number_next** (Integer)


  - **number_next_actual** (Integer)


  - **number_increment** (Integer)


  - **padding** (Integer)


  - **company_id** (Many2one) → res.company


  - **use_date_range** (Boolean)


  - **date_range_ids** (One2many) → ir.sequence.date_range





### ir.sequence.date_range


- Hereda de: Base



- Campos:

  - **date_from** (Date)


  - **date_to** (Date)


  - **sequence_id** (Many2one) → ir.sequence


  - **number_next** (Integer)


  - **number_next_actual** (Integer)





### res.device.log


- Hereda de: Base



- Campos:

  - **session_identifier** (Char) → Session Identifier


  - **platform** (Char) → Platform


  - **browser** (Char) → Browser


  - **ip_address** (Char) → IP Address


  - **country** (Char) → Country


  - **city** (Char) → City


  - **device_type** (Selection)


  - **user_id** (Many2one) → res.users


  - **first_activity** (Datetime) → First Activity


  - **last_activity** (Datetime) → Last Activity


  - **revoked** (Boolean) → Revoked


  - **is_current** (Boolean) → Current Device


  - **linked_ip_addresses** (Text) → Linked IP address





### res.device


- Hereda de:


  - res.device.log





- No agrega campos



### ir.binary


- Hereda de: Base



- No agrega campos



### ir.cron


- Hereda de: Base



- Campos:

  - **ir_actions_server_id** (Many2one) → ir.actions.server


  - **cron_name** (Char) → Name


  - **user_id** (Many2one) → res.users


  - **active** (Boolean)


  - **interval_number** (Integer)


  - **interval_type** (Selection)


  - **nextcall** (Datetime)


  - **lastcall** (Datetime)


  - **priority** (Integer)


  - **failure_count** (Integer)


  - **first_failure_date** (Datetime)





### ir.cron.trigger


- Hereda de: Base



- Campos:

  - **cron_id** (Many2one) → ir.cron


  - **call_at** (Datetime)





### ir.cron.progress


- Hereda de: Base



- Campos:

  - **cron_id** (Many2one) → ir.cron


  - **remaining** (Integer)


  - **done** (Integer)


  - **deactivate** (Boolean)


  - **timed_out_counter** (Integer)





### ir.logging


- Hereda de: Base



- Campos:

  - **create_uid** (Integer)


  - **create_date** (Datetime)


  - **write_uid** (Integer)


  - **write_date** (Datetime)


  - **name** (Char)


  - **type** (Selection)


  - **dbname** (Char)


  - **level** (Char)


  - **message** (Text)


  - **path** (Char)


  - **func** (Char)


  - **line** (Char)





### base


- Hereda de: Base



- No agrega campos



### _unknown


- Hereda de: Base



- No agrega campos



### ir.model


- Hereda de: Base



- Campos:

  - **name** (Char)


  - **model** (Char)


  - **order** (Char)


  - **info** (Text)


  - **field_id** (One2many) → ir.model.fields


  - **inherited_model_ids** (Many2many) → ir.model


  - **state** (Selection)


  - **access_ids** (One2many) → ir.model.access


  - **rule_ids** (One2many) → ir.rule


  - **transient** (Boolean)


  - **modules** (Char)


  - **view_ids** (One2many) → ir.ui.view


  - **count** (Integer)





### ir.model.fields


- Hereda de: Base



- Campos:

  - **name** (Char)


  - **complete_name** (Char)


  - **model** (Char)


  - **relation** (Char)


  - **relation_field** (Char)


  - **relation_field_id** (Many2one) → ir.model.fields


  - **model_id** (Many2one) → ir.model


  - **field_description** (Char)


  - **help** (Text)


  - **ttype** (Selection)


  - **selection** (Char)


  - **selection_ids** (One2many) → ir.model.fields.selection


  - **copied** (Boolean)


  - **related** (Char)


  - **related_field_id** (Many2one) → ir.model.fields


  - **required** (Boolean)


  - **readonly** (Boolean)


  - **index** (Boolean)


  - **translate** (Boolean)


  - **company_dependent** (Boolean)


  - **size** (Integer)


  - **state** (Selection)


  - **on_delete** (Selection)


  - **domain** (Char)


  - **groups** (Many2many) → res.groups


  - **group_expand** (Boolean)


  - **selectable** (Boolean)


  - **modules** (Char)


  - **relation_table** (Char)


  - **column1** (Char)


  - **column2** (Char)


  - **compute** (Text)


  - **depends** (Char)


  - **store** (Boolean)


  - **currency_field** (Char)


  - **sanitize** (Boolean)


  - **sanitize_overridable** (Boolean)


  - **sanitize_tags** (Boolean)


  - **sanitize_attributes** (Boolean)


  - **sanitize_style** (Boolean)


  - **sanitize_form** (Boolean)


  - **strip_style** (Boolean)


  - **strip_classes** (Boolean)





### ir.model.inherit


- Hereda de: Base



- Campos:

  - **model_id** (Many2one) → ir.model


  - **parent_id** (Many2one) → ir.model


  - **parent_field_id** (Many2one) → ir.model.fields





### ir.model.fields.selection


- Hereda de: Base



- Campos:

  - **field_id** (Many2one) → ir.model.fields


  - **value** (Char)


  - **name** (Char)


  - **sequence** (Integer)





### ir.model.constraint


- Hereda de: Base



- Campos:

  - **name** (Char)


  - **definition** (Char)


  - **message** (Char)


  - **model** (Many2one) → ir.model


  - **module** (Many2one) → ir.module.module


  - **type** (Char)


  - **write_date** (Datetime)


  - **create_date** (Datetime)





### ir.model.relation


- Hereda de: Base



- Campos:

  - **name** (Char)


  - **model** (Many2one) → ir.model


  - **module** (Many2one) → ir.module.module


  - **write_date** (Datetime)


  - **create_date** (Datetime)





### ir.model.access


- Hereda de: Base



- Campos:

  - **name** (Char)


  - **active** (Boolean)


  - **model_id** (Many2one) → ir.model


  - **group_id** (Many2one) → res.groups


  - **perm_read** (Boolean)


  - **perm_write** (Boolean)


  - **perm_create** (Boolean)


  - **perm_unlink** (Boolean)





### ir.model.data


- Hereda de: Base



- Campos:

  - **name** (Char)


  - **complete_name** (Char)


  - **model** (Char)


  - **module** (Char)


  - **res_id** (Many2oneReference)


  - **noupdate** (Boolean)


  - **reference** (Char)





### wizard.ir.model.menu.create


- Hereda de: Base



- Campos:

  - **menu_id** (Many2one) → ir.ui.menu


  - **name** (Char)





### ir.actions.report


- Hereda de:

  - ir.actions.actions




- Campos:

  - **type** (Char)


  - **binding_type** (Selection)


  - **model** (Char)


  - **model_id** (Many2one) → ir.model


  - **report_type** (Selection)


  - **report_name** (Char)


  - **report_file** (Char)


  - **groups_id** (Many2many) → res.groups


  - **multi** (Boolean)


  - **paperformat_id** (Many2one) → report.paperformat


  - **print_report_name** (Char) → Printed Report Name


  - **attachment_use** (Boolean)


  - **attachment** (Char)


  - **domain** (Char)





### image.mixin


- Hereda de: Base



- Campos:

  - **image_1920** (Image) → Image


  - **image_1024** (Image) → Image 1024


  - **image_512** (Image) → Image 512


  - **image_256** (Image) → Image 256


  - **image_128** (Image) → Image 128





### ir.fields.converter


- Hereda de: Base



- No agrega campos



### ir.asset


- Hereda de: Base



- Campos:

  - **name** (Char)


  - **bundle** (Char)


  - **directive** (Selection)


  - **path** (Char)


  - **target** (Char)


  - **active** (Boolean)


  - **sequence** (Integer)





### res.groups


- Hereda de: Base



- Campos:

  - **name** (Char)


  - **users** (Many2many) → res.users


  - **model_access** (One2many) → ir.model.access


  - **rule_groups** (Many2many) → ir.rule


  - **menu_access** (Many2many) → ir.ui.menu


  - **view_access** (Many2many) → ir.ui.view


  - **comment** (Text)


  - **category_id** (Many2one) → ir.module.category


  - **color** (Integer)


  - **full_name** (Char)


  - **share** (Boolean)


  - **api_key_duration** (Float)





### res.users.log


- Hereda de: Base



- No agrega campos



### res.users


- Hereda de: Base



- Campos:

  - **partner_id** (Many2one) → res.partner


  - **login** (Char)


  - **password** (Char)


  - **new_password** (Char)


  - **signature** (Html)


  - **active** (Boolean)


  - **active_partner** (Boolean)


  - **action_id** (Many2one) → ir.actions.actions


  - **groups_id** (Many2many) → res.groups


  - **log_ids** (One2many) → res.users.log


  - **device_ids** (One2many) → res.device


  - **login_date** (Datetime)


  - **share** (Boolean)


  - **companies_count** (Integer)


  - **tz_offset** (Char)


  - **res_users_settings_ids** (One2many) → res.users.settings


  - **res_users_settings_id** (Many2one) → res.users.settings


  - **company_id** (Many2one) → res.company


  - **company_ids** (Many2many) → res.company


  - **name** (Char)


  - **email** (Char)


  - **accesses_count** (Integer) → # Access Rights


  - **rules_count** (Integer) → # Record Rules


  - **groups_count** (Integer) → # Groups





### res.groups


- Hereda de:

  - res.groups




- Campos:

  - **implied_ids** (Many2many) → res.groups


  - **trans_implied_ids** (Many2many) → res.groups





### res.users


- Hereda de:

  - res.users




- No agrega campos



### res.groups


- Hereda de:

  - res.groups




- No agrega campos



### ir.module.category


- Hereda de:

  - ir.module.category




- No agrega campos



### res.users


- Hereda de:

  - res.users




- Campos:

  - **user_group_warning** (Text)





### res.users.identitycheck


- Hereda de: Base



- Campos:

  - **request** (Char)


  - **auth_method** (Selection)


  - **password** (Char)





### change.password.wizard


- Hereda de: Base



- Campos:

  - **user_ids** (One2many) → change.password.user





### change.password.user


- Hereda de: Base



- Campos:

  - **wizard_id** (Many2one) → change.password.wizard


  - **user_id** (Many2one) → res.users


  - **user_login** (Char)


  - **new_passwd** (Char)





### change.password.own


- Hereda de: Base



- Campos:

  - **new_password** (Char)


  - **confirm_password** (Char)





### res.users


- Hereda de:

  - res.users




- Campos:

  - **api_key_ids** (One2many) → res.users.apikeys





### res.users.apikeys


- Hereda de: Base



- Campos:

  - **name** (Char) → Description


  - **user_id** (Many2one) → res.users


  - **scope** (Char) → Scope


  - **create_date** (Datetime) → Creation Date


  - **expiration_date** (Datetime) → Expiration Date





### res.users.apikeys.description


- Hereda de: Base



- Campos:

  - **name** (Char) → Description


  - **duration** (Selection)


  - **expiration_date** (Datetime) → Expiration Date





### res.users.apikeys.show


- Hereda de: Base



- Campos:

  - **id** (Id)


  - **key** (Char)





### ir.demo


- Hereda de: Base



- No agrega campos



### ir.profile


- Hereda de: Base



- Campos:

  - **create_date** (Datetime) → Creation Date


  - **session** (Char) → Session


  - **name** (Char) → Description


  - **duration** (Float) → Duration


  - **init_stack_trace** (Text) → Initial stack trace


  - **sql** (Text) → Sql


  - **sql_count** (Integer) → Queries Count


  - **traces_async** (Text) → Traces Async


  - **traces_sync** (Text) → Traces Sync


  - **qweb** (Text) → Qweb


  - **entry_count** (Integer) → Entry count


  - **speedscope** (Binary) → Speedscope


  - **speedscope_url** (Text) → Open





### base.enable.profiling.wizard


- Hereda de: Base



- Campos:

  - **duration** (Selection)


  - **expiration** (Datetime) → Enable profiling until





### ir.attachment


- Hereda de: Base



- Campos:

  - **name** (Char) → Name


  - **description** (Text) → Description


  - **res_name** (Char) → Resource Name


  - **res_model** (Char) → Resource Model


  - **res_field** (Char) → Resource Field


  - **res_id** (Many2oneReference) → Resource ID


  - **company_id** (Many2one) → res.company


  - **type** (Selection)


  - **url** (Char) → Url


  - **public** (Boolean) → Is public document


  - **access_token** (Char) → Access Token


  - **raw** (Binary)


  - **datas** (Binary)


  - **db_datas** (Binary) → Database Data


  - **store_fname** (Char) → Stored Filename


  - **file_size** (Integer) → File Size


  - **checksum** (Char) → Checksum/SHA1


  - **mimetype** (Char) → Mime Type


  - **index_content** (Text) → Indexed Content





### ir.ui.menu


- Hereda de: Base



- Campos:

  - **name** (Char)


  - **active** (Boolean)


  - **sequence** (Integer)


  - **child_id** (One2many) → ir.ui.menu


  - **parent_id** (Many2one) → ir.ui.menu


  - **parent_path** (Char)


  - **groups_id** (Many2many) → res.groups


  - **complete_name** (Char)


  - **web_icon** (Char)


  - **action** (Reference)


  - **web_icon_data** (Binary)





### ir.exports


- Hereda de: Base



- Campos:

  - **name** (Char)


  - **resource** (Char)


  - **export_fields** (One2many) → ir.exports.line





### ir.exports.line


- Hereda de: Base



- Campos:

  - **name** (Char)


  - **export_id** (Many2one) → ir.exports





### res.bank


- Hereda de: Base



- Campos:

  - **name** (Char)


  - **street** (Char)


  - **street2** (Char)


  - **zip** (Char)


  - **city** (Char)


  - **state** (Many2one) → res.country.state


  - **country** (Many2one) → res.country


  - **country_code** (Char)


  - **email** (Char)


  - **phone** (Char)


  - **active** (Boolean)


  - **bic** (Char) → Bank Identifier Code





### res.partner.bank


- Hereda de: Base



- Campos:

  - **active** (Boolean)


  - **acc_type** (Selection)


  - **acc_number** (Char) → Account Number


  - **sanitized_acc_number** (Char)


  - **acc_holder_name** (Char)


  - **partner_id** (Many2one) → res.partner


  - **allow_out_payment** (Boolean) → Send Money


  - **bank_id** (Many2one) → res.bank


  - **bank_name** (Char)


  - **bank_bic** (Char)


  - **sequence** (Integer)


  - **currency_id** (Many2one) → res.currency


  - **company_id** (Many2one) → res.company


  - **country_code** (Char)





### ir.config_parameter


- Hereda de: Base



- Campos:

  - **key** (Char)


  - **value** (Text)





### res.company


- Hereda de:


  - format.address.mixin

  - format.vat.label.mixin





- Campos:

  - **name** (Char)


  - **active** (Boolean)


  - **sequence** (Integer)


  - **parent_id** (Many2one) → res.company


  - **child_ids** (One2many) → res.company


  - **all_child_ids** (One2many) → res.company


  - **parent_path** (Char)


  - **parent_ids** (Many2many) → res.company


  - **root_id** (Many2one) → res.company


  - **partner_id** (Many2one) → res.partner


  - **report_header** (Html)


  - **report_footer** (Html)


  - **company_details** (Html)


  - **is_company_details_empty** (Boolean)


  - **logo** (Binary)


  - **logo_web** (Binary)


  - **uses_default_logo** (Boolean)


  - **currency_id** (Many2one) → res.currency


  - **user_ids** (Many2many) → res.users


  - **street** (Char)


  - **street2** (Char)


  - **zip** (Char)


  - **city** (Char)


  - **state_id** (Many2one) → res.country.state


  - **bank_ids** (One2many)


  - **country_id** (Many2one) → res.country


  - **country_code** (Char)


  - **email** (Char)


  - **phone** (Char)


  - **mobile** (Char)


  - **website** (Char)


  - **vat** (Char)


  - **company_registry** (Char)


  - **paperformat_id** (Many2one) → report.paperformat


  - **external_report_layout_id** (Many2one) → ir.ui.view


  - **font** (Selection)


  - **primary_color** (Char)


  - **secondary_color** (Char)


  - **color** (Integer)


  - **layout_background** (Selection)


  - **layout_background_image** (Binary) → Background Image


  - **uninstalled_l10n_module_ids** (Many2many) → ir.module.module





### ir.http


- Hereda de: Base



- No agrega campos



### ir.qweb.field


- Hereda de: Base



- No agrega campos



### ir.qweb.field.integer


- Hereda de:

  - ir.qweb.field




- No agrega campos



### ir.qweb.field.float


- Hereda de:

  - ir.qweb.field




- No agrega campos



### ir.qweb.field.date


- Hereda de:

  - ir.qweb.field




- No agrega campos



### ir.qweb.field.datetime


- Hereda de:

  - ir.qweb.field




- No agrega campos



### ir.qweb.field.text


- Hereda de:

  - ir.qweb.field




- No agrega campos



### ir.qweb.field.selection


- Hereda de:

  - ir.qweb.field




- No agrega campos



### ir.qweb.field.many2one


- Hereda de:

  - ir.qweb.field




- No agrega campos



### ir.qweb.field.many2many


- Hereda de:

  - ir.qweb.field




- No agrega campos



### ir.qweb.field.one2many


- Hereda de:

  - ir.qweb.field




- No agrega campos



### ir.qweb.field.html


- Hereda de:

  - ir.qweb.field




- No agrega campos



### ir.qweb.field.image


- Hereda de:

  - ir.qweb.field




- No agrega campos



### ir.qweb.field.image_url


- Hereda de:

  - ir.qweb.field.image




- No agrega campos



### ir.qweb.field.monetary


- Hereda de:

  - ir.qweb.field




- No agrega campos



### ir.qweb.field.float_time


- Hereda de:

  - ir.qweb.field




- No agrega campos



### ir.qweb.field.time


- Hereda de:

  - ir.qweb.field




- No agrega campos



### ir.qweb.field.duration


- Hereda de:

  - ir.qweb.field




- No agrega campos



### ir.qweb.field.relative


- Hereda de:

  - ir.qweb.field




- No agrega campos



### ir.qweb.field.barcode


- Hereda de:

  - ir.qweb.field




- No agrega campos



### ir.qweb.field.contact


- Hereda de:

  - ir.qweb.field.many2one




- No agrega campos



### ir.qweb.field.qweb


- Hereda de:

  - ir.qweb.field.many2one




- No agrega campos



### res.users.deletion


- Hereda de: Base



- Campos:

  - **user_id** (Many2one) → res.users


  - **user_id_int** (Integer) → User Id


  - **state** (Selection)





### report.paperformat


- Hereda de: Base



- Campos:

  - **name** (Char) → Name


  - **default** (Boolean) → Default paper format?


  - **format** (Selection)


  - **margin_top** (Float) → Top Margin (mm)


  - **margin_bottom** (Float) → Bottom Margin (mm)


  - **margin_left** (Float) → Left Margin (mm)


  - **margin_right** (Float) → Right Margin (mm)


  - **page_height** (Integer) → Page height (mm)


  - **page_width** (Integer) → Page width (mm)


  - **orientation** (Selection)


  - **header_line** (Boolean) → Display a header line


  - **header_spacing** (Integer) → Header spacing


  - **disable_shrinking** (Boolean) → Disable smart shrinking


  - **dpi** (Integer) → Output DPI


  - **report_ids** (One2many) → ir.actions.report


  - **print_page_width** (Float) → Print page width (mm)


  - **print_page_height** (Float) → Print page height (mm)


  - **css_margins** (Boolean) → Use css margins





### ir.qweb


- Hereda de: Base



- No agrega campos



### format.vat.label.mixin


- Hereda de: Base



- No agrega campos



### format.address.mixin


- Hereda de: Base



- No agrega campos



### res.partner.category


- Hereda de: Base



- Campos:

  - **name** (Char) → Name


  - **color** (Integer)


  - **active** (Boolean)


  - **parent_path** (Char)





### res.partner.title


- Hereda de: Base



- Campos:

  - **name** (Char)


  - **shortcut** (Char)





### res.partner


- Hereda de:


  - format.address.mixin

  - format.vat.label.mixin

  - avatar.mixin





- Campos:

  - **name** (Char)


  - **complete_name** (Char)


  - **parent_name** (Char)


  - **ref** (Char)


  - **lang** (Selection)


  - **active_lang_count** (Integer)


  - **tz** (Selection)


  - **tz_offset** (Char)


  - **vat** (Char)


  - **vat_label** (Char)


  - **company_registry** (Char)


  - **company_registry_label** (Char)


  - **website** (Char) → Website Link


  - **comment** (Html)


  - **active** (Boolean)


  - **employee** (Boolean)


  - **function** (Char)


  - **type** (Selection)


  - **street** (Char)


  - **street2** (Char)


  - **zip** (Char)


  - **city** (Char)


  - **country_code** (Char)


  - **partner_latitude** (Float)


  - **partner_longitude** (Float)


  - **email** (Char)


  - **email_formatted** (Char) → Formatted Email


  - **phone** (Char)


  - **mobile** (Char)


  - **is_company** (Boolean)


  - **is_public** (Boolean)


  - **company_type** (Selection)


  - **color** (Integer)


  - **partner_share** (Boolean) → Share Partner


  - **contact_address** (Char)


  - **commercial_company_name** (Char) → Company Name Entity


  - **company_name** (Char) → Company Name


  - **barcode** (Char)





### res.partner.industry


- Hereda de: Base



- Campos:

  - **name** (Char) → Name


  - **full_name** (Char) → Full Name


  - **active** (Boolean) → Active





### decimal.precision


- Hereda de: Base



- Campos:

  - **name** (Char) → Usage


  - **digits** (Integer) → Digits





### res.users.settings


- Hereda de: Base



- Campos:

  - **user_id** (Many2one) → res.users








## Vistas


### res.config.settings

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | res.config.settings.view.form | `base.res_config_settings_view_form` | - |



### ir.sequence

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | - | `base.sequence_view` | - |
| list | - | `base.sequence_view_tree` | - |
| search | - | `base.view_sequence_search` | - |



#### Filtros de búsqueda (base.view_sequence_search)

**Filtros:**
- **Archived** (`[('active', '=', False)]`)


### ir.cron

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | - | `base.ir_cron_view_tree` | - |
| calendar | - | `base.ir_cron_view_calendar` | - |
| search | - | `base.ir_cron_view_search` | - |



#### Filtros de búsqueda (base.ir_cron_view_search)

**Filtros:**
- **All** (`['|', ('active', '=', False), ('active', '=', True)]`)
- **Archived** (`[('active', '=', False)]`)


**Agrupar por:**
- User
- Execution
- Model


### res.country

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | res.country.list | `base.view_country_tree` | - |
| form | res.country.form | `base.view_country_form` | - |
| search | res.country.search | `base.view_country_search` | - |



### res.country.group

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | res.country.group.list | `base.view_country_group_tree` | - |
| form | res.country.group.form | `base.view_country_group_form` | - |



### res.country.state

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | res.country.state.list | `base.view_country_state_tree` | - |
| form | res.country.state.form | `base.view_country_state_form` | - |
| search | res.country.state.search | `base.view_country_state_search` | - |



#### Filtros de búsqueda (base.view_country_state_search)


**Agrupar por:**
- Country


### ir.module.category

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | ir.module.category.form | `base.view_module_category_form` | - |



### ir.module.module

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| search | ir.module.module.list.select | `base.view_module_filter` | - |
| form | ir.module.module.form | `base.module_form` | - |
| list | ir.module.module.list | `base.module_tree` | - |
| kanban | Apps Kanban | `base.module_view_kanban` | - |



#### Filtros de búsqueda (base.view_module_filter)

**Filtros:**
- **Apps** (`[('application', '=', True)]`)
- **Extra** (`[('application', '=', False)]`)
- **Installed** (`[('state', 'in', ['installed', 'to upgrade', 'to remove'])]`)
- **Not Installed** (`[('state', 'in', ['uninstalled', 'uninstallable', 'to install'])]`)


**Agrupar por:**
- Author
- Category
- Status


#### Botones (base.module_form)
- **Activate** (object) - Grupos: `base.group_system`
- **Upgrade** (object) - Grupos: `base.group_system`
- **Uninstall** (object) - Grupos: `base.group_system`
- **Cancel Uninstall** (object) - Grupos: `base.group_system`
- **Cancel Upgrade** (object) - Grupos: `base.group_system`
- **Cancel Install** (object) - Grupos: `base.group_system`


### ir.ui.view

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | - | `base.view_view_form` | - |
| list | - | `base.view_view_tree` | - |
| search | - | `base.view_view_search` | - |



#### Filtros de búsqueda (base.view_view_search)

**Filtros:**
- **Form** (`[('type', '=','form')]`)
- **List** (`[('type', '=', 'list')]`)
- **Kanban** (`[('type', '=', 'kanban')]`)
- **Search** (`[('type', '=', 'search')]`)
- **QWeb** (`[('type', '=', 'qweb')]`)
- **Modified Architecture** (`[('arch_updated', '=',True)]`)
- **Active** (`[('active', '=',True)]`)
- **Inactive** (`[('active', '=',False)]`)


**Agrupar por:**
- Model
- Type
- Inherit


### reset.view.arch.wizard

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | Reset View Architecture | `base.reset_view_arch_wizard_view` | - |



#### Botones (base.reset_view_arch_wizard_view)
- **Reset View** (object)


### ir.ui.view.custom

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | - | `base.view_view_custom_form` | - |
| list | - | `base.view_view_custom_tree` | - |
| search | - | `base.view_view_custom_search` | - |



### res.currency.rate

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| search | res.currency.rate.search | `base.view_currency_rate_search` | - |
| list | res.currency.rate.list | `base.view_currency_rate_tree` | - |
| form | res.currency.rate.form | `base.view_currency_rate_form` | - |



### res.currency

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| search | res.currency.search | `base.view_currency_search` | - |
| list | res.currency.list | `base.view_currency_tree` | - |
| kanban | res.currency.kanban | `base.view_currency_kanban` | - |
| form | res.currency.form | `base.view_currency_form` | - |



#### Filtros de búsqueda (base.view_currency_search)

**Filtros:**
- **Active** (`[('active','=',True)]`)
- **Inactive** (`[('active','=',False)]`)


### res.lang

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | res.lang.list | `base.res_lang_tree` | - |
| form | res.lang.form | `base.res_lang_form` | - |
| search | res.lang.search | `base.res_lang_search` | - |



#### Botones (base.res_lang_form)
- **%(base.action_view_base_language_install)d** (action)


#### Filtros de búsqueda (base.res_lang_search)

**Filtros:**
- **Active** (`[('active', '=', True)]`)


### wizard.ir.model.menu.create

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | Create Menu | `base.view_model_menu_create` | - |



#### Botones (base.view_model_menu_create)
- **Create Menu** (object)


### ir.model

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | - | `base.view_model_form` | - |
| list | - | `base.view_model_tree` | - |
| search | - | `base.view_model_search` | - |



#### Botones (base.view_model_form)
- **Create a Menu** (action) - Grupos: `base.group_no_one`


#### Filtros de búsqueda (base.view_model_search)

**Filtros:**
- **Transient** (`[('transient', '=', True)]`)
- **Custom** (`[('state', '=', 'manual')]`)
- **Base** (`[('state', '=', 'base')]`)


### ir.model.fields

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | - | `base.view_model_fields_form` | - |
| list | - | `base.view_model_fields_tree` | - |
| search | - | `base.view_model_fields_search` | - |



#### Filtros de búsqueda (base.view_model_fields_search)

**Filtros:**
- **Required** (`[('required', '=', True)]`)
- **Readonly** (`[('readonly', '=', True)]`)
- **Custom** (`[('state', '=', 'manual')]`)
- **Base** (`[('state', '=', 'base')]`)
- **Translate** (`[('translate', '=', True)]`)


**Agrupar por:**
- Model
- Field Type


### ir.model.fields.selection

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | - | `base.view_model_fields_selection_form` | - |
| list | - | `base.view_model_fields_selection_tree` | - |
| search | - | `base.view_model_fields_selection_search` | - |



#### Filtros de búsqueda (base.view_model_fields_selection_search)


**Agrupar por:**
- Field


### ir.model.data

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | - | `base.view_model_data_form` | - |
| list | - | `base.view_model_data_list` | - |
| search | - | `base.view_model_data_search` | - |



#### Filtros de búsqueda (base.view_model_data_search)

**Filtros:**
- **Updatable** (`[('noupdate', '=', False)]`)


**Agrupar por:**
- Module
- Model


### ir.model.constraint

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | - | `base.view_model_constraint_form` | - |
| list | - | `base.view_model_constraint_list` | - |
| search | - | `base.view_model_constraint_search` | - |



#### Filtros de búsqueda (base.view_model_constraint_search)


**Agrupar por:**
- Module
- Model
- Constraint type


### ir.model.relation

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | - | `base.view_model_relation_form` | - |
| list | - | `base.view_model_relation_list` | - |



### ir.model.access

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | ir.model.access.view.list | `base.ir_access_view_tree` | - |
| list | ir.model.access.view.list.edition | `base.ir_access_view_tree_edition` | - |
| form | - | `base.ir_access_view_form` | - |
| search | - | `base.ir_access_view_search` | - |



#### Filtros de búsqueda (base.ir_access_view_search)

**Filtros:**
- **Global** (`[('group_id', '=', False)]`)
- **Full Access** (`[('perm_read', '=', True), ('perm_write', '=', True), ('perm_create', '=', True), ('perm_unlink', '=', True)]`)
- **Read Access** (`[('perm_read', '=', True)]`)
- **Write Access** (`[('perm_write', '=', True)]`)
- **Archived** (`[('active', '=', False)]`)


**Agrupar por:**
- Group
- Model


### ir.actions.actions

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | ir.actions.actions | `base.action_view` | - |
| list | ir.actions.actions.list | `base.action_view_tree` | - |
| search | ir.actions.actions.search | `base.action_view_search` | - |



#### Filtros de búsqueda (base.action_view_search)


**Agrupar por:**
- Action Type
- Binding Type
- Binding Model


### ir.actions.report

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | ir.actions.report | `base.act_report_xml_view` | - |
| list | ir.actions.report.list | `base.act_report_xml_view_tree` | - |
| search | ir.actions.report.search | `base.act_report_xml_search_view` | - |



#### Botones (base.act_report_xml_view)
- **create_action** (object)
- **unlink_action** (object)
- **associated_view** (object)


#### Filtros de búsqueda (base.act_report_xml_search_view)


**Agrupar por:**
- Report Type
- Report Model


### ir.actions.client

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | ir.actions.client.form | `base.view_client_action_form` | - |
| list | Client Actions | `base.view_client_action_tree` | - |



### ir.actions.act_window

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | ir.actions.windows.list | `base.view_window_action_tree` | - |
| form | ir.actions.windows.form | `base.view_window_action_form` | - |
| search | ir.actions.windows.search | `base.view_window_action_search` | - |



#### Filtros de búsqueda (base.view_window_action_search)


**Agrupar por:**
- Binding Model
- Target Window


### ir.actions.server

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | Server Action | `base.view_server_action_form` | - |
| list | Server Actions | `base.view_server_action_tree` | - |
| search | ir.actions.server.search | `base.view_server_action_search` | - |



#### Botones (base.view_server_action_form)
- **Create Contextual Action** (object)
- **Remove Contextual Action** (object)
- **Run** (object)


#### Filtros de búsqueda (base.view_server_action_search)


**Agrupar por:**
- Action Type
- Model
- Usage


### ir.embedded.actions

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | ir.embedded.actions.form | `base.embedded_action_form` | - |
| list | Embedded Actions | `base.embedded_action_tree` | - |



### ir.actions.todo

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | Config Wizard Steps | `base.ir_actions_todo_tree` | - |
| form | Config Wizard Steps | `base.config_wizard_step_view_form` | - |
| search | ir.actions.todo.select | `base.config_wizard_step_view_search` | - |



#### Botones (base.config_wizard_step_view_form)
- **Launch** (object)
- **Set as Todo** (object)


#### Filtros de búsqueda (base.config_wizard_step_view_search)

**Filtros:**
- **To Do** (`[('state','=','open')]`)


### change.password.own

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | Change Own Password | `base.change_password_own_form` | - |



#### Botones (base.change_password_own_form)
- **Change Password** (object)


### change.password.wizard

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | Change Password | `base.change_password_wizard_view` | - |



#### Botones (base.change_password_wizard_view)
- **Change Password** (object)


### change.password.user

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | Change Password Users | `base.change_password_wizard_user_tree_view` | - |



### res.groups

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| search | res.groups.search | `base.view_groups_search` | - |
| form | res.groups.form | `base.view_groups_form` | - |



#### Filtros de búsqueda (base.view_groups_search)

**Filtros:**
- **Internal Groups** (`[('share','=',False)]`)


### res.users

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | res.users.simplified.form | `base.view_users_simple_form` | - |
| form | res.users.form | `base.view_users_form` | - |
| list | res.users.list | `base.view_users_tree` | - |
| kanban | res.users.kanban | `base.view_res_users_kanban` | - |
| search | res.users.search | `base.view_users_search` | - |
| form | res.users.preferences.form | `base.view_users_form_simple_modif` | - |



#### Botones (base.view_users_form)
- **action_show_groups** (object) - Grupos: `base.group_no_one`
- **action_show_accesses** (object) - Grupos: `base.group_no_one`
- **action_show_rules** (object) - Grupos: `base.group_no_one`
- **%(base.action_view_base_language_install)d** (action)


#### Filtros de búsqueda (base.view_users_search)

**Filtros:**
- **Internal Users** (`[('share', '=', False)]`)
- **Portal Users** (`[('share', '=', True)]`)
- **Inactive Users** (`[('active','=',False)]`)


#### Botones (base.view_users_form_simple_modif)
- **%(base.action_view_base_language_install)d** (action) - Grupos: `base.group_system`
- **Change password** (object)
- **Log out from all devices** (object)
- **Delete API key.** (object)
- **New API Key** (object)
- **Save** (object)
- **Cancel**


### res.users.apikeys.description

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | API Key: description input form | `base.form_res_users_key_description` | - |



#### Botones (base.form_res_users_key_description)
- **Generate key** (object)


### res.users.apikeys.show

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | API Key: show | `base.form_res_users_key_show` | - |



### res.users.apikeys

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | API Keys Listing | `base.view_apikeys` | - |



### ir.default

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | ir.default form view | `base.ir_default_form_view` | - |
| list | ir.default list view | `base.ir_default_tree_view` | - |
| search | ir.default search view | `base.ir_default_search_view` | - |



#### Filtros de búsqueda (base.ir_default_search_view)


**Agrupar por:**
- User
- Company


### ir.profile

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| search | IR Profile Search | `base.ir_profile_view_search` | - |
| list | IR Profile List | `base.ir_profile_view_list` | - |
| form | IR Profile Form | `base.ir_profile_view_form` | - |



#### Filtros de búsqueda (base.ir_profile_view_search)


**Agrupar por:**
- Session


### base.enable.profiling.wizard

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | Enable profiling | `base.enable_profiling_wizard` | - |



#### Botones (base.enable_profiling_wizard)
- **Enable profiling** (object)


### res.company

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | res.company.form | `base.view_company_form` | - |
| list | res.company.list | `base.view_company_tree` | - |
| kanban | res.company.kanban | `base.view_res_company_kanban` | - |



#### Botones (base.view_company_form)
- **Branches** (object)


### ir.filters

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | - | `base.ir_filters_view_form` | - |
| list | - | `base.ir_filters_view_tree` | - |
| search | - | `base.ir_filters_view_search` | - |



#### Filtros de búsqueda (base.ir_filters_view_search)

**Filtros:**
- **User** (`[('user_id','!=',False)]`)
- **Shared** (`[('user_id','=',False)]`)
- **My filters** (`[('user_id','=',uid)]`)
- **Archived** (`[('active', '=', False)]`)


**Agrupar por:**
- User
- Model


### ir.mail_server

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | - | `base.ir_mail_server_form` | - |
| list | - | `base.ir_mail_server_list` | - |
| search | - | `base.view_ir_mail_server_search` | - |



#### Botones (base.ir_mail_server_form)
- **Test Connection** (object)
- **action_retrieve_max_email_size** (object)


#### Filtros de búsqueda (base.view_ir_mail_server_search)

**Filtros:**
- **Archived** (`[('active', '=', False)]`)


### ir.asset

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | - | `base.asset_view_form` | - |
| list | - | `base.asset_view_tree` | - |
| search | - | `base.asset_view_search` | - |



#### Filtros de búsqueda (base.asset_view_search)

**Filtros:**
- **Active** (`[('active', '=', True)]`)


### ir.cron.trigger

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | ir.cron.trigger.view.form | `base.ir_cron_trigger_view_form` | - |
| list | ir.cron.trigger.view.list | `base.ir_cron_trigger_view_tree` | - |
| search | ir.cron.trigger.view.search | `base.ir_cron_trigger_view_search` | - |



### res.config

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | res.config.view.base | `base.res_config_view_base` | - |



#### Botones (base.res_config_view_base)
- **Apply** (object)
- **Cancel** (object)


### res.bank

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | res.bank.form | `base.view_res_bank_form` | - |
| list | res.bank.list | `base.view_res_bank_tree` | - |
| search | res.bank.view.search | `base.res_bank_view_search` | - |



#### Filtros de búsqueda (base.res_bank_view_search)

**Filtros:**
- **Archived** (`[('active', '=', False)]`)


### res.partner.bank

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | res.partner.bank.form | `base.view_partner_bank_form` | - |
| list | res.partner.bank.list | `base.view_partner_bank_tree` | - |
| search | res.partner.bank.search | `base.view_partner_bank_search` | - |



#### Botones (base.view_partner_bank_form)
- **Archive** (object)


#### Filtros de búsqueda (base.view_partner_bank_search)

**Filtros:**
- **Archived** (`[('active','=',False)]`)


### ir.attachment

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | - | `base.view_attachment_form` | - |
| list | - | `base.view_attachment_tree` | - |
| search | - | `base.view_attachment_search` | - |



#### Filtros de búsqueda (base.view_attachment_search)

**Filtros:**
- **My Document(s)** (`[('create_uid','=',uid)]`)
- **URL** (`[('type', '=', 'url')]`)
- **Stored** (`[('type', '=', 'binary')]`)


**Agrupar por:**
- Owner
- Type
- Company
- Creation Date


### ir.logging

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | - | `base.ir_logging_form_view` | - |
| list | - | `base.ir_logging_tree_view` | - |
| search | - | `base.ir_logging_search_view` | - |



#### Filtros de búsqueda (base.ir_logging_search_view)


**Agrupar por:**
- Database
- Level
- Type
- Creation Date


### res.partner.title

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | res.partner.title.list | `base.view_partner_title_tree` | - |
| form | res.partner.title.form | `base.view_partner_title_form` | - |



### res.partner

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | res.partner.list | `base.view_partner_tree` | - |
| form | res.partner.simplified.form | `base.view_partner_simple_form` | - |
| form | res.partner.form.address | `base.view_partner_address_form` | - |
| form | res.partner.form | `base.view_partner_form` | - |
| form | res.partner.view.form.private | `base.res_partner_view_form_private` | - |
| search | res.partner.select | `base.view_res_partner_filter` | - |
| kanban | res.partner.kanban | `base.res_partner_kanban_view` | - |



#### Botones (base.view_partner_form)
- **Create company** (object)


#### Filtros de búsqueda (base.view_res_partner_filter)

**Filtros:**
- **Individuals** (`[('is_company', '=', False)]`)
- **Companies** (`[('is_company', '=', True)]`)
- **Archived** (`[('active', '=', False)]`)


**Agrupar por:**
- Salesperson
- Company
- Country


### res.partner.category

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | Contact Tags | `base.view_partner_category_form` | - |
| list | Contact Tags | `base.view_partner_category_list` | - |
| search | res.partner.category.view.search | `base.res_partner_category_view_search` | - |



#### Filtros de búsqueda (base.res_partner_category_view_search)

**Filtros:**
- **Archived** (`[('active', '=', False)]`)


**Agrupar por:**
- Category
- Color


### res.partner.industry

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | Industry | `base.res_partner_industry_view_form` | - |
| list | Industry | `base.res_partner_industry_view_tree` | - |
| search | res.partner.industry.view.search | `base.res_partner_industry_view_search` | - |



#### Filtros de búsqueda (base.res_partner_industry_view_search)

**Filtros:**
- **Archived** (`[('active', '=', False)]`)


### res.device

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | res.device.form | `base.res_device_view_form` | - |
| list | res.device.list | `base.res_device_view_tree` | - |
| kanban | res.device.kanban | `base.res_device_view_kanban` | - |



### ir.config_parameter

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| search | - | `base.view_ir_config_search` | - |
| list | - | `base.view_ir_config_list` | - |
| form | - | `base.view_ir_config_form` | - |



### ir.rule

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | - | `base.view_rule_form` | - |
| list | - | `base.view_rule_tree` | - |
| search | - | `base.view_rule_search` | - |



#### Filtros de búsqueda (base.view_rule_search)

**Filtros:**
- **Global** (`[('global', '=', True)]`)
- **Group-based** (`[('global', '=', False)]`)
- **Full Access** (`[('perm_read', '=', True), ('perm_write', '=', True), ('perm_create', '=', True), ('perm_unlink', '=', True)]`)
- **Read** (`[('perm_read', '=', True)]`)
- **Write** (`[('perm_write', '=', True)]`)
- **Create** (`[('perm_create', '=' ,True)]`)
- **Delete** (`[('perm_unlink', '=', True)]`)
- **Archived** (`[('active', '=', False)]`)


**Agrupar por:**
- Model
- Group


### res.users.identitycheck

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | - | `base.res_users_identitycheck_view_form` | - |



#### Botones (base.res_users_identitycheck_view_form)
- **Confirm Password** (object)


### decimal.precision

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | Decimal Precision | `base.view_decimal_precision_form` | - |
| list | Decimal Precision List | `base.view_decimal_precision_tree` | - |



### report.paperformat

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | paper_format_view_tree | `base.paperformat_view_tree` | - |
| form | paper_format_view_form | `base.paperformat_view_form` | - |



### ir.ui.menu

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | - | `base.edit_menu_access` | - |
| list | - | `base.edit_menu` | - |
| search | ir.ui.menu.search | `base.edit_menu_access_search` | - |



#### Filtros de búsqueda (base.edit_menu_access_search)

**Filtros:**
- **Archived** (`[('active', '=', False)]`)


### base.partner.merge.automatic.wizard

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | base.partner.merge.automatic.wizard.form | `base.base_partner_merge_automatic_wizard_form` | - |



#### Botones (base.base_partner_merge_automatic_wizard_form)
- **Deduplicate the other Contacts** (action)
- **Merge Contacts** (object)
- **Skip these contacts** (object)
- **Merge with Manual Check** (object)
- **Merge Automatically** (object)
- **Merge Automatically all process** (object)


### base.module.update

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | Module Update | `base.view_base_module_update` | - |



#### Botones (base.view_base_module_update)
- **Update** (object)
- **Open Apps** (object)


### base.language.import

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | Import Translation | `base.view_base_import_language` | - |



#### Botones (base.view_base_import_language)
- **Import** (object)


### base.language.export

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | Export Translations | `base.wizard_lang_export` | - |



#### Botones (base.wizard_lang_export)
- **Export** (object)


### base.language.install

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | Switch to language | `base.language_install_view_form_lang_switch` | - |
| form | Load a Translation | `base.view_base_language_install` | - |



#### Botones (base.language_install_view_form_lang_switch)
- **Close** (object)
- **switch_lang** (object)


#### Botones (base.view_base_language_install)
- **Add** (object)


### base.module.upgrade

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | Module Upgrade | `base.view_base_module_upgrade` | - |
| form | Module Upgrade Install | `base.view_base_module_upgrade_install` | - |



#### Botones (base.view_base_module_upgrade)
- **Confirm** (object)
- **Cancel** (object)


#### Botones (base.view_base_module_upgrade_install)
- **Start configuration** (object)


### base.module.uninstall

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | Uninstall module | `base.view_base_module_uninstall` | - |



#### Botones (base.view_base_module_uninstall)
- **Uninstall** (object)

