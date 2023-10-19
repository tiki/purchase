# Consumer Demographics

The dataset contains standard user demographic information like age, race, gender, income band, and location. See [Taxonomy](#taxonomy) below for all available fields.

Each record contains a standard `userid` which can be used to join demographics to various other datasets, such as [transaction](transaction.md) and [receipt](receipt.md).

Other user identifiers, such as `maid` are redacted by default and only available upon request where your use case(s) meets the requirements of the user and supplier.

## Access
Access requires an [AWS account](https://aws.amazon.com). To request access, provide your TIKI representative with the **ARN for the IAM user or role.**

- **Table Name**: demographic
- **Format**: Parquet
- **Location**: AWS S3 (URL provided by TIKI rep.)
- **Size:** ~5 million consumers
- **Geography:** United States

**[Get a Sample](sample/README.md)**

**Connection Guides:**
- [Query with AWS Athena](guide/query.md)
- [Connect with Iceberg (SQL/DataFrame/ETL)](guide/iceberg.md)
- [ETL Raw Parquet](guide/raw.md)

## Taxonomy
_NOTE: * fields are redacted by default._

| column                | type   | description                                               | example                                  |
|:----------------------|:-------|:----------------------------------------------------------|:-----------------------------------------|
| userid	               | string | Unique User ID	                                           | 9F8134BC4A372DDEE0A9E41D20FBC061B6084468 |
| ipaddress*	           | string | IP Address	                                               | 192.158. 1.38                            |
| maid*	                | string | Mobile advertising ID	                                    | AE7E364D-6561-471C-830D-94523BFBC94Z     |
| estimated_age	        | int32  | User age calculated from birthday	                        | 25                                       |
| age_range	            | string | User age range	                                           | 25-34                                    |
| age_generation	       | string | User's generation as determined by age	                   | Millennials                              |
| race_ethnicity	       | string | User's declared race/ethnicity	                           | African American or Black                |
| income_range	         | string | User's declared household income range before taxes	      | $30,000-$34,999                          |
| income_bucket	        | string | User's income bucket	                                     | Low Income                               |
| gender	               | string | User's declared gender	                                   | Female                                   |
| user_zip	             | string | User home zip code	                                       | 35452                                    |
| user_state	           | string | User's declared home state	                               | IL                                       |
| presence_of_children	 | string | Presence of children under 18 in user's household	        | yes                                      |
| quant_of_children	    | int32  | User's declared number of children in household under 18	 | 1                                        |
| education	            | string | User's declared highest level of education	               | Associates degree                        |
| living_situation	     | string | User's declared living situation	                         | Owned                                    |
| hh_size	              | int32  | User's declared household size	                           | 3                                        |
| marital_status	       | string | User's declared marital status	                           | Married                                  |
| employment_status	    | string | User's declared employment status	                        | Employed Full-time                       |
| sexual_orientation	   | string | User's declared sexual orientation	                       | Heterosexual                             |
