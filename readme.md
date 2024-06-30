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

# Introduction to AWS CloudFormation Service..!
![image](https://github.com/pooja-bhavani/About-AWS-services/assets/147735975/c4c672eb-11d0-4c11-92ad-2f144be6dd68)


CloudFormation templates helps us to create, manage and update resources. It implements the principle of (Iaac) Infrastructure as a code. It targets only AWS 
and does not support any other cloud provider. User can either write YAML or Json template because CF supports only these templates. When we submit the template to cloudformation it converts it into API calls.

Difference between CLI and CloudFormation template ?

CLI- It is used to perform quick actions Eg: To give the list of S3 Buckets available on AWS account or to get the details about resources.

CFT- It can be used to create multiple resources.

# AWS Transfer Family
![image](https://github.com/pooja-bhavani/About-AWS-services/assets/147735975/5a2b0af8-e946-4aca-947a-ab550765bc06)
* Transfer Family is used to transfer files in and out of S3 and Elastic File System(EFS) using File Transfer Protocol(FTP)
* AWS Transfer Family Supports
1. FTP- File Transfer Protocol (it is unencrypted form)
Unencrypted: Transfers files without encryption, makes it suitable for non-sensitive data transfers.
2. SFTP- Secure File Transfer Protocol (it is encrypted form)
Encrypted: Provides secure file transfer by encrypting both commands and data, ensuring data privacy.

3. FTPS over SSL/TLS- File Transfer Protocol (it is over Secure Socket Layer SSL encrypted form)
SSL/TLS Encrypted: Enhances security by utilizing Secure Socket Layer / Transport Layer Security (TLS) for encrypting the FTP data transfers.

* It is reliable, scalable and highly available.

# AWS Glue
![image](https://github.com/pooja-bhavani/About-AWS-services/assets/147735975/f9748d81-88ec-4f0d-b64b-570f84ff3929)
* Glue is used to Extract, Transform/ Filter and Load data to destinations.
Eg: We can use glue to load data from S3 bucket or RDS to destinations like Redshift.
* It is a Serverless service, there is no infrastructure to manage 
* Clients can prepare and transform data for analytics.
* It can automatically detect and catalog data across various data sources, including S3, RDS, Redshift, and others.
* It allows us to schedule ETL jobs to run at specified times or intervals.

# VPC Flow Logs
![image](https://github.com/pooja-bhavani/About-AWS-services/assets/147735975/bca2bad4-3736-497f-8eed-41f5e19fac49)
* VPC Flow Logs capture information about the IP traffic going to and from network interfaces in your VPC.
* It can be setup at VPC/Subnet/Elastic Network Interface(ENI) level to except or reject traffic.
Use Cases
* Identify and investigate potential security threats or unusual activities.
* Troubleshoot network misconfigurations and application performance issues.
* It helps to identify attacks, analyze using Athena or CloudWatch log insights.

# AWS Direct Connect...!
![image](https://github.com/pooja-bhavani/About-AWS-services/assets/147735975/4f68b655-c47d-4a0c-86e5-e6aa1250ac9c)

