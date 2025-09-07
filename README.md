# Spotify End To End Data Engineering Project

## Introduction
This project focuses on building a robust ETL (Extract, Transform, Load) pipeline using the Spotify API and AWS services. The pipeline is designed to automatically retrieve music data from the Spotify API, transform it into a desired format, and load it into an AWS data store for analysis. The final architecture enables scalable data processing and analytics.

### Architecture
![Spotify Data-Graph](https://user-images.githubusercontent.com/43290363/224507907-2b22a26f-7a9a-420a-adc5-6c959c217658.png)

### About Dataset/API
This API contain information or Data about music artist, album, songs, views etc.. - [Spotify API](https://developer.spotify.com/)\
This Document contain how to use this spotify Module - [Spotify Module](https://spotipy.readthedocs.io/en/2.25.1/)

### Project Workflow
The project's execution flow is automated and designed for continuous data ingestion:
* **Extraction:** The pipeline is triggered to extract raw data from the Spotify API. This data includes information on artists, albums, and songs.
* **Serverless Trigger:** An AWS Lambda function is scheduled to run every hour, initiating the extraction process.
* **Raw Data Storage:** The raw data is stored in an Amazon S3 bucket, which acts as a data lake.
* **Transformation & Loading:** The pipeline then triggers a transformation function that processes the raw data. The cleaned and structured data is loaded into a target data store.
* **Query & Analysis:** The final, structured data is made available for analysis using services like Amazon Athena, which allows for querying the data using standard SQL.

 ## Services Used
 1. **S3 (simple storage service):** Amazone S3 (simple storage servide) is a highly scalable object storage servvice that can store and retrive any amount of data from commonly used to store and distribution large media files, data backups, and statics website files.
 
 2. **AWS Lamda:** AWS Lamda is a serverless computing service that lets you run your code without managing servers.You can use lamda to run code in response to events like changes in S3 , DynamoDB, or other AWS services.

 3. **Cloud Watch:** Amazone CloudWatch is a monitoring service for the AWS resources and the application you to run on them. You can use CloudWatch to collect and track metrics, collect and monitor log files, and set alarms.

 4.  **Glue Crawler:** AWS Glue Crawler is a fully managed service that automaticallty crawls your data sources, identifies data formates, and infers schemas to create an AWS Glue Data Catlog.

 5.  **Data Catlog:** AWS Glue Data Catlog is a fully managed metadata repository that makes it easy to discover and managed data in AWS. You can use the GLue Data Catlog with other AWS service Such as Athena.

 6.  **Amazon Athena:** Amazon Athena is an interactive query service that makes it easy to analyze data in Amazon S3 using standard SQL. You can use Athena to analyze data in your Glue Data Catalog or in other S3 buckets

## ⚙️ How to Use This Project
To replicate this project on your AWS account, follow these steps:


### Prerequisites
* An AWS account with configured credentials.

* A Spotify Developer account to get API credentials.

* Python 3.8+

### Install Packages
```
pip install pandas
pip install numpy
pip install spotipy
```
### Configure AWS & Spotify:
* Create an S3 bucket for your raw and transformed data.

* Deploy the Python script as an AWS Lambda function.

* Set your Spotify API credentials as environment variables in the Lambda function.

* Configure a CloudWatch event to trigger the Lambda function on a schedule (e.g., every hour).

* Create a Glue Crawler to catalog the data in your S3 bucket.

### Query Data:
* Use Amazon Athena to connect to your Glue Data Catalog and run SQL queries on your data.

### Visualize Data:
* Visualize Transform Data using QuickSight  

### Project Execution Flow 
Extract data from API -> Lamda Trigger (Every 1 hour) -> Run Extract code -> store Raw Data -> Trigger Transform Function -> Transform Data and Load It-> Query Using Athena -> Visualize Using QuickSight

# 👤 Author

* **[ Aryan Khristi ]** - [![linkedin](https://img.shields.io/badge/linkedin-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/christian-aryan2710/)
