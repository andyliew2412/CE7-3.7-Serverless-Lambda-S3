# CE7 Assignment 3.7 

# Create serverless lambda function to convert csv file into txt file format and the input and output fille will store in S3 bucket separately.

1) Create and clone new github repository.

2) Add the "serverless-lambda-s3" folder inside the local git folder.

3) Locate to serverless-lambda-s3 folder and edit the serverless.yml. modify below setting
-         service: andyliew-serverless-lambda-s3
          runtime: nodejs20.x 
          region: us-east-1
          name: andyliewconvertCSVToTxt
          bucket: andyliew-serverless-bucket-input
          BucketName: andyliew-serverless-bucket-output

4) Setup the package and dependency
-     npm install -g serverless
      npm install
      npm ci

5) To deploy serverless into AWS run below command
-      serverless deploy -v

6) The serverless deployment successfully, below this will be created at AWS services.
    - S3 input bucket
    - S3 output bucket
    - Lambda function

7) To test the Lambda function, drag and drop the CSV file (sampleData.csv) from the git repository folder into S3 input bucket.Once uploaded is done, go to the S3 output bucket, you will see the txt file (sampleData.txt) generated.

8) Go the the Lambda function and check the CloudWatch for the log event and the metrics.

9) To clean up for the exercise.
    - S3 Bucket - manually delete the all file in both input and output S3 bucket
    - Serverless - run below command to clean up
