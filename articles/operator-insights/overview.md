---
title: What is Azure Operator Insights?
description: Azure Operator Insights is an Azure service for monitoring and analyzing data from multiple sources
author: rcdun
ms.author: rdunstan
ms.reviewer: rathishr
ms.service: operator-insights
ms.topic: overview 
ms.date: 01/10/2024
---

# What is Azure Operator Insights?

Azure Operator Insights is a fully managed service that enables the collection and analysis of massive quantities of network data gathered from complex multi-part or multi-vendor network functions. It delivers statistical, machine learning, and AI-based insights for operator-specific workloads to help operators understand the health of their networks and the quality of their subscribers' experiences in near real-time.

Azure Operator Insights accelerates time to business value by eliminating the pain and time-consuming task of assembling off-the-shelf cloud components (chemistry set). This reduces load on ultra-lean operator platform and data engineering teams by making the following turnkey: 
High scale ingestion to handle large amounts of network data from operator data sources. 

- Pipelines managed for all operators, leading to economies of scale dropping the price. 
- Operator privacy module. 
- Operator compliance including handling retention policies. 
- Common data model with open standards such as parquet and delta lake for easy integration with other Microsoft and non-Microsoft services.
- High speed analytics to enable fast data exploration and correlation between different data sets produced by disaggregated 5G multi-vendor networks. 

The result is that the operator has a lower total cost of ownership but higher insights of their network over equivalent on-premises or cloud chemistry set platforms.

## How does Azure Operator Insights work?

Azure Operator Insights requires two separate types of resources.

- _Ingestion agents_ in your network collect data from your network and upload them to Data Products in Azure.
- _Data Product_ resources in Azure process the data provided by ingestion agents, enrich it and make it available to you.
    - You can use prebuilt dashboards provided by the Data Product or build your own in Azure Data Explorer. Azure Data Explorer also allows you to query your data directly, analyze it in Power BI or use it with Logic Apps. For more information, see [Data visualization in Data Products](concept-data-visualization.md).
    - Data Products provide [metrics for monitoring the quality of your data](concept-data-quality-monitoring.md).
    - Data Products are designed for specific types of source data and provide specialized processing for that source data. For more information, see [Data types](concept-data-types.md).

:::image type="complex" source="media/operator-insights-architecture.svg" alt-text="Diagram of ingestion agents and Data Products for Azure Operator Insights " lightbox="media/operator-insights-architecture.svg":::
    Diagram of the Azure Operator Insights architecture. It shows ingestion by ingestion agents from on-premises data sources, processing in a Data Product, and analysis and use in Logic Apps and Power BI.
:::image-end:::

We provide the following Data Products.

|Data Product  |Purpose  |Supporting ingestion agent|
|---------|---------|---------|
|[Quality of Experience - Affirmed MCC Data Product](concept-mcc-data-product.md) | Analysis and insight from EDRs provided by Affirmed Networks Mobile Content Cloud (MCC) network elements| [MCC EDR ingestion agent](how-to-install-mcc-edr-agent.md)|
| [Monitoring - Affirmed MCC Data Product](concept-monitoring-mcc-data-product.md) | Analysis and insight from performance management data (performance statistics) from Affirmed Networks MCC network elements| [SFTP ingestion agent](sftp-agent-overview.md) |

If you prefer, you can provide your own ingestion agent to upload data to your chosen Data Product.

## How do I get access to Azure Operator Insights?

Access is currently limited by request. More information is included in the application form. We appreciate your patience as we work to enable broader access to Azure Operator Insights Data Product. Apply for access by [filling out this form](https://aka.ms/AAn1mi6).
