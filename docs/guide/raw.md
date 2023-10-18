## Raw datasets

**Advanced.** For most production use cases we recommend using our [Iceberg](iceberg.md) configuration, which resolves both the metadata and raw data for you and most likely already compatible with all your favorite data tooling.

**All files are in parquet and comply with the iceberg open table format.**

_NOTE: The instructions below are for the [Sample Cleanroom](../sample/README.md)_

## Location
- Data files
  - demographic: [s3://mytiki-cleanroom-sample/demographic/data](https://s3.console.aws.amazon.com/s3/buckets/mytiki-cleanroom-sample?region=us-east-2&prefix=demographic/data/)
  - transaction: [s3://mytiki-cleanroom-sample/transaction/data](https://s3.console.aws.amazon.com/s3/buckets/mytiki-cleanroom-sample?region=us-east-2&prefix=transaction/data/)
  - receipt: [s3://mytiki-cleanroom-sample/receipt/data](https://s3.console.aws.amazon.com/s3/buckets/mytiki-cleanroom-sample?region=us-east-2&prefix=receipt/data/)
- Metadata files
  - demographic: [s3://mytiki-cleanroom-sample/demographic/metadata](https://s3.console.aws.amazon.com/s3/buckets/mytiki-cleanroom-sample?region=us-east-2&prefix=demographic/metadata/)
  - transaction: [s3://mytiki-cleanroom-sample/transaction/metadata](https://s3.console.aws.amazon.com/s3/buckets/mytiki-cleanroom-sample?region=us-east-2&prefix=transaction/metadata/)
  - receipt: [s3://mytiki-cleanroom-sample/receipt/metadata](https://s3.console.aws.amazon.com/s3/buckets/mytiki-cleanroom-sample?region=us-east-2&prefix=receipt/metadata/)

