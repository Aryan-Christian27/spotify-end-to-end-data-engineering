# Spotify End To End Data Engineering Project

## Introduction
in this project, we will build an ETL (Extract, Transform, Load) Pipeline using the Spotify API on AWS.The Pipeline will retrieve data from the spotify API ,transform it to a desired formate, and load it into an AWS data store.

### Architecture
![Spotify Data-Graph](https://user-images.githubusercontent.com/43290363/224507907-2b22a26f-7a9a-420a-adc5-6c959c217658.png)

### About Dataset/API
This API contain information about music artist, album and songs - [Spotify API](https://spotipy.readthedocs.io/en/2.25.1/)

 ## Services Used
 1. **S3 (simple storage service):** Amazone S3 (simple storage servide) is a highly scalable object storage servvice that can store and retrive any amount of data from commonly used to store and distribution large media files, data backups, and statics website files.
 
 2. **AWS Lamda:** AWS Lamda is a serverless computing service that lets you run your code without managing servers.You can use lamda to run code in response to events like changes in S3 , DynamoDB, or other AWS services.

 3. **Cloud Watch:** Amazone CloudWatch is a monitoring service for the AWS resources and the application you to run on them. You can use CloodWatch to collect and track metrics, collect and monitor log files, and set alarms.

 4.  **Glue Crawler:** AWS Glue Crawler is a fully managed service that automaticallty crawls your data sources, identifies data formates, and infers schemas to create an AWS Glue Data Catlog.

 5.  **Data Catlog:** AWS Glue Data Catlog is a fully managed metadata repository that makes it easy to discover and managed data in AWS. You can use the GLue Data Catlog with other AWS service Such as Athena.

 6.  **Amazon Athena:** Amazon Athena is an interactive query service that makes it easy to analyze data in Amazon S3 using standard SQL. You can use Athena to analyze data in your Glue Data Catalog or in other S3 buckets

### Install Packages
```
pip install pandas
pip install numpy
pip instal spotipy
```

### Project Execution Flow 
Extract data from API -> Lamda Trigger (Every 1 hour) -> Run Extract code -> store Raw Data -> Trigger Transform Function -> Transform Data and Load It-> Query Using Athena
