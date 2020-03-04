### Understanding IAM role

* Cross account access in IAM role.

We are trying to allow user David from account A to access s3 bucket in account B.

 ![](https://github.com/nanofaroque/nerd-read/blob/master/aws_solution_architect_prep/notes/iam/s3-role.png)

 * What is principle?
 
     Principle defines who or what can assume this role. In the example above,
 user david with account ID: 111111111 can assume this role to access S3 Get or List operations.

 * What is resource?
   This defines what resources above IAM role can access or do operation defined by the action section.  

As we have created an am role called s3-role in the account B. Now we have to add this to the David permission, so that he can assume the role called s3-role. How?
- we can take the ARN of the s3-role and added into the resource section of David like below:

![](https://github.com/nanofaroque/nerd-read/blob/master/aws_solution_architect_prep/notes/iam/david.png)

* How to Restrict Amazon S3 Bucket Access to a Specific IAM Role
https://aws.amazon.com/blogs/security/how-to-restrict-amazon-s3-bucket-access-to-a-specific-iam-role/

* IAM example with details 
http://docs.netapp.com/sgws-112/index.jsp?topic=%2Fcom.netapp.doc.sg-s3%2FGUID-D15FCD21-1869-4546-9234-56227206AB99.html
