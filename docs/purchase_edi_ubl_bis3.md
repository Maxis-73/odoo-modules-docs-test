# Módulo: Import/Export electronic orders with UBL

## Información General
- **Nombre técnico:** purchase_edi_ubl_bis3
- **Versión:** 1.0
- **Categoría:** Inventory/Purchase
- **Dependencias:** purchase, account_edi_ubl_cii




## Descripción

Allows to export and import formats: UBL Bis 3.
When generating the PDF on the order, the PDF will be embedded inside the xml for all UBL formats. This allows the
receiver to retrieve the PDF with only the xml file.
    



## Modelos

### purchase.order


- Hereda de:

  - purchase.order




- No agrega campos




### purchase.edi.xml.ubl_bis3


- Hereda de:

  - account.edi.xml.ubl_bis3




- No agrega campos






