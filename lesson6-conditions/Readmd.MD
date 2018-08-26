## Conditions in Cloudformation

Conditions are one of the componenets of Cloudformation template along with Mappings, Resources etc.

> The optional Conditions section includes statements that define when a resource is created or when a property is defined. For example, you can compare whether a value is equal to another value. Based on the result of that condition, you can conditionally create resources.

### You can use the following intrinsic functions to define conditions:

- Fn::And

- Fn::Equals

- Fn::If

- Fn::Not

- Fn::Or



-----

In our example, we will prompt for 2 parameter values. Password and PasswordConfirm

```yaml
Parameters:
  Password:
    Type: String
  PasswordConfirm:
    Type: String
```

Then, in the **conditions section** we will check if these values are same or not.

```yaml
Conditions:
  MakeBucket:  !Equals [ !Ref Password, !Ref PasswordConfirm ]
```

The MakeBucket condition will be true if the values of the parameters are the same.

Finally, during creation of one of the resource( S3 bucket) we will put a conditon that we defined above. The resource is created **only if the conditions are met**

```yaml
Resources:
  S3Bucket:
    # This condition means that this bucket/resource will be created only if the 2 supplied parameters (passwords ) match
    Condition: MakeBucket
    Type: AWS::S3::Bucket
    Properties:
      AccessControl: PublicReadWrite
```

Use the full template named : conditions.yaml that's provided to launch a stack and try it out yourself. Feel free to add to this template and create cool things!

Any Questions? Use the issues tab on Github
Want to contribute? Open a pull request. 



