# Módulo: Denmark - Accounting

## Información General
- **Nombre técnico:** l10n_dk
- **Versión:** 1.3
- **Categoría:** Accounting/Localizations/Account Charts
- **Dependencias:** base_iban, base_vat, account




## Descripción


Localization Module for Denmark

This is the module to manage the **accounting chart for Denmark**. Cover both one-man business as well as I/S, IVS, ApS and A/S

**Modulet opsætter:**

- **Dansk kontoplan**

- Dansk moms
        - 25 % moms
        - Restaurationsmoms 6,25 %
        - Omvendt betalingspligt

- Konteringsgrupper
        - EU (Virksomhed)
        - EU (Privat)
        - Tredjelande

- Finansrapporter
        - Resultatopgørelse
        - Balance
        - Momsafregning
            - Afregning
            - Rubrik A, B og C

- **Anglo-saksisk regnskabsmetode**

.

Produktopsætning:

**Vare**

**Salgsmoms:**      Salgsmoms 25 %

**Salgskonto:**     1.010 Salg af varer inkl. moms

**Købsmoms:**       Købsmoms 25 %

**Købskonto:**      2.010 Direkte vareomkostninger inkl. moms

.

**Ydelse**

**Salgsmoms:**      Salgsmoms 25 %, ydelser

**Salgskonto:**     1.011 Salg af ydelser inkl. moms

**Købsmoms:**       Købsmoms 25 %, ydelser

**Købskonto:**      2.011 Direkte omkostninger ydelser inkl. moms

.

**Vare med omvendt betalingspligt**

**Salgsmoms:**      Salg med omvendt betalingspligt

**Salgskonto:**     1.012 Salg af varer ekskl. moms

**Købsmoms:**       Køb med omvendt betalingspligt

**Købskonto:**      2.012 Direkte vareomkostninger ekskl. moms


.

**Restauration**

**Købsmoms:**       Restaurationsmoms 6,25 %, købsmoms

**Købskonto:**      4010 Restaurationsbesøg
    



## Modelos

### account.chart.template


- Hereda de:

  - account.chart.template




- No agrega campos



### account.journal


- Hereda de:

  - account.journal




- No agrega campos



### ['account.account']


- Hereda de:


  - account.account





- No agrega campos



### res.partner


- Hereda de:

  - res.partner




- No agrega campos





