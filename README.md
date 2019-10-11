# Using CloudFormation VPC with private and public subnets

A VPC is a virtual network inside AWS where you can isolate your setup using private IP addresses. A VPC consists of several subnets.
A public subnet has a direct route to the Internet. As long as your EC2 instances have an public IP they can communicate (in and out) with the Internet. A private subnet does not have a route to the Internet. Instances in private subnets can not be accessed from the public Internet. 
If you want to access the Internet from a private subnet you need to create a NAT gateway/instance. 
You can deploy a bastion host/instance to reduce the attack surface of internal applications.

## Infrastructure Architecture

 Images/VPC-Template.png

## Parameters


# Using CloudFormation VPC endpoints with S3

One of the most common use cases for the new CloudFormation VPC endpoints is to allow resources within a VPC to signal back to CloudFormation CreationPolicy and WaitConditionHandles without needing to route across the public internet.
Today we are simplifying access to S3 resources from within a VPC by introducing the concept of a VPC Endpoint. These endpoints are easy to configure, highly reliable, and provide a secure connection to S3 that does not require a gateway or NAT instances.
EC2 instances running in private subnets of a VPC can now have controlled access to S3 buckets, objects, and API functions that are in the same region as the VPC. You can use an S3 bucket policy to indicate which VPCs and which VPC Endpoints have access to your S3 buckets.   

## Infrastructure Architecture   


## Parameters



### For more information:
- [Setting Up VPC Endpoints for AWS CloudFormation](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/cfn-vpce-bucketnames.html).
- [Interface VPC Endpoint (for CloudFormation)](https://docs.aws.amazon.com/vpc/latest/userguide/vpce-interface.html)
- [Gateway VPC Endpoints (for S3)](https://docs.aws.amazon.com/vpc/latest/userguide/vpce-gateway.html)
- [AWS::EC2::VPCEndpoint](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-ec2-vpcendpoint.html)
- [Creating Wait Conditions in a Template](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-cfn-waitcondition.html)
