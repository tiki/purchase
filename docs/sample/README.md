# Cleanroom Sample

**THIS DATASET IS FOR EVALUATION PURPOSES ONLY AND MAY NOT BE SHARED OR USED IN ANY OTHER FROM WITHOUT WRITTEN CONSENT FROM TIKI INC.**

The sample cleanroom contains 1 week of actual consumer data, representing over 1 million US consumers.

**Date Range:** 8/29/23 to 9/6/23

## Contains:
- [Consumer Demographics](../demographic.md): 1.2M records
- [Purchase Transactions](../transaction.md): 34M records
- [Product Receipts](../receipt.md): 300k records

**Gross Merchandise Value (GMV):** Many customers ask for this, and while you can calculate it yourself with:

```sql
select merchant_name, sum(amount) as total
from transaction
group by merchant_name
order by total desc
```

it's even easier to just download the [gmv.csv](gmv.csv) file :).

## Access

Access to the cleanroom requires an [AWS account](https://aws.amazon.com).

To request access, contact Barry O'Connor ([barry@mytiki.com](mailto:barry@mytiki.com)) with the **ARN for the IAM user or role.**

### IAM User

To find an IAM user's ARN open the [aws console](http://console.aws.amazon.com) and head to IAM > Access Management > Users > {selected user}

<img width="1054" alt="Screenshot 2023-09-11 at 10 31 18 PM" src="https://github.com/tiki/ocean/assets/3769672/1d968af7-3323-41e5-8fcf-44005f9b730c">

### Connecting to the Cleanroom

We provide guides for the 3 most common techniques customers use to evaluate the Sample Cleanroom. 

1. [SQL querying with AWS Athena](guide/query.md)  
**Recommended for getting up and running quickly.** Run standard SQL queries at low-to-no cost. 
2. [Connect with Iceberg (SQL/DataFrame/ETL)](guide/iceberg.md)  
**Recommended for most workloads.** Use standard [Iceberg](https://iceberg.apache.org) connectors to bring datasets into your own systems with pyspark, Databricks, Snowflake, and dozens of other integrations
3. [ETL Raw Parquet](guide/raw.md)  
Don't like Iceberg or need something extra custom? The raw data parquet files are hosted in S3 for direct ETL into your system.




