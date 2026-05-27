Q> ou opened SSH from 0.0.0.0/0. In a real company, what would you restrict it to instead, and how?
As you explained in the class you dont want anyone other than the employees of comapny can access the internal ec2 instances of the company.0.0.0.0 allows any ip to access the bastion host. This restrcition is meant for users with certain ip can only access the internal machines 

Q> You copied a private key onto the bastion in Task 3.2. Name two reasons this is a bad practice and one alternative.
The key might be private to a user so by keeping it in bastion host you are exposing this key to everyone who has access to bastion host

Q> When would you choose a Gateway Endpoint vs an Interface Endpoint vs just using the NAT Gateway?
<I dont know the answer to this question now>

Q> VPC Peering vs Transit Gateway — when does Transit Gateway start to make sense?
VPC Peering is vpc to vpc communication only between 2 vpc. and transit gateway means you are creating hub where several vpc can communicate with each other.
Like you gave that example of packets flowing to singapre from europe via dubai.Dubai can be transit gateway for several VPC
