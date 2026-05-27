
Q> What is the relationship cardinality between an IGW and a VPC?
As explained in the class this is 1:1 relationship. one vpc can have only one IGW


Q>The route table already had one route before you added 0.0.0.0/0. What was it, what was its target, and why does it exist by default?

Within the VPC any node with any ip can access the machine

Q> Open the role and look at the Trust relationships tab. What does the JSON say? Explain in your own words what "trust policy" means and how it differs from "permissions policy."

{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Principal": {
                "Service": "ec2.amazonaws.com"
            },
            "Action": "sts:AssumeRole"
        }
    ]
}
The permissions policy grants the user of the role the needed permissions to carry out the intended tasks on the resource.
The trust policy specifies which trusted account members are allowed to assume the role.
(taken from https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles.html#id_roles_terms-and-concepts)

For the IAM role we have our permssion policy allows us to read,list s3 buckets and SSM managed instance core.
Trust policy allows us to 
  a. use this permission on ec2 instance
  b. This service can assume role to perform an action on ec2 instance


Q> What is the difference between an AWS managed policy, a customer managed policy, and an inline policy? When would you use each?
AWS managed policy: Standalone policies created by AWS.For example we used AmazonS3ReadOnlyAccess to read S3 buckets
Customer managed policy: Policy created for specific usecase. We created bootcamp-s3-readonly-onebucket for our usecase
Inline Policy: Policy created for a single IAM identity (user, group, or role) that maintains a strict one-to-one relationship between a policy and an identity.
(Answer is taken from https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_managed-vs-inline.html)

Q> What's the difference between a Gateway Endpoint and an Interface Endpoint? Which AWS services support Gateway Endpoints? Why might you still pay for an Interface Endpoint despite the cost?
Gateway EP: It uses AWS own's internal network which is free of charge
Interface EP: It uses external network which connects with AWS's services
(Its just a guess) we will pay for interface EP so private network can access EC2 services from outside its internal network.



