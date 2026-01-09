# Módulo: Quizzes on Tracks

## Información General
- **Nombre técnico:** website_event_track_quiz
- **Versión:** 1.0
- **Categoría:** Marketing/Events
- **Dependencias:** website_profile, website_event_track


## Propósito
Quizzes on tracks





## Modelos

### event.quiz


- Hereda de: Base



- Campos:

  - **name** (Char) → Name


  - **question_ids** (One2many) → event.quiz.question


  - **event_track_id** (Many2one) → event.track


  - **event_id** (Many2one) → event.event


  - **repeatable** (Boolean) → Unlimited Tries





### event.quiz.question


- Hereda de: Base



- Campos:

  - **name** (Char) → Question


  - **sequence** (Integer) → Sequence


  - **quiz_id** (Many2one) → event.quiz


  - **correct_answer_id** (One2many) → event.quiz.answer


  - **awarded_points** (Integer) → Number of Points


  - **answer_ids** (One2many) → event.quiz.answer





### event.quiz.answer


- Hereda de: Base



- Campos:

  - **sequence** (Integer) → Sequence


  - **question_id** (Many2one) → event.quiz.question


  - **text_value** (Char) → Answer


  - **is_correct** (Boolean) → Correct


  - **comment** (Text) → Extra Comment


  - **awarded_points** (Integer) → Points





### event.track.visitor


- Hereda de:


  - event.track.visitor





- Campos:

  - **quiz_completed** (Boolean) → Completed


  - **quiz_points** (Integer) → Quiz Points





### ['event.track']


- Hereda de:


  - event.track





- Campos:

  - **quiz_id** (Many2one) → event.quiz


  - **quiz_ids** (One2many) → event.quiz


  - **quiz_questions_count** (Integer)


  - **is_quiz_completed** (Boolean) → Is Quiz Done


  - **quiz_points** (Integer) → Quiz Points





### event.event


- Hereda de:

  - event.event




- No agrega campos






## Vistas


### event.quiz.question

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| search | event.quiz.question.view.search | `website_event_track_quiz.event_quiz_question_view_search` | - |
| list | event.quiz.question.view.list | `website_event_track_quiz.event_quiz_question_view_tree` | - |
| form | event.quiz.question.view.form | `website_event_track_quiz.event_quiz_question_view_form` | - |



#### Filtros de búsqueda (website_event_track_quiz.event_quiz_question_view_search)


**Agrupar por:**
- Quiz


### event.quiz

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| search | event.quiz.view.search | `website_event_track_quiz.event_quiz_view_search` | - |
| list | event.quiz.view.list | `website_event_track_quiz.event_quiz_view_tree` | - |
| form | event.quiz.view.form | `website_event_track_quiz.event_quiz_view_form` | - |



#### Filtros de búsqueda (website_event_track_quiz.event_quiz_view_search)


**Agrupar por:**
- Track
- Event

