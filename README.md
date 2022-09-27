# Data-analysis-using-AWS-services-Athena-Glue-S3-IAM-Quicksight

This is an end-to-end simple data analytics solution using AWS services. From uploading dataset to S3 bucket to visualizing insights in Quicksight.The dataset used in this project is the data science job salaries from kaggle 'kaggle.com/datasets/ruchi798/data-science-job-salaries'. 

Variables include work_year, experience_level, enployement_type, job_type, salary, salary_currency, salary_in_usd, employee_residence, remote_ratio, company_location, company_size. We are interested in identifying the agrregate top 5 salaries by jobtile. The data analytics process is done as follow:

Step 1- First, we create an IAM user to grant access permission to s3. In the search bar we type IAM > users > add users

![iam8](https://user-images.githubusercontent.com/59377247/191630320-238eed91-49d7-4cde-b0f5-ff2f5fd9091f.jpg)




1a- Set user details and access type then next permissions

![iam9](https://user-images.githubusercontent.com/59377247/191634641-ddc941c8-6eb0-45fd-be2f-1c9206e3bbbd.jpg)




1b- We proceed by choosing attach existing policies directly to the user since we already have a policy set up.

![Capture 2](https://user-images.githubusercontent.com/59377247/191635668-9a6117cd-49be-4e58-8ca4-39f370f66c35.jpg)



1c-Review all the details and create user
![iam13](https://user-images.githubusercontent.com/59377247/191636843-4e6acb89-6121-4456-81c8-ade5306d00d9.PNG)




1d- User successfully created

![iam14(hide account   access key)](https://user-images.githubusercontent.com/59377247/191638546-fe4a3be8-326d-4ecb-a641-bafc057f7172.jpg)




Step 2- S3 buckets are created. The data-science-salaries-bucket will hold the raw file, while the data-science-salaries-bucket-result will hold the query results      from  Athena.
![Capture1](https://user-images.githubusercontent.com/59377247/191639429-78f18f97-a733-4b52-9647-9c29309e62f4.PNG)




2a- The csv file is uploaded to the data-science-salaries-bucket

![Capture9](https://user-images.githubusercontent.com/59377247/191640923-c1b5901a-aee4-4ee2-9ab8-754beb51ef5b.PNG)




Step 3- Moving on to Athena. Before we can create our table we need to choose the bucket where the output query will be sent. In the Athena query editor we select          settings > manage > browse s3 to choose the appropriate bucket.





3a- In Athena data catalogue, we select >create table > AWS glue crawler > add crawler to retrieve data information schema automatically.
![Capture12](https://user-images.githubusercontent.com/59377247/191648372-a1413357-4181-4210-9556-3c2d05275c4d.PNG)




3b- Crawler succesfully created

![Capture (crawler was created) 14](https://user-images.githubusercontent.com/59377247/191651624-264aceea-5315-4000-b3bc-1335498b16f3.PNG)





Step 4- Data query is performed in Athena, then results are loaded to data-science-bucket-result 
![athena_queries 1PNG](https://user-images.githubusercontent.com/59377247/192561875-c7572441-b2ee-4344-a112-008b40792f24.PNG)




Step 5- Now we can extract data from S3 using Quicksight to built report. But before quicksight can read the s3 bucket, we have to make sure it has permission to do so. We navigate the account section by clicking on top right > manage quicksight > security & permissions > manage > select s3 bucket.

![quicksight_bucket_permission](https://user-images.githubusercontent.com/59377247/192400172-bfcaaf7f-d45e-4fd5-a3ab-363f903a745f.PNG)




5a- Next we set up a new data source to access S3 from quicksight new analysis > new dataset > S3 > upload Json manifest file > importe to spice




5b- After he data is imported to spice, we create report in Quicksight. Our interest was to identify top 5 popular data science salary in US based on job titlte.

![quicksight_dashboard](https://user-images.githubusercontent.com/59377247/192424686-7f6ff09c-274b-41cb-8888-514624db1916.PNG)



