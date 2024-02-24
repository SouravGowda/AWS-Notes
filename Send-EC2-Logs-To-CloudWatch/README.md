# Send EC2 Logs To CloudWatch

> **Steps To Follow**

1. Create IAM Role With CloudWatch Log Policy
2. Attach Role To EC2 Instance
3. Install CloudWatch Agent
4. Install Nginx Web Server
5. Configure Json File For CloudWatch
6. Add Necessary Log Location In JSON File.

# Create IAM Role With Custom Policy

- Role Name - AWS-EC2-Log

```

{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": [
        "logs:CreateLogGroup",
        "logs:CreateLogStream",
        "logs:PutLogEvents",
        "logs:DescribeLogStreams"
    ],
      "Resource": [
        "arn:aws:logs:*:*:*"
    ]
  }
 ]
}

```

- Attach This Policy To EC2 Instance

- Install CloudWatch Agent On EC2

Ref: https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/verify-CloudWatch-Agent-Package-Signature.html

```

wget https://amazoncloudwatch-agent-ap-south-1.s3.ap-south-1.amazonaws.com/amazon_linux/amd64/latest/amazon-cloudwatch-agent.rpm

rpm -ivh amazon-cloudwatch-agent.rpm

```


