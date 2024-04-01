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

### Creation of a DLQ
![aws-15](https://github.com/Ham12-3/AWS_HANDS_ON_3/assets/93613316/a7a4e554-f0a4-4cb4-a851-af19a04b5265)


![aws-16](https://github.com/Ham12-3/AWS_HANDS_ON_3/assets/93613316/3479aee5-275e-4725-861a-b9655c0183f9)

### DLQ redrive hands on

![aws-17](https://github.com/Ham12-3/AWS_HANDS_ON_3/assets/93613316/cd586185-2b41-40b5-be4c-9ff60679df91)


### DelayQueue in action delaying the sending of message to consumers for 10 seconds

![aws-17](https://github.com/Ham12-3/AWS_HANDS_ON_3/assets/93613316/6ced54ea-02f5-446f-880c-4a0bc679d0fd)


### Long Polling technique to increase a message wait time

![aws-18](https://github.com/Ham12-3/AWS_HANDS_ON_3/assets/93613316/4a63f98f-bea4-4245-bcb7-675e985c3371)

### Creation of a FIFO Queue with message deduplication enabled

![aws-19](https://github.com/Ham12-3/AWS_HANDS_ON_3/assets/93613316/9f81919e-1bbd-4f47-bd0a-a37795a8c7e3)



### Creating an AWS SNS topic named MyFirstTopic using Standard instead of FIFO

![aws-20](https://github.com/Ham12-3/AWS_HANDS_ON_3/assets/93613316/1acd822d-c8b6-450d-9bb7-e2bd5f7a1206)

### Email  from the subscription I recently created

![aws-21](https://github.com/Ham12-3/AWS_HANDS_ON_3/assets/93613316/1de1b20f-d0db-462b-9c93-eb43d053fa5c)


### Successfully confirmed subscription


![aws-22](https://github.com/Ham12-3/AWS_HANDS_ON_3/assets/93613316/809555ea-211d-4ba6-a57e-1bb5edd8e96d)


### Publishing a message using MyFirstTopic SNS topic after just creating a subscription

![aws-23](https://github.com/Ham12-3/AWS_HANDS_ON_3/assets/93613316/9a36b163-a7b9-4a0a-971a-0306bff34844)

### Successfully recieved into my message

![aws-24](https://github.com/Ham12-3/AWS_HANDS_ON_3/assets/93613316/eee456c7-9056-4524-a311-06e5b4bef273)


### Creation of Kinesis data stream shard

![aws-25](https://github.com/Ham12-3/AWS_HANDS_ON_3/assets/93613316/19f242f7-8931-4675-aed4-b9e282143b03)

### Exisiting Cloudwatch log groups 

![aws-26](https://github.com/Ham12-3/AWS_HANDS_ON_3/assets/93613316/1a91f067-61f8-4cdf-a406-184383b13982)

![aws-27](https://github.com/Ham12-3/AWS_HANDS_ON_3/assets/93613316/06d81313-8d74-46d9-9776-c49357e7a44a)


### Creation of a metric filter

![aws-28](https://github.com/Ham12-3/AWS_HANDS_ON_3/assets/93613316/9e60e737-bc15-459d-8374-d65b5fcd1f94)

### Assigning of Metric Filter

![aws-29](https://github.com/Ham12-3/AWS_HANDS_ON_3/assets/93613316/8d1de02d-ad34-4f44-9127-d09b2fbd2d77)


### Our metric filter is finally created

![aws-30](https://github.com/Ham12-3/AWS_HANDS_ON_3/assets/93613316/7e46fc0f-bd21-41f5-bf91-b4a602fe6e60)


