# AWS Virtual Private Cloud (VPC)
![image](https://github.com/pooja-bhavani/About-AWS-services/assets/147735975/2ace1514-e8cf-4cde-82c3-5cb591615ae2)

* VPC is created in a region. It cannot be extended to another region.
* Maximum 5 VPC's can be created in a region. And 200 Subnets in 1 VPC Note: Subnets are AZ specific
* Maximum 5 Elastic ip addresses can be allocated in 1 account, if we require more we can request amazon and extend it.
* While creating a VPC once the primary Classless Inter-Domain Routing(CIDR) is submitted we cannot change it.
Eg: If I submit 10.000/16, than later I cannot change it. 
* If we want to change the CIDR we first need to create a CIDR and make it primary then only we can delete the before CIDR. 
* If we create a subnet and do not associate it with any route table then it will be associated with the default route table.
* VPC subnet ID should be different in both the subnets they shouldn't overlap.
* Network Address Translation (NAT) Gateway is always created in Public Subnet and used to provide internet access to instances in Private Subnet.
* Network Access Control List (NACL) works at subnet level to control inbound and outbound traffic within VPC.
* Internet Gateway (IGW) allows resources(Eg: EC2 instances) in VPC to connect to Internet.

# Difference between Security Groups and Network Access Control List(NACL).
* Security Groups- It operates at an Instance-level. They are stateful and have allow option only if you allow an incoming request, the response is automatically allowed. Because security groups are stateful we need to carefully define security group rules, based on application's security requirements.

* Network Access Control List (NACL)- It operates at an Subnet-level. Because NACL operates at subnet-level and are stateless the traffic is not automatically allowed, we must define both inbound and outbound rules in NACL to allow or deny traffic based on source and destination ip addresses, ports and protocols.

#b Introduction to AWS CloudFormation Service..!
![image](https://github.com/pooja-bhavani/About-AWS-services/assets/147735975/c4c672eb-11d0-4c11-92ad-2f144be6dd68)


CloudFormation templates helps us to create, manage and update resources. It implements the principle of (Iaac) Infrastructure as a code. It targets only AWS 
and does not support any other cloud provider. User can either write YAML or Json template because CF supports only these templates. When we submit the template to cloudformation it converts it into API calls.

Difference between CLI and CloudFormation template ?
CLI- It is used to perform quick actions Eg: To give the list of S3 Buckets available on AWS account or to get the details about resources.

CFT- It can be used to create multiple resources.


