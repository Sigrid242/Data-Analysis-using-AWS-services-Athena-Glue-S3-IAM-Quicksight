# Data-analysis-using-AWS-services-Athena-Glue-S3-Quicksight

This is an end-to-end simple data analytics solution using AWS services from uploading dataset into S3 bucket to visualizing insights in Quicksight.The dataset used in this project is the data science job salaries from kaggle 'kaggle.com/datasets/ruchi798/data-science-job-salaries'. 

Variables include work_year, experience_level, enployement_type, job_type, salary, salary_currency, salary_in_usd, employee_residence, remote_ratio, company_location, company_size. We are interested in identifying the agrregate top 5 salaries by jobtile, sum of salaries in US dollar by experience, the remote work ratio, and the sum of salaries in US by employment type. The data analytics process is done as follow:


Step 1- First, we create an IAM user to grant access permission to s3 buckets. In the search bar we type IAM > users > add users, and AmazonFullAccessPolicy is          attached to it.

![iam8](https://user-images.githubusercontent.com/59377247/191630320-238eed91-49d7-4cde-b0f5-ff2f5fd9091f.jpg)



1a- Set user details and access type then next permissions

![iam9](https://user-images.githubusercontent.com/59377247/191634641-ddc941c8-6eb0-45fd-be2f-1c9206e3bbbd.jpg)



1b- We proceed by attaching policy to the user since we already have a policy set up.

![Capture 2](https://user-images.githubusercontent.com/59377247/191635668-9a6117cd-49be-4e58-8ca4-39f370f66c35.jpg)



1c-Review all the details and then create user
![iam13](https://user-images.githubusercontent.com/59377247/191636843-4e6acb89-6121-4456-81c8-ade5306d00d9.PNG)



1d- User successfully created

![iam14(hide account   access key)](https://user-images.githubusercontent.com/59377247/191638546-fe4a3be8-326d-4ecb-a641-bafc057f7172.jpg)



Step 2- S3 buckets are created. The data-science-salaries-bucket will hold the raw file, while the data-science-salaries-bucket-results will hold the query results      from  Athena.
![Capture1](https://user-images.githubusercontent.com/59377247/191639429-78f18f97-a733-4b52-9647-9c29309e62f4.PNG)



2a- The csv file is uploaded to the data-science-salaries-bucket

![Capture9](https://user-images.githubusercontent.com/59377247/191640923-c1b5901a-aee4-4ee2-9ab8-754beb51ef5b.PNG)



Step 3- Moving on to Athena. Before we can create our table we need to choose the bucket where the output query will be sent. In the Athena query editor we select          settings > manage > browse s3 to choose the appropriate bucket.

3a- In Athena data catalogue, we select >create table > AWS glue crawler > add crawler to retrieve data information schema automatically.
![Capture12](https://user-images.githubusercontent.com/59377247/191648372-a1413357-4181-4210-9556-3c2d05275c4d.PNG)



3b- Crawler succesfully created

![Capture (crawler was created) 14](https://user-images.githubusercontent.com/59377247/191651624-264aceea-5315-4000-b3bc-1335498b16f3.PNG)



4- Data query is performed in Athena, then results are loaded to data-science-bucket-results 

5- Data is extracted from S3 using Quicksight to build report



