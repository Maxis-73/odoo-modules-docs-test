# Módulo: To-Do

## Información General
- **Nombre técnico:** project_todo
- **Versión:** 1.0
- **Categoría:** Productivity/To-Do
- **Dependencias:** project


## Propósito
Organize your work with memos and to-do lists





## Modelos

### res.users


- Hereda de:

  - res.users




- No agrega campos



### project.task


- Hereda de:

  - project.task




- No agrega campos






## Vistas


### project.task

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| kanban | project.task.kanban | `project_todo.project_task_view_todo_kanban` | - |
| list | project.task.todo.list | `project_todo.project_task_view_todo_tree` | - |
| form | project.task.view.todo.form | `project_todo.project_task_view_todo_form` | - |
| form | project.task.view.todo.quick.create.todo | `project_todo.project_task_view_todo_quick_create_form` | - |
| form | project.task.view.todo.conversion.form | `project_todo.project_task_view_todo_conversion_form` | - |
| activity | project.task.view.todo.activity | `project_todo.project_task_view_todo_activity` | - |
| search | project.task.view.todo.search | `project_todo.project_task_view_todo_search` | - |



#### Botones (project_todo.project_task_view_todo_conversion_form)
- **Convert to Task** (object)


#### Filtros de búsqueda (project_todo.project_task_view_todo_search)

**Filtros:**
- **Starred** (`[('priority', '=', '1')]`)
- **Open** (`[('is_closed', '=', False)]`)
- **Closed** (`[('is_closed', '=', True)]`)
- **Closed On** (`[('is_closed', '=', True)]`)
- **Archived** (`[('active', '=', False)]`)
- **Late Activities** (`[('my_activity_date_deadline', '<', context_today().strftime('%Y-%m-%d'))]`)
- **Today Activities** (`[('my_activity_date_deadline', '=', context_today().strftime('%Y-%m-%d'))]`)
- **Future Activities** (`[('my_activity_date_deadline', '>', context_today().strftime('%Y-%m-%d'))]`)


**Agrupar por:**
- Tags
- Assignees
- Stage


### mail.activity.todo.create

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | mail.activity.todo.create.popup | `project_todo.mail_activity_todo_create_popup` | - |



#### Botones (project_todo.mail_activity_todo_create_popup)
- **create_todo_activity** (object)

