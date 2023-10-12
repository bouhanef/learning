🚧
✅

# Description
Create a crud of s3 using the fllowing aws services
- Lambda AWS
- DynmoDB database
- API Gateway integration
- ReactNative application
- Put all in amplify 
- Add autehntication

The following features will be created in the API AWS Lambda :
- Read S3 Buckets
- Read S3 Bucket structure (directories)
- Read S3 object content
- synchronise S3 in config

# Details
## Lambda function
- Create Strategy
- Create role
- Create Lambda function

### Create policy policy-s3-util
- Name : policy-s3-util
- Content :
```json
{{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": "logs:CreateLogGroup",
            "Resource": "arn:aws:logs:eu-west-1:089463998915:*"
        },
        {
            "Effect": "Allow",
            "Action": [
                "logs:CreateLogStream",
                "logs:PutLogEvents"
            ],
            "Resource": "arn:aws:logs:eu-west-1:089463998915:log-group:/aws/lambda/function-s3-util:*"
        },
        {
            "Effect": "Allow",
            "Action": "s3:*",
            "Resource": "*"
        }
    ]
}
```

### Create role role-s3-util
- Name : role-s3-util
- Use policy stategy-s3-util

## DynmoDB
- Create table for objects : Content of each bucket, grouped by bucket name, containing root object. 

### Create table for objects dynamo-s3-util-structure
- id
- bucket : group by bucket name
- parent : group by folder
- name
- isFolder
- extention
- fullName
- fullPath

### Create Lambda function function-s3-util
- Name : function-s3-util
- Use role role-s3-util
- Tasks
    - Read S3 Buckets
    - Read S3 Bucket structure (directories)
    - Read S3 object content
    - synchronise S3 in config

## API Gateway integration
- Create api gateway

### api-s3-utility

## ReactNative application
- Create react native application 
- Create list folders and files
- Create content viewer

## Put all in amplify 
- Add amplify project
- Add function with DynmoDB
- Add API
- Add autehntication