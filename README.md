# SAP-Data-Pipeline
This project implements an end-to-end data pipeline using ADF to replicate SAP tables from SQL Server into a Medallion Architecture on Azure

### Tools Used: Azure Data Factory, SQL Server, Azure SQL Database, Azure Data Lake Storage Gen2

### Project Overview
This project implements an end-to-end data pipeline using Azure Data Factory to replicate 6 SAP tables (MARA, VBAP, VBRK, COSTLIST, INVOICE_LINE_ITEM, PRODUCING_STAT_RATIO_DETAIL) from On-Premise SQL Server into a Medallion Architecture (Bronze/Silver/Gold) on Azure, enabling incremental data loads with a sliding 14-day window for reporting purposes. Three tables are loaded as CSV files into the target silver ADLS Gen2 and only the largest file is copied into the target Gold ADLS Gen2, whereas three tables are loaded as SQL tables into bronze schema in Azure SQL Source DB and incremental load of 14 days data is loaded into silver schema in Azure SQL Target DB and the latest table is copied to the target Gold Data Lake Storage as CSV file.

### Pipelines
1. pl_ingest_sqlserver_to_bronze
2. pl_check_and_delete_rowsUpdated
3. pl_adls_largest_file_gold

For more details please refer to the document: Project Name _ SAP Data Pipeline.pdf
