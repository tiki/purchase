## Connecting directly

*This section assumes a familiarity with [Apache Iceberg](https://iceberg.apache.org).*

All files (data and metadata) for the lake can be found in the S3 bucket **[s3://mytiki-cleanroom-sample](https://s3.console.aws.amazon.com/s3/buckets/mytiki-cleanroom-sample?region=us-east-2)** with [AWS Glue](https://aws.amazon.com/glue/) as the metadata catalog.

Just set your Iceberg Catalog properties to:
- **catalog-name**: iceberg
- **catalog-impl**: org.apache.iceberg.aws.glue.GlueCatalog
- **warehouse**: s3://mytiki-cleanroom-sample
- **io-impl**: org.apache.iceberg.aws.s3.S3FileIO

For example, here's how we do it in Java:

```
GlueCatalog catalog = new GlueCatalog();
catalog.initialize("glue_catalog", new HashMap<>(){{
    put("catalog-name", properties.getProperty("iceberg"));
    put("catalog-impl", properties.getProperty("org.apache.iceberg.aws.glue.GlueCatalog"));
    put("warehouse", properties.getProperty("s3://mytiki-cleanroom-sample"));
    put("io-impl", properties.getProperty("org.apache.iceberg.aws.s3.S3FileIO"));
}});
```

Detailed instructions on configuring an Iceberg client using AWS Glue + S3 can be found in [Apache's docs](https://iceberg.apache.org/docs/latest/aws/#glue-catalog).

With your Iceberg client configured, use your favorite data tools to interact with the dataset.

- [Spark/PySpark](https://iceberg.apache.org/spark-quickstart/)
- [Hive](https://iceberg.apache.org/hive-quickstart/)
- [Snowflake](https://www.snowflake.com/blog/iceberg-tables-powering-open-standards-with-snowflake-innovations/)
- [AWS EMR](https://docs.aws.amazon.com/emr/latest/ReleaseGuide/emr-iceberg-use-cluster.html)
- [Databricks](https://docs.databricks.com/en/delta/clone-parquet.html)
- and a ton more...
