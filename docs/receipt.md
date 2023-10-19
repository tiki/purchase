# Purchase Receipts
The dataset contains receipt-level purchase information like the specific upc code, quantity, merchant, price, and item description. Combine with [transaction](transaction.md) to drill into transaction spend. See [Taxonomy](#taxonomy) below for all available fields.

Each record contains a standard `userid` which can be used to join demographics to various other datasets, such as [transaction](transaction.md) and [demographic](demographic.md).

## Access
Access requires an [AWS account](https://aws.amazon.com). To request access, provide your TIKI representative with the **ARN for the IAM user or role.**

- **Table Name**: receipt
- **Format**: Parquet
- **Location**: AWS S3 (URL provided by TIKI rep.)
- **Size:** ~500k unique purchases per month
- **Geography:** United States

**[Get a Sample](sample/README.md)**

**Connection Guides:**
- [Query with AWS Athena](guide/query.md)
- [Connect with Iceberg (SQL/DataFrame/ETL)](guide/iceberg.md)
- [ETL Raw Parquet](guide/raw.md)

## Taxonomy
| column               | type   | description                                                             | example                                  |
|:---------------------|:-------|:------------------------------------------------------------------------|:-----------------------------------------|
| userid	              | string | XXXX Unique User ID	                                                    | 9F8134BC4A372DDEE0A9E41D20FBC061B6084468 |
| receiptID	           | string | Unique Receipt Identifier; ties products together at the receipt-level	 | AC668FE7-8B76-4DE8-BF3A-4F88820A3465     |
| receipt_date	        | string | Receipt Date	                                                           | 12/22/2022                               |
| merchant_name	       | string | Merchant Name	                                                          | WALGREENS                                |
| merchant_address	    | string | Merchant Street Address	                                                | 5036 S COTTAGE GROVE AVE                 |
| merchant_city	       | string | Merchant City	                                                          | CHICAGO                                  |
| merchant_state	      | string | Merchant State	                                                         | IL                                       |
| merchant_zip	        | string | Merchant Zip	                                                           | 60615                                    |
| channel	             | string | Merchant Channel	                                                       | MASS                                     |
| amount	              | float  | Receipt Total Amount	                                                   | 4.86                                     |
| brand	               | string | Brand Name	                                                             | SKINNY POP                               |
| product_name	        | string | Standard Product Name	                                                  | SKINNY POP ORIGINAL POPCORN, 6.7 OZ      |
| product_description	 | string | Product Details (Size, Count, etc.)	                                    | 6.7OZ ORIGI                              |
| quantity	            | int32  | Receipt Quantity	                                                       | 1                                        |
| unit_price	          | float  | Item Price	                                                             | 4.2                                      |
| total_price	         | float  | Item Price x Quantity	                                                  | 4.2                                      |
| category_level1	     | string | Product Category Level 1	                                               | GROCERY                                  |
| category_level2	     | string | Product Category Level 2	                                               | SNACKS                                   |
| category_level3	     | string | Product Category Level 3	                                               | POPCORN                                  |
| size	                | string | Product Size	                                                           | 6.7 OZ                                   |
| upc	                 | string | Product UPC Code	                                                       | 816925000000                             |
