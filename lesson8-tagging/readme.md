In addition to any tags you define, AWS CloudFormation automatically creates the following stack\-level tags with the prefix ```aws:``` :
+ `aws:cloudformation:logical-id`
+ `aws:cloudformation:stack-id`
+ `aws:cloudformation:stack-name`

The `aws:` prefix is reserved for AWS use\. This prefix is case\-insensitive\. If you use this prefix in the `Key` or `Value` property, you cannot update or delete the tag\. Tags with this prefix don't count toward the number of tags per resource\.

All stack\-level tags, including automatically created tags, are propagated to resources that AWS CloudFormation supports\. Currently, tags are not propagated to Amazon EBS volumes that are created from block device mappings\.


Reference: 
https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-properties-resource-tags.html


### Lab Template( Also available as a seperate file on this folder). This will only work in the US-east-1 regino due to hardcoded AMI value

```
---
AWSTemplateFormatVersion: "2010-09-09"
Description: Create multiple AWS resources to test Cloudformation Tags propagation.

Resources:
  SimpleInstance:
    Type: AWS::EC2::Instance

    Properties:
      InstanceType: t2.micro
      ImageId: ami-8c1be5f6

  SimpleInstance1:
    Type: AWS::EC2::Instance

    Properties:
      InstanceType: t2.micro
      ImageId: ami-8c1be5f6

  S3Bucket:
    Type: AWS::S3::Bucket
    Properties:
      AccessControl: Private


```
2 Methods of deplyoing this template: 

1)  You can use this template and add tags to the Cloudformation Stack from the AWS Management Console. 
     OR 
2)  You can use the AWS CLI. 
    
    
Steps: 
-  Download the template above ( also available as a seperate file on this folder) 

- We will first look at the AWS CLI way of adding tags to the Stack and verify the tags propagation to the individual resources. Replace 

`aws cloudformation create-stack --stack-name tags-test8 --template-body file://tags-test-multiple-resource.yaml --tags Key=ProjectID,Value=53 Key=Team,Value=Security                                                         `

