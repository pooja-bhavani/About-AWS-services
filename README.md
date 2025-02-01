...........................# About IAM (Identity and Access Management)
![image](https://github.com/pooja-bhavani/About-AWS-services/assets/147735975/914d9c83-f1aa-43b4-b6f5-d4d0d9ed6a53)

About IAM users, groups, policies and roles.

IAM Users: We create an iam (Identity and Access Management) user for individuals within the organization and give access to resources. And the tasks will be performed as iam user and not root user for security purpose. IAM users will have permanent long-term credentails in the form of username and passward and for enhance security will enable multi-factor authentication (MFA).  

IAM Policies: IAM users can be directly assigned to iam policies. IAM Policies are used to define permissions for iam users, groups and roles. Eg: The policies specify what actions are allowed or denied on AWS resources.. Policies primarily handle authorization part. IAM Polocies controll access to AWS services without policies users cannot access the services.  

IAM Group: IAM group is the collection of iam users. By organizing iam users into groups, we can manage permissions collectively. Eg: we can create a developers group and add iam user who belong to development team. If the group requires access to any of the resources we can edit the group policy instead of manual process. 

IAM Roles: IAM roles are similar to iam users but is not associated with specific individual user. IAM Roles are used to grant permissions to services not users. Eg: I have you deployed an python application on EC2 instance and for some reason it wants access to database or S3 bucket in AWS. In this case will attach an IAM role to this EC2 instance to grant read or write permissions to database.

# About AWS Load Balancer Service
![image](https://github.com/pooja-bhavani/About-AWS-services/assets/147735975/cabca34a-b5e4-4a67-8f2c-35867717f782)
Load balancer is a service used to route the incoming traffic across all servers equally that are capable of fulfilling those requests in a manner that maximizes speed and capacity utilization. The load balancer ensures that no one server is overloded with the traffic.

# Types of load balancers? And difference between them.
Application Load Balancer (ALB): Layer 7
* ALB supports HTTP, HTTPS and Web socket traffic.
* Allows load balancing to multiple HTTP applications across different machines and same machines (EC2).
* The application servers don't see the client's ip directly.
* ALB is an internet-facing load balancer That allows users access the application so it is exposed to external world and can distribute incoming application traffic across multiple targets, such as EC2 instances, containers, and IP addresses. 
 
Network Load balancer (NLB): Layer 4
* It works at transport layer.
* It forwards TCP/UDP traffic to instances.
* Handles millions of requests per second.
* It has one static IP per AZ.
* NLB can be used to route traffic to internal resources within a network.

# AWS Data Sync Service
![image](https://github.com/pooja-bhavani/About-AWS-services/assets/147735975/525a9506-aab6-44a7-a7eb-9d2b2a54a51e)
* It is used to move large amount of data to and from places. Places would be on-permises/other cloud to AWS by connecting to server using (NFS, SMB, S3API)- needs agent. 
* It is an online data transfer service.
* AWS to AWS - does not require agent.

# AWS RDS Service
![image](https://github.com/pooja-bhavani/About-AWS-services/assets/147735975/a159cf83-1ac9-48ee-807c-e78adfe1f690)
About Relational database service(RDS)...!

RDS uses SQL as a query language and is an managed database service.
Use Cases:
* It is best suitable for online transaction processing(OLTP). 
* Multi-AZ for disaster Recovery
* Manages security and patching
* If multi-AZ option is selected with synchronous replication, so even on failover of an database we can still access service from standby replica.

Types of database engines
1. Postgres- It is very reliable and stable.
2. MySQL- It is used for web application.
3. Oracle- It manages data, prevents security breaches and provide seamless access to applications.
4. Aurora- For fast processing.

# RDS Proxy
![image](https://github.com/pooja-bhavani/About-AWS-services/assets/147735975/defdc672-a982-4e61-a70e-c7bd5aa1d470)

Lambda with RDS Proxy 
* If the lambda functions directly access your database , they may open too many connections under high load.
RDS Proxy
* It improves scability by pooling and sharing database connections, which can help in managing database connections more efficiently.
* To use RDS Proxy the lambda functions must be deployed in your VPC, because RDS Proxy are never publicly accessible.
* If we launch LF's publicly we will have no network connectivity to RDS Proxy.


# Brief about Amazon DynamoDB
![image](https://github.com/pooja-bhavani/About-AWS-services/assets/147735975/6fb7b83e-deb6-420d-bdb4-865e2dc172b9)
# It is an Non-Relational database service.
* DynamoDB is an high available service.
* Scales to massive workloads.
* Can scale millions of requests per seconds.
For Security
* It is integrated with IAM for security, authorization and administration.
* Low cost and auto-scaling capabilities.
* No maintenance or patching required, (don't need to provision database) just need to create table and specify capacity needs.
* DynamoDB is an schemaless (unstructured database).
* It is made of tables. Each table has a primary key (must be decided at the time of creation).
* Infinite no. of items.
* Maximum size of item must be 400 KB(DynamoDB is not for storing large objects).

# AWS Global Accelerator
![image](https://github.com/pooja-bhavani/About-AWS-services/assets/147735975/62f98f79-d1ba-421b-bbca-2f87d7726513)

AWS Global Accelerator
* Provides two types of IP Addresses:
1. Unicast IP - Here, one server holds one ip address. When a client sends request to this IP address, it's directed to the specific server associated with that IP.

2. Anycast IP - Here, all the servers hold the same ip address and client's request is routed to the nearest server.
* Instead of sending the request to public internet ALB directly talks to the closest edge locations.
*It improves performance and reliability.

# AWS Database Migration Service (DMS)
![image](https://github.com/pooja-bhavani/About-AWS-services/assets/147735975/ff9b772e-9a98-4c8f-ace2-56113c49db73)
Use Cases
* DMS is used to quickly and securely migrate databases to AWS.
* For continuous data replication.
1. To use Database migration service we need to create EC2 instance to perform the replication tasks.
2. To convert database from one engine to another we need to use SCT(Schema Conversion Tool).
# If we migrate the same database engine there is no need to use SCT
EG: PostgreSQL => RDS PostgreSQL it is same DB engine no need of SCT.
# If source and targetDB engine is different we use SCT.
EG: Oracle => PostgreSQL.


# AWS Redshift Service
![image](https://github.com/pooja-bhavani/About-AWS-services/assets/147735975/0b8ccd86-a167-400c-a6aa-05b33f2a9164)
* Redshift is based on PostgreSQL.
* It is used for Online Analytical Processing(OLAP) Workloads not Online Transaction Processing(OLTP). And scales PB's of data.
* It Provides SQL interface for performing Queries.
* It is used to scale and analyze large amount of data.
* It offers various security features, which involves encryption at rest, IAM integration, VPC isolation.
* It  is a powerful data warehousing solution for businesses seeking to analyze large amount of data.






