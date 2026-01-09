# Módulo: Import/Export electronic invoices with UBL/CII

## Información General
- **Nombre técnico:** account_edi_ubl_cii
- **Versión:** 1.0
- **Categoría:** Accounting/Accounting
- **Dependencias:** account




## Descripción

Electronic invoicing module
===========================

Allows to export and import formats: E-FFF, UBL Bis 3, EHF3, NLCIUS, Factur-X (CII), XRechnung (UBL).
When generating the PDF on the invoice, the PDF will be embedded inside the xml for all UBL formats. This allows the
receiver to retrieve the PDF with only the xml file. Note that **EHF3 is fully implemented by UBL Bis 3:** [Reference](https://anskaffelser.dev/postaward/g3/spec/current/billing-3.0/norway/#_implementation>).

The formats can be chosen from the journal (Journal > Advanced Settings) linked to the invoice.

Note that E-FFF, NLCIUS and XRechnung (UBL) are only available for Belgian, Dutch and German companies,
respectively. UBL Bis 3 is only available for companies which country is present in the [EAS list](https://docs.peppol.eu/poacc/billing/3.0/codelist/eas/>).

Note also that in order for Chorus Pro to automatically detect the "PDF/A-3 (Factur-X)" format, you need to activate
the "Factur-X PDF/A-3" option on the journal. This option will also validate the xml against the Factur-X and Chorus
Pro rules and show the errors.
    



## Modelos

### account.move.send


- Hereda de:

  - account.move.send




- No agrega campos




### account.edi.xml.ubl_sg


- Hereda de:

  - account.edi.xml.ubl_bis3




- No agrega campos




### account.edi.common


- Hereda de: Base



- No agrega campos




### account.edi.xml.ubl_bis3


- Hereda de:

  - account.edi.xml.ubl_21




- No agrega campos




### account.edi.ubl


- Hereda de:

  - account.edi.common




- No agrega campos




### account.edi.xml.ubl_de


- Hereda de:

  - account.edi.xml.ubl_bis3




- No agrega campos




### ir.actions.report


- Hereda de:

  - ir.actions.report




- No agrega campos




### account.edi.xml.cii


- Hereda de:

  - account.edi.common




- No agrega campos




### account.move


- Hereda de:

  - account.move




#### Campos
- **ubl_cii_xml_id** (Many2one) → ir.attachment
- **ubl_cii_xml_file** (Binary)





### account.edi.xml.ubl_efff


- Hereda de:

  - account.edi.xml.ubl_20




- No agrega campos




### account.edi.xml.ubl_21


- Hereda de:

  - account.edi.xml.ubl_20




- No agrega campos




### account.edi.xml.ubl_nl


- Hereda de:

  - account.edi.xml.ubl_bis3




- No agrega campos




### account.edi.xml.ubl_a_nz


- Hereda de:

  - account.edi.xml.ubl_bis3




- No agrega campos




### res.partner


- Hereda de:

  - res.partner




#### Campos
- **invoice_edi_format** (Selection)
- **is_ubl_format** (Boolean)
- **is_peppol_edi_format** (Boolean)
- **peppol_endpoint** (Char)
- **peppol_eas** (Selection)
- **available_peppol_eas** (Json)





### account.edi.xml.ubl_20


- Hereda de:

  - account.edi.ubl




- No agrega campos






