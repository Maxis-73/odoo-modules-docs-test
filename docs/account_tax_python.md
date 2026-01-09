# Módulo: Define Taxes as Python Code

## Información General
- **Nombre técnico:** account_tax_python
- **Versión:** 1.0
- **Categoría:** Accounting/Accounting
- **Dependencias:** account


## Propósito
Use python code to define taxes



## Descripción

A tax defined as python code consists of two snippets of python code which are executed in a local environment containing data such as the unit price, product or partner.

"Applicable Code" defines if the tax is to be applied.

"Python Code" defines the amount of the tax.
        



## Modelos

### account.tax


- Hereda de:

  - account.tax




- Campos:

  - **amount_type** (Selection)


  - **formula** (Text)


  - **formula_decoded_info** (Json)







