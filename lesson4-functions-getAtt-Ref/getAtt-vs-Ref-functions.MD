## Cloudformation Intrinsic Functions : GetAtt vs Ref


AWS CloudFormation provides several built-in functions that help you manage your stacks\

Among them, 2 of the most used are Fn::GetAtt and Ref . I've gotten feedbacks when teaching that these 2 look so similar and when should you use which one? I had a similar confision at first.



## Ref:

### This is how you declare a Ref function:

- JSON
  - { "Ref" : "logicalName" }

- YAML
  - Ref: logicalName

Ref is used to refer to the logical name of another resource. Ref function returns a value that's predefined for each resource.

- For example if your EC2 instances had a logical name of EC2 :
  - Ref: EC2 will return the InstanceId 
- Ref on AWS::EC2::EIP  will return the IP address

Here's a short list of predefined values that will be returned when you use a Ref function:
- **AWS::EC2::Subnet :** Subnet ID
- **AWS::EC2::VPC:** VPC ID
- **AWS::S3::Bucket:** Name of the bucket
- **AWS::IAM::User:** User Name



## Fn:GetAtt

### This is how you declare/use a Fn:GetAtt function:


- **JSON**
  - { "Fn::GetAtt" : [ "logicalNameOfResource", "attributeName" ] }
- **YAML**

  - Fn::GetAtt: [ logicalNameOfResource, attributeName ]
  
  
 Unlike Ref , Fn: GetAtt has 2 fields where you put the logical name of the resource in the first field and the desired attribute name in the second field. You may choose from  available attributes.

 For example , in the case of EC2 you can choose from these attributes:
 


**1) AvailabilityZone**

The Availability Zone where the instance that you specified is launched.

**Returns:** us-east-1a



**2) PrivateDnsName**

The private DNS name of the instance that you specified.

**Returns something like :** ip-10-1-3-4.ec2.internal



**3) PublicDnsName**

The public DNS name of the instance that you specified.

**Returns something like :** ec2-10-20-30-40.compute-1.amazonaws.com



**4) PrivateIp**

The private IP address of the instance that you specified.

**Returns something like:** 10.24.34.0



**5) PublicIp**

The public IP address of the instance that you specified.
**Returns something like:** 35.36.2.9


## Conclusion
I hope this clears up what the difference between these two functions are. Or I hope ( if you've never worked with cloudformation functions) you get an idea of what cloudformation functions can do.

Thanks and see you in the next lesson!

