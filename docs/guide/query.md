# Querying with AWS Athena

The quickest path to getting up and running standard SQL queries against TIKI datasets is through the use of [AWS Athena](https://aws.amazon.com/athena/). 

_NOTE: The instructions below are for the [Sample Cleanroom](../sample/README.md)_

### Add the data source

1. Open [Athena](https://us-east-2.console.aws.amazon.com/athena/home?region=us-east-2#/landing-page) in the us-east-2 region and open the hamburger menu.
   <img width="1438" alt="Screenshot 2023-09-11 at 10 41 25 PM" src="https://github.com/tiki/ocean/assets/3769672/6d5f8551-8cc2-4c0a-840e-2851880e72da">

2. Select **Data sources** then click **Create data source**.
   <img width="1440" alt="Screenshot 2023-09-11 at 10 47 09 PM" src="https://github.com/tiki/ocean/assets/3769672/fe261833-ffbc-4148-bef2-72f749312252">

3. Select **S3 - AWS Glue Data Catalog** scroll down and click **Next**.
   <img width="1440" alt="Screenshot 2023-09-11 at 10 45 03 PM" src="https://github.com/tiki/ocean/assets/3769672/692a7f6a-8a9e-423b-bcd9-f50442c0bd9c">

4. Select **AWS Glue Data Catalog in another account**. Then scroll down and enter:

- **Data source name**: TIKI
- **Catalog ID**: 254962200554
  <img width="1440" alt="Screenshot 2023-09-11 at 10 45 22 PM" src="https://github.com/tiki/ocean/assets/3769672/12bcec0b-c062-46ec-8a5c-08f4c5e7ce37">

5. Click **Next**, scroll down and click **Create data source**.
   <img width="1440" alt="Screenshot 2023-09-11 at 10 46 24 PM" src="https://github.com/tiki/ocean/assets/3769672/364c5638-facd-44c3-8f9f-c90468164edf">

### Run a SQL query

1. Open the **Query Editor**. Select **TIKI** from the Data Source dropdown and **cleanroom_sample** from the Database dropdown.
   <img width="1440" alt="Screenshot 2023-09-11 at 10 55 21 PM" src="https://github.com/tiki/ocean/assets/3769672/60dee800-1a0b-4e1b-b420-ac6f5880b042">

2. Run a simple query to test the connection.

```sql
select count(*) from demographic;
```
**result:** 1200000
