## Cloudformation Stack Policies 
https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/protect-stack-resources.html


-  If someone has a CloudFormation stack update permission, they can accidentally update a Stack. Stack policies can help you prevent accidental updates of your cloudformation stacks.

- `A stack policy is a JSON document that defines the update actions that can be performed on designated resources.`

- A stack policy is a JSON document that defines the AWS CloudFormation stack update actions that AWS CloudFormation users can perform and the resources that the actions apply to.

- **Note: A stack policy applies only during stack updates. It doesn't provide access controls like an AWS Identity and Access Management (IAM) policy. Use a stack policy only as a fail-safe mechanism to prevent accidental updates to specific stack resources. To control access to AWS resources or actions, use IAM.**


