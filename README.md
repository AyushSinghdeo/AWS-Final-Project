# AWS-Final-Project
Setup a system which do following things: If a file uploads to s3 then file name and file size will be automatically written in dynamo db. 1. Create Iam role full access of dynamo db (select lambda) 2. Create lambda function. 3. Deploy code in lambda. 4. Add trigger to s3 bucket
#FFIRST STEP 
Create a lambda function

#SECOND STEP 2
Create a S3 Bucket


#THIRD STEP 3
Hook up the trigger

#FOURTH STEP 4
Upload the code to S3 Bucket that we created for lambda function


#STEP 1:
First we create a lambda function


For the run time we pick python 3.6 and what we need to do here is create a S3 get object permission, so click on policy templet and click on S3 read only permission
so that give the persiion that we need



#Step 2:
Then put in the handler code

#Step 3:
Create a Bucket in S3

#Step 4:
Go to bucket and click on property then go to Event section that going to hook up our S3 put to lambda function and clik on add a notification and we get to pick which type of notification we want to trigger on


#Step 5:
Now upload a file to S3 bucket, so click on bucket and click upload then add files and add that TRANSACTION JSON file


#Step 6:
Go to monetering system to check to see if there actually any instance of the invoccation.

So we have one data point signalling that there was one invacction

#Step 7
Go to Cloudwatch to see the logs that we emmited and verify that we succesfully handle the message and log the content, so go to log section and then click on the log group and click on the log stream. Here's the first line where i was printing the data object so that printing the content of JSON file and you cam see here i am iterating over the JSON content and extracting out the transacton type so the purchase and the refund and thats been extracted out here.
