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
* Direct connect provides a dedicated private connection from remote network into VPC.
* To establish a connection, we need to set up a Direct Connect connection at the AWS side and configure the appropriate customer gateway device at the client side.
* To connect multiple VPC's in different regions with same account we use direct connect gateway.
* It supports both IPv4 and IPv6.

# AWS Backup...!
![image](https://github.com/pooja-bhavani/About-AWS-services/assets/147735975/c1b1701c-b2d0-46cc-aec7-e5ae5bf8469a)
* Supported services by AWS Backup:
* Amazon EC2, Elastic Block Store (EBS)
* Amazon S3 focuses on object-level backups in S3
* Amazon RDS (Relational Database Service), Aurora  (a MySQL and PostgreSQL-compatible relational database)
* DynamoDB (NoSQL database), DocumentDB (with MongoDB compatibility), Amazon Neptune (graph database)
* Amazon EFS, FSX for (lustre and windows file server)
* AWS Storage Gateway for (hybrid cloud storage)

# Cross-Region Backups
* Supports cross-account backups- Supports the ability to backup and restore resources across AWS accounts for better security and management.

* Cross-Region Backups- AWS Backup supports the automatic copying of backups across AWS regions to enhance disaster recovery capabilities.

* Point in time Recovery (PITR) for available supported services like Aurora, Amazon DynamoDB and Amazon RDS.

* On-Demand and Scheduled Backups- AWS Backup allows for both manual (on-demand) and automated (scheduled) backups. You can define backup policies and schedules to ensure regular and reliable data protection.

* Backup Policies- Can create and manage backup policies using AWS Backup's backup plans to standardize and automate backup processes. 

* Compliance and Security- AWS Backup integrates with AWS Identity and Access Management (IAM) for access control and AWS Key Management Service (KMS) for encryption.

# Disaster Recovery...!
![image](https://github.com/pooja-bhavani/About-AWS-services/assets/147735975/632a570c-c83a-46d8-a3b7-15ce868cd1af)
* There are two terms 
1. RPO- Recovery Point Objective: The maximum acceptable amount of data loss measured in time.
2. RTO- Recovery Time Objective: The maximum acceptable amount of time to restore the business process after a disaster.

Tips for Disaster Recovery
* Backups- Elastic Block Store (EBS snapshots) to backup EBS volumes, RDS automated backups/snapshots etc.
* Regular pushes to S3, S3 IA (Infrequent Access), Glacier for cost-effective and durable storage, cross-region replication.

# High Availability 
* Use route53 to migrate Domain Name System (DNS) over from region to region to manage DNS failover.
* RDS multi-AZ configuration to enhance database availability , EFS high-availability file storage, S3 for durability.
* Site-to-site VPN as a recovery to direct connect  for reliable network connectivity during failures.

# Replication 
* RDS replication to create read replicas and enhance database availability, Aurora+Global database feature.
* Storage gateway.
