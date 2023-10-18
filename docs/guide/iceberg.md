## Connect with Iceberg
With Iceberg, directly query data, create data frames, and plug results direct into your ETL. This guide assumes a familiarity with [Apache Iceberg](https://iceberg.apache.org).

_NOTE: The instructions below are for the [Sample Cleanroom](../sample/README.md)_

## Location
- Data and metadata files for the cleanroom are hosted in the S3 bucket [s3://mytiki-cleanroom-sample](https://s3.console.aws.amazon.com/s3/buckets/mytiki-cleanroom-sample?region=us-east-2)
- AWS Glue contains a metadata catalog

## Connect

Set your Iceberg Catalog connection properties to:
- **catalog-name**: iceberg
- **catalog-impl**: org.apache.iceberg.aws.glue.GlueCatalog
- **warehouse**: s3://mytiki-cleanroom-sample
- **io-impl**: org.apache.iceberg.aws.s3.S3FileIO

Detailed instructions on configuring an Iceberg client using AWS Glue + S3 can be found in [Apache's docs](https://iceberg.apache.org/docs/latest/aws/#glue-catalog).

### Example (Java):

```
GlueCatalog catalog = new GlueCatalog();
catalog.initialize("glue_catalog", new HashMap<>(){{
    put("catalog-name", properties.getProperty("iceberg"));
    put("catalog-impl", properties.getProperty("org.apache.iceberg.aws.glue.GlueCatalog"));
    put("warehouse", properties.getProperty("s3://mytiki-cleanroom-sample"));
    put("io-impl", properties.getProperty("org.apache.iceberg.aws.s3.S3FileIO"));
}});
```

### Tooling

- [Spark/PySpark](https://iceberg.apache.org/spark-quickstart/)
- [Hive](https://iceberg.apache.org/hive-quickstart/)
- [Snowflake](https://www.snowflake.com/blog/iceberg-tables-powering-open-standards-with-snowflake-innovations/)
- [AWS EMR](https://docs.aws.amazon.com/emr/latest/ReleaseGuide/emr-iceberg-use-cluster.html)
- [Databricks](https://docs.databricks.com/en/delta/clone-parquet.html)
- and a ton more...
