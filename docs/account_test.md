# Módulo: Accounting Consistency Tests

## Información General
- **Nombre técnico:** account_test
- **Versión:** 1.0
- **Categoría:** Accounting/Accounting
- **Dependencias:** account




## Descripción

Asserts on accounting.
======================
With this module you can manually check consistencies and inconsistencies of accounting module from menu Reporting/Accounting/Accounting Tests.

You can write a query in order to create Consistency Test and you will get the result of the test 
in PDF format which can be accessed by Menu Reporting -> Accounting Tests, then select the test 
and print the report from Print button in header area.




## Modelos

### accounting.assert.test


- Hereda de: Base



#### Campos
- **name** (Char)
- **desc** (Text)
- **code_exec** (Text)
- **active** (Boolean)
- **sequence** (Integer)





#### Vistas

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| list | accounting.assert.test.list | `account_test.account_assert_tree` | - |
| form | accounting.assert.test.form | `account_test.account_assert_form` | - |
| search | accounting.assert.test.view.search | `account_test.accounting_assert_test_view_search` | - |



**Filtros de búsqueda (account_test.accounting_assert_test_view_search):**

- **Archived** (`[('active', '=', False)]`)








