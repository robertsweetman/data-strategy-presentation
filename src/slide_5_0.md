# Implementation

```mermaid
flowchart TD

   db1[(Db 1)]
   db2[(Db 2)]
   db3[(Db 3)]
   ai["MCP"]
   guard["Guardrails"] 
   query["Query Frontend"]

   ai --> db1
   ai --> db2
   ai --> db3
   ai --> guard
   guard --> query
   query --> ai

   linkStyle 0,1,2,3,4,5 stroke:#ffffff,stroke-width:2px
   style query fill:#3498db,stroke:#2980b9,color:white,stroke-width:2px
   style guard fill:#ff0000,stroke:#ff0000,color:white,stroke-width:2px
   style ai fill:#e67e22,stroke:#d35400,color:white,stroke-width:2px    
```
## Stakeholders
* Executive Board and SLT
  * Drive change
* Security Team
  * Legitimacy and Confidence
* Data and Reporting Team
  * Evangelise Internally

---
> ### Milestone 3: Create an Implementation Plan For Your Proposal
> For your proposed change, deliver a compelling proposal focussed on the business impact of your data strategy recommendation. 
> Include a detailed implementation plan, considering potential limitations and risks to inform the impace and scalability of your proposal (wk9)
>
> 4 minutes
> * Detailed plan for implementing the proposed changes, including steps, timelines and key stakeholders
> * Analysis of potential limitations and risks associated with the proposal
> * Strategies for mitigating risks and addressing limitations to ensure scalability and impact
