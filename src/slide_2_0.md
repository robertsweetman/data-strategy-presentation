# Organisational Evaluation

* NOMIS - National Offender Management Information System 
    * Legacy Oracle database that has been used to manage prisoners and probationers. 
    * Original incarnation in 2004, updated in 2017.

* OASYS - Offender Assessment System
    * Legacy Oracle based system used to asses the risk of re-offending.

```mermaid
block-beta
    columns 8
    NOMIS["NOMIS DB"]:4 OASYS["OASYS DB"]:4
    block:group1:8
        columns 1
        APPS["APPLICATIONS"] 
        REPORTING["REPORTING"]
    end
    block:group2:8
        HMPPS["HMPPS"]
        HMCTS["HMCTS"]
        LAA["LAA"]
        CICA["CICA"] 
    end
    style NOMIS fill:#3498db,stroke:#2980b9,color:white,stroke-width:2px
    style OASYS fill:#e67e22,stroke:#d35400,color:white,stroke-width:2px
    style REPORTING fill:#9b59b6,stroke:#8e44ad,color:white,stroke-width:2px
```
* HMPPS - Her Majesty's Prison and Probation Service
* HMCTS - Her Majesty's Courts and Tribunals Service
* LAA - Legal Aid Agency
* CICA - Criminal Injuries Compensation Authority
* and more...

**There are a LOT of bodies relying on this data.**

Unlike many other departments though, the MoJ has a CTO! 
