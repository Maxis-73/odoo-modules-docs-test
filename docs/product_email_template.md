# Módulo: Product Email Template

## Información General
- **Nombre técnico:** product_email_template
- **Versión:** N/A
- **Categoría:** Accounting/Accounting
- **Dependencias:** account




## Descripción

Add email templates to products to be sent on invoice confirmation

With this module, link your products to a template to send complete information and tools to your customer.
For instance when invoicing a training, the training agenda and materials will automatically be sent to your customers.'
    



## Modelos

### account.move


- Hereda de:

  - account.move




- No agrega campos



### product.template


- Hereda de:

  - product.template




- Campos:

  - **email_template_id** (Many2one) → mail.template








## Vistas


### mail.template

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | mail.template.form.simplified | `product_email_template.email_template_form_simplified` | - |


