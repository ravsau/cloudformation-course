# Working with Nested Stacks<a name="using-cfn-nested-stacks"></a>

*Nested stacks* are stacks created as part of other stacks\. You create a nested stack within another stack by using the [`AWS::CloudFormation::Stack`](aws-properties-stack.md) resource\.

As your infrastructure grows, common patterns can emerge in which you declare the same components in multiple templates\. You can separate out these common components and create dedicated templates for them\. Then use the resource in your template to reference other templates, creating nested stacks\.

In our example, we will have an security group in the root stack and we will have an EC2  instance in the child stack. 



Nested stacks can themselves contain other nested stacks, resulting in a hierarchy of stacks, as in the diagram below\. The *root stack* is the top\-level stack to which all the nested stacks ultimately belong\. In addition, each nested stack has an immediate *parent stack*\. For the first level of nested stacks, the root stack is also the parent stack\. in the diagram below, for example:
+ Stack A is the root stack for all the other, nested, stacks in the hierarchy\.
+ For stack B, stack A is both the parent stack, as well as the root stack\.
+ For stack D, stack C is the parent stack; while for stack C, stack B is the parent stack\.

![\[Nested stacks, which are created as part of another stack, have an immediate parent stack, as well as the top-level root stack.\]](http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/images/cfn-console-nested-stacks.png)

## Reference
https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-cfn-nested-stacks.html
