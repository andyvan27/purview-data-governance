- [Overview](#overview)
- [Prerequisites](#prerequisites)
- [Create your governance domains](#create-your-governance-domains)
- [Add domain glossary terms](#add-domain-glossary-terms)
- [Add domain data product](#add-domain-data-product)
- [Add domain critical data elements](#add-domain-critical-data-elements)
- [Add domain OKRs](#add-domain-okrs)
- [Publish domains](#publish-domains)
- [Request access to the data products](#request-access-to-the-data-products)
- [Approve access requests](#approve-access-requests)
- [Complete access requests](#complete-access-requests)
- [Register storage as ADLS source](#register-storage-as-adls-source)
- [Use Azure Data Factory for lineage](#use-azure-data-factory-for-lineage)
- [Register ADF](#register-adf)
- [Produce lineage](#produce-lineage)
- [View Data governance reports](#view-data-governance-reports)

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

## Add domain data product
- On each domain, click on Data products tile
![](images/README-2026-02-03-10-10-45.png)
- In the Data products list, click New data product and fill in
![](images/README-2026-02-03-10-19-20.png)
![](images/README-2026-02-03-10-22-59.png)
- Finish the creation

## Add domain critical data elements
- On each domain, click on Critical data elements tile
![](images/README-2026-02-03-10-33-36.png)
- In the Critical data elements list, click New critical data elements and fill in
![](images/README-2026-02-03-10-38-13.png)
- Add physical columns
![](images/README-2026-02-03-17-20-58.png)
- Add Glossary terms
- Do the same for `Revenue Amount`, `Opportunity Stage`, `Order Date` and `Customer ID`

## Add domain OKRs
- On each domain, click on OKRs tile
![](images/README-2026-02-03-10-51-30.png)
- In the OKRs list, click New OKRs and fill in
![](images/README-2026-02-03-10-52-44.png)

## Publish domains
- On each domain, click on Publish button
![](images/README-2026-02-03-11-12-17.png)
- Go to each domain artifacts and click on Publish button
![](images/README-2026-02-03-11-19-04.png)
- For Data product, it will ask to Add data assets, add sales.csv
![](images/README-2026-02-03-11-31-33.png)
- It might ask to Set up workflow, fill in, and click on Save Changes
![](images/README-2026-02-03-11-44-01.png)
- Publish it
- Do the same for `Customer` domain

## Request access to the data products
- On Purview portal, go to Unified Catalog | Discovery | Data products, select a product and click on Request access button
![](images/README-2026-02-03-15-42-53.png)
- Fill in the request and click on Send button
![](images/README-2026-02-03-15-45-04.png)
- Do the same for other products

## Approve access requests
- On Purview portal, go to Unified Catalog | Request and Approvals, select a request
![](images/README-2026-02-03-15-52-18.png)
- Give comments and click on Approve button
![](images/README-2026-02-03-15-54-47.png)
- Do the same for the others

## Complete access requests
- On Purview portal, go to Unified Catalog | Request and Approvals, select a request
- Change asset status from Not provided to Provided with comment and click Complete button
![](images/README-2026-02-03-16-23-02.png)
- Do the same for the others

## Register storage as ADLS source
- Go to Data map, register the storage account as ADLS source to the same collection
- Run scan on this new source

## Use Azure Data Factory for lineage
- On Azure portal, create a new ADF in the same resource group
- Open it in ADF studio
- Create a new pipeline `CopyPipeline`
![](images/README-2026-02-04-10-45-43.png)

## Register ADF
- On Purview portal, go to Data map | Source Management | Lineage connections, click New button
- Select the ADF created
![](images/README-2026-02-04-11-29-17.png)

## Produce lineage
- Rerun ADF
- Rescan ADLS source
- Go to Unified Catalog | Discovery | Data assets, search for `customers.csv` and open it
- Go to Lineage tab
![](images/README-2026-02-04-12-19-54.png)
- View in Data product
![](images/README-2026-02-04-13-06-28.png)

## View Data governance reports
![](images/README-2026-02-04-13-03-41.png)