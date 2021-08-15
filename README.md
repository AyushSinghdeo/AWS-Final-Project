# AWS-Final-Project
Setup a system which do following things: If a file uploads to s3 then file name and file size will be automatically written in dynamo db. 1. Create Iam role full access of dynamo db (select lambda) 2. Create lambda function. 3. Deploy code in lambda. 4. Add trigger to s3 bucket


#FIRST STEP 
Create a lambda function

![1](https://user-images.githubusercontent.com/73579847/129484390-3e7603fa-7db5-416c-a1ce-be22faa4c441.jpg)

#SECOND STEP 2
Create a S3 Bucket

![2](https://user-images.githubusercontent.com/73579847/129484391-416fb8d4-be26-402e-ab5f-27eebaed55b9.jpg)

#THIRD STEP 3
Hook up the trigger

![3](https://user-images.githubusercontent.com/73579847/129484392-2182b00c-52ea-42a7-9009-8598c0dea8f4.jpg)

#FOURTH STEP 4
Upload the code to S3 Bucket that we created for lambda function

![4](https://user-images.githubusercontent.com/73579847/129484378-7ef8e14d-4696-47eb-9799-690e7cb4ef7c.jpg)


#STEP 1:
First we create a lambda function
![5](https://user-images.githubusercontent.com/73579847/129484379-936fa53c-f59b-4912-9359-739bfee9b09b.jpg)


For the run time we pick python 3.6 and what we need to do here is create a S3 get object permission, so click on policy templet and click on S3 read only permission
so that give the persiion that we need
![6](https://user-images.githubusercontent.com/73579847/129484380-95992d17-a2fb-4379-a515-7bc302ba6727.jpg)

![7](https://user-images.githubusercontent.com/73579847/129484381-9e150fd7-ca72-4495-8bfc-96af7f293f72.jpg)


#Step 2:
Then put in the handler code
![8](https://user-images.githubusercontent.com/73579847/129484382-87d221a0-ccea-48b8-826c-352fbbb0e227.jpg)
![9](https://user-images.githubusercontent.com/73579847/129484383-9409d785-36f3-427c-ac9c-e36c6ed27f79.jpg)

#Step 3:
Create a Bucket in S3
![10](https://user-images.githubusercontent.com/73579847/129484384-354d97cf-0334-4a5f-a339-3a3f5dc7628e.jpg)

#Step 4:
Go to bucket and click on property then go to Event section that going to hook up our S3 put to lambda function and clik on add a notification and we get to pick which type of notification we want to trigger on
![11](https://user-images.githubusercontent.com/73579847/129484385-53c4c652-1e36-49e4-bddd-930dc32424c7.jpg)


#Step 5:
Now upload a file to S3 bucket, so click on bucket and click upload then add files and add that TRANSACTION JSON file
![12](https://user-images.githubusercontent.com/73579847/129484386-a85ddf3f-fc1a-4dfa-9cfd-c514b4d35252.jpg)


#Step 6:
Go to monetering system to check to see if there actually any instance of the invoccation.
![13](https://user-images.githubusercontent.com/73579847/129484387-47928352-1d60-4914-8730-7ddf71ae923b.jpg)
So we have one data point signalling that there was one invacction

#Step 7
Go to Cloudwatch to see the logs that we emmited and verify that we succesfully handle the message and log the content, so go to log section and then click on the log group and click on the log stream. Here's the first line where i was printing the data object so that printing the content of JSON file and you cam see here i am iterating over the JSON content and extracting out the transacton type so the purchase and the refund and thats been extracted out here.
![14](https://user-images.githubusercontent.com/73579847/129484388-df785bda-d65c-49a4-b4b0-cf3500c3b07b.jpg)

