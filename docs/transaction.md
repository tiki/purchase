# Purchase Transactions
The dataset contains purchase transaction information like the date, amount, merchant, type, and location. Combine with [demographic](demographic.md) to build profiles against spend. See [Taxonomy](#taxonomy) below for all available fields.

Each record contains a standard `userid` which can be used to join demographics to various other datasets, such as [transaction](transaction.md) and [demographic](demographic.md).

## Access
Access requires an [AWS account](https://aws.amazon.com). To request access, provide your TIKI representative with the **ARN for the IAM user or role.**

- **Table Name**: receipt
- **Format**: Parquet
- **Location**: AWS S3 (URL provided by TIKI rep.)
- **Size:** ~50M unique transactions per month
- **Geography:** United States

**[Get a Sample](sample/README.md)**

**Connection Guides:**
- [Query with AWS Athena](guide/query.md)
- [Connect with Iceberg (SQL/DataFrame/ETL)](guide/iceberg.md)
- [ETL Raw Parquet](guide/raw.md)
## Taxonomy
| column                              | type   | description                                                                                                                     | example                                  |
|:------------------------------------|:-------|:--------------------------------------------------------------------------------------------------------------------------------|:-----------------------------------------|
| userid	                             | string | XXXX Unique User ID	                                                                                                            | 9F8134BC4A372DDEE0A9E41D20FBC061B6084468 |
| transactionid	                      | string | Unique Transaction ID	                                                                                                          | MBOY9BJX55S5EBWPD1QATQ9BJVQKYNHMM7DWE    |
| authorized_date	                    | string | Authorized Date, date user authorizes purchase	                                                                                 | 2022-05-07                               |
| transaction_date	                   | string | Transaction Date, date bank authorizes purchase; can be several days after authorized date; otherwise known as the posted date	 | 2022-05-09                               |
| clean_merchant_name	                | string | Merchant name field that has been through Attain's data hygiene IP	                                                             | Walmart                                  |
| merchant_name	                      | string | Merchant Name	                                                                                                                  | WALMART                                  |
| transaction_name	                   | string | Transaction Name	                                                                                                               | WALMART                                  |
| amount	                             | float  | Transaction Total Amount	                                                                                                       | 96.21                                    |
| payment_channel	                    | string | Online, offline, or other                                                                                                       | IN STORE                                 |
| category_level1	                    | string | Transaction Category Level 1	                                                                                                   | SHOPS                                    |
| category_level2	                    | string | Transaction Category Level 2	                                                                                                   | SUPERMARKETS AND GROCERIES               |
| category_level3	                    | string | Transaction Category Level 3	                                                                                                   |                                          |
| num_levels	                         | int32  | Number of Category Levels (how many categories exist for this transaction)	                                                     | 2                                        |
| primary_personal_finance_category	  | string | Primary Transaction Category, will soon replace Transaction Category Level 1	                                                   | GENERAL MERCHANDISE                      |
| detailed_personal_finance_category	 | string | Detailed Transaction Category, will soon replace Transaction Category Level 2	                                                  | SUPERSTORES                              |
| merchant_address	                   | string | Merchant Street Address	                                                                                                        | 5710 MCFARLAND BLVD                      |
| merchant_city	                      | string | Merchant City	                                                                                                                  | NORTHPORT                                |
| merchant_state	                     | string | Merchant State	                                                                                                                 | AL                                       |
| merchant_zip	                       | string | Merchant Zip	                                                                                                                   | 35476                                    |
