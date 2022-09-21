# Data-analysis-using-AWS-services-Athena-Glue-S3-Quicksight

This is an end-to-end simple data analytics solution using AWS services from uploading dataset into S3 bucket to visualizing insights in Quicksight.The dataset used in this project is the data science job salaries from kaggle 'kaggle.com/datasets/ruchi798/data-science-job-salaries'. 

Variables include work_year, experience_level, enployement_type, job_type, salary, salary_currency, salary_in_usd, employee_residence, remote_ratio, company_location, company_size. We are interested in identifying the agrregate top 5 salaries by jobtile, sum of salaries in US dollar by experience, the remote work ratio, and the sum of salaries in US by employment type. The data analytics process is done as follow:

1- An IAM user is created to grant access permission to s3 buckets, and AmazonFullAccessPolicy is attached to it.

2- S3 buckets are created, file is uploaded to the S3 csv file bucket

3- Glue crawler is selected to retrieve data information schema automatically

4- Data query is performed in Athena, then results are loaded to S3 query results bucket

5- Data is extracted from S3 using Quicksight to build report



