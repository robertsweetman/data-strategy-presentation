# Current Data Strategy and Governance - Overview

```mermaid
flowchart TD;
    MOJDB["Ministry of Justice Departmental Board"];
    ARAC["Audit Risk and Assurance Committee"];
    NC["Nominations Committee"];
    EC["Executive Committee"];
    DB["Delivery Board"];
    IC["Investment Committee"];
    FPR["Finance Performance and Risk"];
    PBR["People Business Committee"];
    PC["PortFolio Committee"];
    
    %% HMPPS["HM Prison and Probation Service"];
    %% HMCTS["HM Courts and Tribunals Service"];
    %% LAA["Legal Aid Agency"];
    %% OPG["Office of the Public Guardian"];
    %% CICA["Criminal Injuries Compensation Authority"];
    
    MOJDB --> ARAC & NC & EC;
    EC --> DB & IC & FPR & PBR & PC;
    MOJDB -.-> PC;

    style EC fill:#3498db,stroke:#2980b9,color:white,stroke-width:2px
    style DB fill:#e67e22,stroke:#d35400,color:white,stroke-width:2px
    %% style DTC fill:#9b59b6,stroke:#8e44ad,color:white,stroke-width:2px
    linkStyle 0,1,2,3,4,5,6,7,8 stroke:#ffffff,stroke-width:2px
```

* While it's a challenge to focus across ALL areas, given the scope of the Digital Strategy document, there are two key issues which are inexorably linked...

  1. Legacy Systems.
  2. User experience, impacting both staff and prisoners.
  3. Here comes <del>our new robot overlords</del> AI.

![MoJ Digital Strategy](./images/digi-strategy-2025.jpg)

![MoJ Focus](./images/wordcloud-191603.png)


---
> **TODO:** Evaluation (using a particular method) and Gap Analysis
> ### Milestone 1: Evaluate your organisations data stratey and governance
>
> Use Principals of leadership to thoroughly evaluate your organisations relationship between data strategy, data governance and value (wk 3)
>
> 4 minutes
> * Overview of the organisations current data strategy and governance
> * Evaluation of current data governance approaches, model proposals and data quality enhancements
> * Gap analysis of potential improvements


