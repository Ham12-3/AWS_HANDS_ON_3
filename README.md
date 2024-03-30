# Hands on Contd

## AWS SQS


### Creation of queue in SQS

![aws-9](https://github.com/Ham12-3/AWS_HANDS_ON_3/assets/93613316/9da044f8-d0ad-4232-852e-e5e9383c2c50)


### Queue successfully created

![aws-10](https://github.com/Ham12-3/AWS_HANDS_ON_3/assets/93613316/643bd71a-6c5e-4d40-9042-df0ed5627dae)

### Queue access policy

![aws-11](https://github.com/Ham12-3/AWS_HANDS_ON_3/assets/93613316/4d3f7795-eba7-463d-ab55-291b114f9ea9)


### Creation of an event notification in S3 to connect to the SQS Queue

![aws-12](https://github.com/Ham12-3/AWS_HANDS_ON_3/assets/93613316/c96956d0-e6a1-4286-af64-b134c0f4ea9b)

### SQS Policy to allow the sending of information


```JSON
{
  "Version": "2012-10-17",
  "Id": "example-ID",
  "Statement": [
    {
      "Sid": "__owner_statement",
      "Effect": "Allow",
      "Principal": {
        "Service": "s3.amazonaws.com"
      },
      "Action": "SQS:SendMessage",
      "Resource": "arn:aws:sqs:us-east-1:058264276076:DemoQueue",
      "Condition": {
        "StringEquals": {
          "aws:SourceAccount": "058264276076"
        },
        "ArnLike": {
          "aws:SourceArn": "arn:aws:s3:*:*:demo-mide-bucket"
        }
      }
    }
  ]
}
```

### Event notification successfully created

![aws-13](https://github.com/Ham12-3/AWS_HANDS_ON_3/assets/93613316/a5bf54e5-f68c-493a-a99d-c7ce66737862)

### Then we can now poll messages we got from the S3

![aws-14](https://github.com/Ham12-3/AWS_HANDS_ON_3/assets/93613316/f01c0746-3850-46e2-8e1a-a4e7b4c4a0f5)



