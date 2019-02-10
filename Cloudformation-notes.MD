Cloudformation Helper Scripts

Cloudformation stack metadata




## Wait condition vs Creation Policy
- They are very similar, as they pause the stack creation until certain software/apps/resources are created/provisioned completely.
- Creation policy are best practices for EC2 and autoscaling group. Wait condition are useful with on-prem resources.
- If the count for no of signals is not met then a rollback will occur on the stack
- AWS::CloudFormation::WaitCondition is a  resource and CreationPolicy  is an attribute




### Wait condition
- when you create a wait condition, you also need a wait condition handle

####  What is a waitcondition Handle?
The AWS::CloudFormation::WaitConditionHandle type has no properties. When you reference the WaitConditionHandle resource by using the Ref function, AWS CloudFormation returns a presigned URL. You pass this URL to applications or scripts that are running on your Amazon EC2 instances to send signals to that URL. An associated AWS::CloudFormation::WaitCondition resource checks the URL for the required number of success signals or for a failure signal.




### DependsOn Attribute
With the DependsOn attribute you can specify that the creation of a specific resource follows another. When you add a DependsOn attribute to a resource, that resource is created only after the creation of the resource specified in the DependsOn attribute.


### Update stack
- Update Command
- Change sets

### Security of the stack

- Termination Protection
