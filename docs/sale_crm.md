# Módulo: Opportunity to Quotation

## Información General
- **Nombre técnico:** sale_crm
- **Versión:** 1.0
- **Categoría:** Hidden
- **Dependencias:** sale, crm




## Descripción

This module adds a shortcut on one or several opportunity cases in the CRM.
===========================================================================

This shortcut allows you to generate a sales order based on the selected case.
If different cases are open (a list), it generates one sales order by case.
The case is then closed and linked to the generated sales order.

We suggest you to install this module, if you installed both the sale and the crm
modules.
    



## Modelos

### sale.order


- Hereda de:

  - sale.order




#### Campos
- **opportunity_id** (Many2one) → crm.lead





### res.users


- Hereda de:

  - res.users




#### Campos
- **target_sales_invoiced** (Integer) → Invoiced in Sales Orders Target





### crm.team


- Hereda de:

  - crm.team




- No agrega campos




### crm.lead


- Hereda de:

  - crm.lead




#### Campos
- **sale_amount_total** (Monetary)
- **quotation_count** (Integer)
- **sale_order_count** (Integer)
- **order_ids** (One2many) → sale.order










## Vistas Adicionales


### crm.quotation.partner

| Tipo | Nombre | ID XML | Hereda de |
|------|--------|--------|-----------|
| form | crm.quotation.partner.view.form | `sale_crm.crm_quotation_partner_view_form` | - |



**Botones (sale_crm.crm_quotation_partner_view_form):**
- **Confirm** (object)



