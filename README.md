# Data-analysis-using-AWS-services-Athena-Glue-S3

This is an end-to-end simple AWS data analytics solutions, from uploading dataset into S3 bucket to visualizing insights in Quicksight.The dataset used in this scenario is the data science job salaries from kaggle 'kaggle.com/datasets/ruchi798/data-science-job-salaries'. 

Variables include work_year, experience_level, enployement_type, job_type, salary, salary_currency, salary_in_usd, employee_residence, remote_ratio, company_location, company_size. We are interested in identifying the agrregate top 5 salaries by jobtile, sum of Salary in US dollar by experience, the remote work ratio, and the sum of salaries in US by employment type. The analytics process will be done as follow:

1- An IAM user is created to grant access permission to s3 buckets, then attach AmazonFullAccessPolicy to the user.

2- Create s3 buckets, then upload file to S3 bucket csv file

3- Glue crawler is selected to retrieve data information schema automatically

4- Transform and query data in Athena, then load the results to S3 query results bucket

5- Extract data from s3 using Quicksight, and build report

