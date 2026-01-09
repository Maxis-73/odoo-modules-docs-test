# Módulo: Italy - Stock DDT

## Información General
- **Nombre técnico:** l10n_it_stock_ddt
- **Versión:** 0.1
- **Categoría:** Accounting/Localizations/EDI
- **Dependencias:** l10n_it_edi, stock_delivery, stock_account




## Descripción

Documento di Trasporto (DDT)

Whenever goods are transferred between A and B, the DDT serves
as a legitimation e.g. when the police would stop you.

When you want to print an outgoing picking in an Italian company,
it will print you the DDT instead.  It is like the delivery
slip, but it also contains the value of the product,
the transportation reason, the carrier, ... which make it a DDT.

We also use a separate sequence for the DDT as the number should not
have any gaps and should only be applied at the moment the goods are sent.

When invoices are related to their sale order and the sale order with the
delivery, the system will automatically calculate the linked DDTs for every
invoice line to export in the FatturaPA XML.
    



## Modelos

### account.move


- Hereda de:

  - account.move




- Campos:

  - **l10n_it_ddt_ids** (Many2many) → stock.picking


  - **l10n_it_ddt_count** (Integer)





### stock.picking


- Hereda de:

  - stock.picking




- Campos:

  - **l10n_it_transport_reason** (Selection)


  - **l10n_it_transport_method** (Selection)


  - **l10n_it_transport_method_details** (Char) → Transport Note


  - **l10n_it_parcels** (Integer)


  - **l10n_it_ddt_number** (Char) → DDT Number


  - **l10n_it_show_print_ddt_button** (Boolean)





### stock.picking.type


- Hereda de:

  - stock.picking.type




- Campos:

  - **l10n_it_ddt_sequence_id** (Many2one) → ir.sequence







