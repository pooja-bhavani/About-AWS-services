# About IAM (Identity and Access Management)
About IAM users, groups, policies and roles.

IAM Users: We create an iam (Identity and Access Management) user for individuals within the organization and give access to resources. And the tasks will be performed as iam user and not root user for security purpose. IAM users will have permanent long-term credentails in the form of username and passward and for enhance security will enable multi-factor authentication (MFA).  

IAM Policies: IAM users can be directly assigned to iam policies. IAM Policies are used to define permissions for iam users, groups and roles. Eg: The policies specify what actions are allowed or denied on AWS resources.. Policies primarily handle authorization part. IAM Polocies controll access to AWS services without policies users cannot access the services.  

IAM Group: IAM group is the collection of iam users. By organizing iam users into groups, we can manage permissions collectively. Eg: we can create a developers group and add iam user who belong to development team. If the group requires access to any of the resources we can edit the group policy instead of manual process. 

IAM Roles: IAM roles are similar to iam users but is not associated with specific individual user. IAM Roles are used to grant permissions to services not users. Eg: I have you deployed an python application on EC2 instance and for some reason it wants access to database or S3 bucket in AWS. In this case will attach an IAM role to this EC2 instance to grant read or write permissions to database.

![image](https://github.com/pooja-bhavani/About-AWS-services/assets/147735975/1194512f-ee4e-4b54-b1dd-081d0e9c05af)

# AWS Data Sync Service
* It is used to move large amount of data to and from places. Places would be on-permises/other cloud to AWS by connecting to server using (NFS, SMB, S3API)- needs agent. 
* It is an online data transfer service.
* AWS to AWS - does not require agent.
