# Recommendation

## Increase Public Access

* From the Governments own Data Maturity Model there is a lack of transparency. 

* Ethical/discrimination issues go un-addressed .[(8)](./references_1.md#Data_First_Research_Bulletin_MoJ)
  * There's a difference between a suspicion of discrimination vs. data-backed evidence

* The data is only available for accedemic scrutiny under strict supervision. 
  * This effectively limits it's value to the organisation and the public since insights may only appear slowly and on an ad-hoc basis, if at all.

_It's hard to claim that the MoJ is a Data Driven organisation when the data is not available to wider scrutiny._

## The pre-AI solution

Initiate a multi-year project to anonymise the data, eventually making it publicly available.

This would require significant technical changes:
  - Modernisation and standardisation of the databases, schemas and various tables inside them.
  - Likely re-write of key legacy applications
  - Large scale anonymisation effort on an ongoing basis
  - Significant security improvements to allow for public access
  - Increased cost, unless the data is made available in a more cost effective way

Even with this type of re-write/re-architecture it would likely remain the case that only specialist data scientist would be able to gain insight from it.

## The post-AI solution

AI agents that leverage the Model Context Protocol [(9)](./references_1.md#model-context-[protocol])
  * Connect to data in any form 
  * Ask questions using natural language rather than a query language
  * Return anonymized results

At a high level combining the MCP with (for example) AWS Bedrock Guardrails [(10)](./references_1.md#guardrails-sensitive-filters) would allow for a secure, anonymised and queryable data set to be made available to the public.

This would also allow the data to be queried in a natural language format, a key to opening up engagement to non-academic users.
