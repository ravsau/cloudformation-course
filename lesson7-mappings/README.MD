The purpose of this lesson is to make this template reusable for both windows and linux instance using the mapping feature and the findinmap function.




## 
In the other CF template example provided had the ami for EC2 instance hard coded so the user who deploys the template had no choice to choose the AMI. We could make the ami a parameter and let users enter the ami-id but we can go a step further and create a map for windows and linux.\
The users then will be prompted to select the type of instance with 2 options provided:  Windows(2008 Server) and Linux(Amazon AMI) . We'll do this with parameters.\

You can add more options by modifying this template.


## Official Reference 
https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/mappings-section-structure.html






 
