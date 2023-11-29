# (Work in progress) SQL Server Extended Security Updates (ESU) with Azure Arc
## Summary/TL;DR



## What are Extended Security Updates, important dates, and options
"The Extended Security Update (ESU) program is a last resort option for customers who need to run certain legacy Microsoft products past the end of support. It includes Critical and/or Important security updates for a maximum of three years after the product's End of Extended Support date."


Product | End of Extended Support/ESU Start Date | ESU End Date Year 1 | ESU End Date Year 2 | ESU End Date Year 3 | Type of Security Update |
-------|--------------------------------------|-------------------|-------------------|-------------------|-----------------------
SQL Server 2012 | July 12, 2022 | July 11, 2023 | July 9, 2024 | July 8, 2025 | Critical
SQL Server 2014 | July 9, 2024 | July 8, 2025 | July 14, 2026 | July 12, 2027 | Critical

The following links provide additional detail. The summary is that SQL Server 2012 reached end of support on July 12, 2022 and SQL Server 2014 reaches end of support on July 9, 2024. In order to continue receiving security updates you must purchase ESU for each SQL server.

You can get access to ESUs through the following options:
* SQL Server on Azure Virtual Machines - ESUs are free and enabled by default.
* SQL Server on-premises or a hosted environment. ESUs are free on the following Azure services:
  * Azure Stack HCI
  * Azure Stack Hub
* **SQL Server on-premises or a hosted environment, and connected to Azure Arc** - You can use Extended Security Updates enabled by Azure Arc to enable ESU as a monthly subscription. The updates can be automatically installed when they're available. You also benefit from the features that SQL Server enabled by Azure Arc provides. If you migrate your SQL Server to Azure or upgrade the subscription, charges then automatically stop. You can cancel the ESU subscription manually at any time.
* SQL Server on-premises or in a hosted environment, and not connected to Azure Arc - You can purchase the ESU SKU through the Volume Licensing Service Center (VLSC), and manually register your SQL Server instances on the Azure portal to receive the patches. For more information, see Register disconnected SQL Server instances for ESUs later in this article.

**Important Note** - Software Assurance (SA) is required before you can enable ESU. During the ESU enablement process you will need to attest to having SA.

### Additional resources:
[Lifecycle FAQ - Extended Security Updates](https://learn.microsoft.com/en-us/lifecycle/faq/extended-security-updates)

[What are Extended Security Updates for SQL Server?](https://learn.microsoft.com/en-us/sql/sql-server/end-of-support/sql-server-extended-security-updates?view=sql-server-ver16&tabs=portal)

[SQL Server enabled by Azure Arc supports Extended Security Updates](https://learn.microsoft.com/en-us/sql/sql-server/azure-arc/extended-security-updates?view=sql-server-ver16)

## Why enable ESU with Azure Arc?

ESU enabled by Azure Arc was announced in July of 2023. This allows customers to deploy the Azure Arc agent on their servers to enable ESU instead of managing and deploying activation keys. The link below goes into all benefits but I'll highlight two key benefits:

1. Pay as you Go (PAYG) billing - You previously paid for ESU 1 year at a time. If you decommissioned or upgraded the server after 3 months you were stuck with the fixed cost of 12 months. Arc ESU enables monthly billing. Now when you decommission or upgrade a server after 3 months you can stop billing to reduce your ESU costs.
2. Azure Billing - The monthly Arc ESU costs are billed against your Azure subscription. This allows you to monitor your ESU spend and work with your application teams to optimize their cloud spend (showback/chargeback). It also counts towards your Microsoft Azure Consumption Commitment (MACC).

**FINISH THIS**

## Licensing guidelines and pricing

### Identify core counts

## Deploy Azure Arc and configure Arc ESU licenses