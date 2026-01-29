- [Overview](#overview)
- [Prerequisites](#prerequisites)
- [Create your governance domains](#create-your-governance-domains)
- [Add domain glossary terms](#add-domain-glossary-terms)

## Overview
Steps to play with Microsoft Purview Data Governance (Domain driven)

## Prerequisites
- M365 tenant with E5 license
- Azure subscription on the same tenant
- Purview account has been configured/upgraded to an Azure Purview Account to be the Enterprise level Purview Account
![](images/README-2026-01-29-17-43-59.png)

## Create your governance domains
- On Purview portal, go to Unified Catalog | Catalog management | Governance domains
- Click Create governance domain button
- Fill in Basic details for `Sales`, click Next button
![](images/README-2026-01-29-17-59-54.png)
- Leave no custom attribute and click Create button
- Do the same for `Customer`
![](images/README-2026-01-29-18-05-04.png)

## Add domain glossary terms
- On each domain, click on Glossary terms tile
![](images/README-2026-01-29-18-21-44.png)
- In the Glossary terms list, click New term and fill in
![](images/README-2026-01-29-18-27-42.png)
- Do the same for: `Order`, `Opportunity`, `Revenue`, `Product`
![](images/README-2026-01-29-18-33-29.png)
- Do the same for `Customer` domain the terms: `Customer`