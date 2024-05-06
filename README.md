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

### Cloud tail running on the log group stream

![aws-1](https://github.com/Ham12-3/AWS_HANDS_ON_3/assets/93613316/e979be5b-1a19-4d81-b8b0-6ed782131588)


### Creation of an EC2 instance to use a cloudwatch alarm

![aws-2](https://github.com/Ham12-3/AWS_HANDS_ON_3/assets/93613316/3085cb0f-c1e8-423b-8271-da831e25fdc4)

### Selecting of metric for the cloudwatch alarms

![aws-3](https://github.com/Ham12-3/AWS_HANDS_ON_3/assets/93613316/b5d8a17d-e045-4024-99b4-4bbb9562d88d)


### The EC2 action for alarm in case it gets triggered

![aws-4](https://github.com/Ham12-3/AWS_HANDS_ON_3/assets/93613316/7367ca89-b91e-4d5a-aea4-8cdd5b09d251)

### The cloudwatch alarm has been finally created

![aws-5](https://github.com/Ham12-3/AWS_HANDS_ON_3/assets/93613316/e624973c-2782-4aae-a827-a5bf0bec05e4)

### Creation of an event bus from amazon eventbridge

![aws-6](https://github.com/Ham12-3/AWS_HANDS_ON_3/assets/93613316/a41a967c-952a-4bfd-8883-670b3c1cb7b0)

### Creation of eventbridge source to connect with partners such as salesforce, adobe, datadog and so on

![aws-7](https://github.com/Ham12-3/AWS_HANDS_ON_3/assets/93613316/efdf034e-dcf5-4c29-bcd4-c0992c403f17)


### Creation of a rule for the aws eventbridge

![aws-8](https://github.com/Ham12-3/AWS_HANDS_ON_3/assets/93613316/200f58e6-cb1e-4aab-9f4b-dab093a12ab8)

### Event rules pattern for the EC2 Instance State Change Notification

![aws-9](https://github.com/Ham12-3/AWS_HANDS_ON_3/assets/93613316/9e6ddfeb-bb27-4beb-ae48-525fcddeb974)

```JSON
{
  "version": "0",
  "id": "7bf73129-1428-4cd3-a780-95db273d1602",
  "detail-type": "EC2 Instance State-change Notification",
  "source": "aws.ec2",
  "account": "123456789012",
  "time": "2015-11-11T21:29:54Z",
  "region": "us-east-1",
  "resources": ["arn:aws:ec2:us-east-1:123456789012:instance/i-abcd1111"],
  "detail": {
    "instance-id": "i-abcd1111",
    "state": "stopped"
  }
}

```

### Finally the event rule has been created

![aws-10](https://github.com/Ham12-3/AWS_HANDS_ON_3/assets/93613316/aceed15f-a3d4-4434-9fed-6707177dae9a)


### When it comes to debugging especially on the production, it is kind of tedious, that is where the X-ray comes into place

With X-ray,
- You can understand troubleshooting performance
- Understand the microservices architecture
- Find errors and exceptions
- Know which users are imapacted by our error
- X-ray is compatible with EC2, lambda and several other AWS services.

#### Creation of a cloudformation stack to use with the X-ray

![image](https://github.com/Ham12-3/AWS_HANDS_ON_3/assets/93613316/f6594bf6-b77d-47bb-963f-a2c31796db83)

#### Selecting of subnets and VPCs

![image](https://github.com/Ham12-3/AWS_HANDS_ON_3/assets/93613316/ec359494-8601-4988-923c-32becec873c6)

#### The result of the cloudformation stack being created


![image](https://github.com/Ham12-3/AWS_HANDS_ON_3/assets/93613316/371b6ff6-1854-4d79-9a0d-242b1b0885c4)



### While playing the game, X-ray generated the service map, here is the map

![image](https://github.com/Ham12-3/AWS_HANDS_ON_3/assets/93613316/0ec390e9-5214-4607-92de-20a8e00d7ee9)

The insights and analytics

![image](https://github.com/Ham12-3/AWS_HANDS_ON_3/assets/93613316/c39276ac-5b11-4f50-af76-369eedbfa82b)











