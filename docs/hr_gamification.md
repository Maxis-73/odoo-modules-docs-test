# Módulo: HR Gamification

## Información General
- **Nombre técnico:** hr_gamification
- **Versión:** 1.0
- **Categoría:** Human Resources
- **Dependencias:** gamification, hr




## Descripción
Use the HR resources for the gamification process.

The HR officer can now manage challenges and badges.
This allow the user to send badges to employees instead of simple users.
Badge received are displayed on the user profile.




## Modelos

### gamification.badge.user


- Hereda de:

  - gamification.badge.user




#### Campos
- **employee_id** (Many2one) → hr.employee





### gamification.badge


- Hereda de:

  - gamification.badge




#### Campos
- **granted_employees_count** (Integer)





### hr.employee.base


- Hereda de:

  - hr.employee.base




#### Campos
- **goal_ids** (One2many) → gamification.goal
- **badge_ids** (One2many) → gamification.badge.user
- **has_badges** (Boolean)
- **direct_badge_ids** (One2many) → gamification.badge.user





### res.users


- Hereda de:

  - res.users




#### Campos
- **goal_ids** (One2many) → gamification.goal
- **badge_ids** (One2many) → gamification.badge.user










## Vistas Adicionales


### gamification.badge.user.wizard

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | gamification.badge.user.wizard.form | `hr_gamification.view_badge_wizard_reward` | - |



**Botones (hr_gamification.view_badge_wizard_reward):**
- **Reward Employee** (object)



