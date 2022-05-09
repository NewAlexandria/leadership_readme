# Data Warehouse Naming Conventions

[via](https://stackoverflow.com/a/1830893/263858)

`[type][subject][name]`

* where type is 'dim' or 'fact' (or 'facts' for aggregates)
* where subject is the subject area within the warehouse ('comm' for common, 'fw' for firewall, 'ids', etc)
* where name is ideally a single word name, or abbreviations of dimensions in the case of an aggregate table
* ex: `dim_comm_org` for the organizational dimension
* ex: `fact_scan` for the scan fact table
* ex: `facts_scan_org_sev_daily` - fact scan summary table grouped at the org, sev & day level

### Column Names:

don't prefix with the entire table name - that's way too long

do prefix with just a meaningful part of it - this helps tremendously when writing or reading queries.


## Sources

[via](https://adatis.co.uk/azure-data-factory-suggested-naming-conventions-and-best-practices/)

| Type      | Linked Service               | Name   | Linked Service | Dataset  | Full            |
|-----------|------------------------------|--------|----------------|----------|-----------------|
| Databases | SQL Server*                  | MSQL\_ | LS\_MSQL\_     | DS\_MSQL\_  | LS\_SQL\_Example  |
|           | Oracle*                      | ORAC\_ | LS\_ORAC\_       | DS\_ORAC\_ | LS\_ORAC\_Example |
|           | MySQL*                       | MYSQ\_ | LS\_MYSQ\_       | DS\_MYSQ\_ | LS\_MYSQ\_Example |
|           | DB2*                         | DB2\_  | LS\_DB2\_        | DS\_DB2\_  | LS\_DB2\_Example  |
|           | Teradata*                    | TDAT\_ | LS\_TDAT\_       | DS\_TDAT\_ | LS\_TDAT\_Example |
|           | PostgreSQL*                  | PG\_   | LS\_PG\_       | DS\_PG\_ | LS\_PG\_Example |
|           | Sybase*                      | SYBA\_ | LS\_SYBA\_       | DS\_SYBA\_ | LS\_SYBA\_Example |
|           | Cassandra*                   | CASS\_ | LS\_CASS\_       | DS\_CASS\_ | LS\_CASS\_Example |
|           | MongoDB*                     | MONG\_ | LS\_MONG\_       | DS\_MONG\_ | LS\_MONG\_Example |
|           | Amazon Redshift              | AMRED\_ | LS\_AMRED\_     | DS\_AMRED\_ | LS\_AMRED\_Example |
| File      | File System*                 | FILE\_ | LS\_FILE\_       | DS\_FILE\_ | LS\_FILE\_Example |
|           | HDFS*                        | HDFS\_ | LS\_HDFS\_       | DS\_HDFS\_ | LS\_HDFS\_Example |
|           | Amazon S3                    | AMS3\_ | LS\_AMS3\_       | DS\_AMS3\_ | LS\_AMS3\_Example |
|           | FTP                          | FTP\_  | LS\_FTP\_        | DS\_FTP\_  | LS\_FTP\_Example  |
| Services  | Finale                       | FNLE\_ | LS\_FNLE\_       | DS\_FNLE\_  | LS\_FNLE_Example  |
|           | Airtable                     | AIRT\_ | LS\_AIRT\_       | DS\_AIRT\_ | LS\_AIRT\_Example |
|           | Klaviyo                      | AIRT\_ | LS\_AIRT\_       | DS\_AIRT\_ | LS\_AIRT\_Example |
|           | Northbeam                    | NBM\_  | LS\_NBM\_       | DS\_NBM\_ | LS\_NBM\_Example |
|           | ShipStation                  | AIRT\_ | LS\_AIRT\_       | DS\_AIRT\_ | LS\_AIRT\_Example |
|           | SOS Inventory                | SOS\_  | LS\_SOS\_        | DS\_SOS\_ | LS\_SOS\_Example |
|           | EasyPost                     | AIRT\_ | LS\_AIRT\_       | DS\_AIRT\_ | LS\_AIRT\_Example |
|           | ZenDesk                      | ZEN\_  | LS\_AIRT\_       | DS\_AIRT\_ | LS\_AIRT\_Example |
|           | Andlor                       | ANDL\_ | LS\_ANDL\_      | DS\_ANDL\_ | LS\_ANDL\_Example |
|           | Storage Made Easy            | SME\_  | LS\_SME\_       | DS\_SME\_  | LS\_SME_Example  |
| Google    | Google Big Table             | GBT\_  | LS\_GBT\_       | DS\_GBT\_ | LS\_GBT\_Example |
|           | Google Tag Manager           | GTM\_  | LS\_GTM\_       | DS\_GTM\_ | LS\_GTM\_Example |
|           | Google Analytics             | GA\_   | LS\_GA\_       | DS\_GA\_ | LS\_GA\_Example |
|           | Google Sheets                | GSHT\_ | LS\_GSHT\_       | DS\_GSHT\_ | LS\_GSHT\_Example |
|           | Google Docs                  | GDOC\_ | LS\_GDOC\_       | DS\_ GDOC\_ | LS\_ GDOC\_Example |
| Azure     | Azure Blob storage           | AZBLB\_ | LS\_AZBLB\_       | DS\_AZBLB\_ | LS\_AZBLB\_Example |
|           | Azure Data Lake Store        | AZDLS\_ | LS\_AZDLS\_       | DS\_AZDLS\_ | LS\_AZDLS\_Example |
|           | Azure SQL Database           | AZSQL\_ | LS\_AZSQL\_       | DS\_AZSQL\_ | LS\_AZSQL\_Example |
|           | Azure SQL Data Warehouse     | AZSDW\_ | LS\_AZSDW\_       | DS\_AZSDW\_ | LS\_AZSDW\_Example |
|           | Azure Table storage          | AZTBL\_ | LS\_AZTBL\_       | DS\_AZTBL\_ | LS\_AZTBL\_Example |
|           | Azure DocumentDB             | AZDOC\_ | LS\_AZDOC\_       | DS\_AZDOC\_ | LS\_AZDOC\_Example |
|           | Azure Search Index           | AZSER\_ | LS\_AZSER\_       | DS\_AZSER\_ | LS\_AZSER\_Example |
| Others    | Salesforce                   | SAFC\_ | LS\_SAFC\_       | DS\_SAFC\_ | LS\_SAFC\_Example |
|           | Generic ODBC*                | ODBC\_ | LS\_ODBC\_       | DS\_ODBC\_ | LS\_ODBC\_Example |
|           | Generic OData                | ODAT\_ | LS\_ODAT\_       | DS\_ODAT\_ | LS\_ODAT\_Example |
|           | Web Table (table from HTML)  | WEBT\_ | LS\_WEBT\_       | DS\_WEBT\_ | LS\_WEBT\_Example |
|           | GE Historian*                | GEHI\_ | LS\_GEHI\_       | DS\_GEHI\_ | LS\_GEHI\_Example |


## Pipelines

[via](https://towardsdatascience.com/architecting-a-machine-learning-pipeline-a847f094d1c7)

| Type                         | Name     | Action                       | Example                                 |
|------------------------------|----------|------------------------------|-----------------------------------------|
| Data movement Activity       | PL\_DATA\_ | NA                           | PL\_DATA\_DS\_SQL\_Person\_To\_DS\_ABLB\_Person |
| Data transformation pipeline | PL\_TRAN\_ | SPRC – Stored Procedure      | PL\_TRAN\_SPRC\_CleanDimAccount            |
|                              | PL\_TRAN\_ | DNET – Script                | PL\_TRAN\_DNET\_AggregateSales             |
|                              | PL\_TRAN\_ | ADLK – Azure Data Lake       | PL\_TRAN\_ADLK\_AggregateSales             |
|                              | PL\_TRAN\_ | HIVE – Hive                  | PL\_TRAN\_HIVE\_AggregateSales             |
|                              | PL\_TRAN\_ | PIG – Pig                    | PL\_TRAN\_PIG\_AggregateSales              |
|                              | PL\_TRAN\_ | MAPR – MapReduce             | PL\_TRAN\_MAPR\_AggregateSales             |
|                              | PL\_TRAN\_ | HADP – Hadoop Stream         | PL\_TRAN\_HADP\_StreamData                 |
|                              | PL\_TRAN\_ | AML – Azure Machine Learning | PL\_TRAN\_AML\_CalculateMonthlyChurn       |
| Data Segementation           | PL\_SEG\_  | OPS manual ops classification | PL\_SEG\_CLAS\_UserFirstPurchaseBehavior  |
| Model Training               | PL\_MTRAIN\_ | SUP supervised training    | PL\_MTRAIN\_SUP\_UserFirstPurchaseBehavior |
| Model Training               | PL\_MTRAIN\_ | UNSUP unsupervised training | PL\_MTRAIN\_UNSUP\_UserFirstPurchaseBehavior |
| Model Training               | PL\_MTRAIN\_ | SEMISUP semi-supervised training | PL\_MTRAIN\_SEMISUP\_UserFirstPurchaseBehavior       |
| Model Training               | PL\_MTRAIN\_ | REIF reinforcement training | PL\_MTRAIN\_REIF\_UserFirstPurchaseBehavior |
| Model Evaluation             | PL\_MEVAL\_ | OPS human model eval        | PL\_MEVAL\_OPS\_UserFirstPurchaseBehavior  |
| Model Evaluation             | PL\_MEVAL\_ | REPLAY model eval with data | PL\_MEVAL\_AML\_UserFirstPurchaseBehavior  |
| Model Deployment             | PL\_MODL\_ | depoyed model name           | PL\_MODL\_UserFirstPurchaseBehavior        |
| Model Performance            | PL\_MPERF\_ | model perf metrics          | PL\_MPERF\_UserFirstPurchaseBehavior       |
