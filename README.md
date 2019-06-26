# aws
AWS Tutorial

#### AWS Certifications

https://aws.amazon.com/certification/

**AWS Solution Architect Certification : **
https://aws.amazon.com/certification/certified-solutions-architect-associate/

#### AWS Certification and Exam Details

https://d0.awsstatic.com/training-and-certification/docs-sa-assoc/AWS_certified_solutions_architect_associate_blueprint.pdf

#### AWS Solutions Architect – Associate (SAA-C01) Sample Exam :

https://d1.awsstatic.com/training-and-certification/docs/AWS_Certified_Solutions_Architect_Associate_Sample_Questions.pdf

#### Exam Rediness Video Course from Amazon

https://www.aws.training/learningobject/curriculum?id=20685

### Reference Materials:

**Free Practice Test Questions : **
		20 Questions : https://awspro.academy/aws-certified-solutions-architect-associate-exam-free-20-questions/
		10 Questions: https://phoenixts.com/resources/aws-associate-assessment/
		20 Questions : https://linuxacademy.com/blog/certifications/test-your-knowledge-with-our-aws-practice-quiz/

**AWS Cheat Sheets :** https://tutorialsdojo.com/aws-cheat-sheets/

**Paid Training (I Followed) : **

https://www.udemy.com/aws-certified-solutions-architect-associate-saa-c01

**Paid Practice Paper (I Followed) : **
https://www.amazon.com/dp/B07TG845T6

### Last Minutes Points to Remember

- Use ElastiCache if the read data is static and read often. For example, if you are selling products and the products don't have changing details (Prices, titles, descriptions) use ElastiCache.

- Use a read replica for the other cases. For example, you have a content sharing service where many users are looking at many other users content (Tumblr for example). Caching all of the different users data would take up too much space, but allowing other users to read from a different database would make the strain on one database much less.

- Elastic Beanstalk is a PaaS-like layer ontop of AWS's IaaS services which abstracts away the underlying EC2 instances, Elastic Load Balancers, auto scaling groups, etc. This makes it a lot easier for developers, who don't want to be dealing with all the systems stuff, to get their application quickly deployed on AWS. It's very similar to other PaaS products such as Heroku, EngineYard, Google App Engine, etc. With Elastic Beanstalk, you don't need to understand how any of the underlying magic works.

- CloudFormation, on the other hand, doesn't automatically do anything. It's simply a way to define all the resources needed for deployment in a huge JSON file. So a CloudFormation template might actually create two ElasticBeanstalk environments (production and staging), a couple of ElasticCache clusters, a DyanmoDB table, and then the proper DNS in Route53. I then upload this template to AWS, walk away, and 45 minutes later everything is ready and waiting. Since it's just a plain-text JSON file, I can stick it in my source control which provides a great way to version my application deployments. It also ensures that I have a repeatable, "known good" configuration that I can quickly deploy in a different region.

- There are certain metrics that are not readily available in CloudWatch. Here's the list of custom metrics that you can set up:

- - Memory utilization
- - Disk swap utilization
- - Disk space utilization
- - Page file utilization
- - Log collection

- S3 Select is an Amazon S3 feature that makes it easy to retrieve specific data from the contents of an object using simple SQL expressions without having to retrieve the entire object. Amazon Redshift Spectrum is a feature of Amazon Redshift that enables you to run queries against exabytes of unstructured data in Amazon S3 with no loading or ETL required.

- For tasks that use the Fargate launch type, the only supported method is referencing a Systems Manager Parameter Store parameter. This feature also requires that your task use platform version 1.3.0 or later.

- Enhanced Monitoring is a feature of RDS and not of CloudWatch.

- Lambda@Edge lets you run Lambda functions to customize the content that CloudFront delivers

- In addition to the network and transport layer protections that come with Standard, AWS Shield Advanced provides additional detection and mitigation against large and sophisticated DDoS attacks, near real-time visibility into attacks, and integration with AWS WAF, a web application firewall.

- AWS WAF can help you block common attack patterns to your VPC such as SQL injection or cross-site scripting, this is still not enough to withstand DDoS attacks. 

- Canary: Traffic is shifted in two increments. You can choose from predefined canary options that specify the percentage of traffic shifted to your updated Lambda function version in the first increment and the interval, in minutes, before the remaining traffic is shifted in the second increment.

- Linear: Traffic is shifted in equal increments with an equal number of minutes between each increment. You can choose from predefined linear options that specify the percentage of traffic shifted in each increment and the number of minutes between each increment.

- AWS IoT Core is a managed cloud service that lets connected devices easily and securely interact with cloud applications and other devices. AWS IoT Core provides secure communication and data processing across different kinds of connected devices and locations so you can easily build IoT applications.

- By default, all data stored by AWS Storage Gateway in S3 is encrypted server-side with Amazon S3-Managed Encryption Keys (SSE-S3). Amazon RDS, ECS and Lambda all support encryption, you still have to enable and configure them first with tools like AWS KMS to encrypt the data at rest.

- CloudFront and Elastic Load Balancing are the two AWS services that support Perfect Forward Secrecy.

- MX record specifies the mail server responsible for accepting email messages on behalf of a domain name. 

- You only need to enable Cross-Origin Resource Sharing (CORS) when your client web application on one domain interacts with the resources in a different domain.

- An elastic network interface (ENI) is a logical networking component in a VPC that represents a virtual network card. You can attach a network interface to an EC2 instance in the following ways:

- - When it's running (hot attach)
- - When it's stopped (warm attach)
- - When the instance is being launched (cold attach).

- BLOB data is too large a chunk of data to be put into a NoSQL database such as DynamoDB.

- Remember that an 80 TB Snowball appliance and 100 TB Snowball Edge appliance only have 72 TB and 83 TB of usable capacity respectively\

- You can use Amazon Data Lifecycle Manager (Amazon DLM) to automate the creation, retention, and deletion of snapshots taken to back up your Amazon EBS volumes. Automating snapshot management helps you to:

- If you have a bastion host in AWS, it is basically just an EC2 instance. It should be in a public subnet with either a public or Elastic IP address with sufficient RDP or SSH access defined in the security group. Users log on to the bastion host via SSH or RDP and then use that session to manage other hosts in the private subnets. 

- When failing over, Amazon RDS simply flips the canonical name record (CNAME) for your DB instance to point at the standby, which is in turn promoted to become the new primary. 

- Security Groups usually control the list of ports that are allowed to be used by your EC2 instances and the NACLs control which network or list of IP addresses can connect to your whole VPC.

- Instances that you launch into a nondefault subnet in a default VPC don't receive a public IPv4 address or a DNS hostname. You can change your subnet's default public IP addressing behavior

- Business Intelligence reporting systems is a type of Online Analytical Processing (OLAP) which Redshift is known to support. In addition, Redshift also provides columnar storage unlike the other options

- AWS CloudTrail is a service that enables governance, compliance, operational auditing, and risk auditing of your AWS account

- Amazon Glacier Select is primarily used to perform filtering operations using simple Structured Query Language (SQL) statements directly on your data archive in Glacier

- Reserved Instances that applied to terminated instances are still billed until the end of their term according to their payment option.

- Use this failover configuration when you want all of your resources to be available the majority of the time. When a resource becomes unavailable, Route 53 can detect that it's unhealthy and stop including it when responding to queries. In active-active failover, all the records that have the same name, the same type (such as A or AAAA), and the same routing policy (such as weighted or latency) are active unless Route 53 considers them unhealthy. Route 53 can respond to a DNS query using any healthy record.

- Use an active-passive failover configuration when you want a primary resource or group of resources to be available the majority of the time and you want a secondary resource or group of resources to be on standby in case all the primary resources become unavailable.

- Transitive Peering : You have a VPC peering connection between VPC A and VPC B (pcx-aaaabbbb), and between VPC A and VPC C (pcx-aaaacccc). There is no VPC peering connection between VPC B and VPC C. You cannot route packets directly from VPC B to VPC C through VPC A.

- Edge to Edge Routing Through a Gateway or Private Connection : if VPC A and VPC B are peered, and VPC A has any of these connections, then instances in VPC B cannot use the connection to access resources on the other side of the connection. Similarly, resources on the other side of a connection cannot use the connection to access VPC B.

- AWS Storage Gateway connects an on-premises software appliance with cloud-based storage to provide seamless integration with data security features between your on-premises IT environment and the AWS storage infrastructure

- When you upload your data in S3, your objects are redundantly stored on multiple devices across multiple facilities within the region only, where you created the bucket. Hence, if there is an outage on the entire region, your S3 bucket will be unavailable if you do not enable Cross-Region Replication, which should make your data available to another region.

- You can configure Amazon Redshift to copy snapshots for a cluster to another region. To configure cross-region snapshot copy, you need to enable this copy feature for each cluster and configure where to copy snapshots and how long to keep copied automated snapshots in the destination region.

- You can use AWS X-Ray to trace and analyze user requests as they travel through your Amazon API Gateway APIs to the underlying services. API Gateway supports AWS X-Ray tracing for all API Gateway endpoint types: regional, edge-optimized, and private. You can use AWS X-Ray with Amazon API Gateway in all regions where X-Ray is available.

For any help, get in touch @ [LinkedIn](https://www.linkedin.com/in/aroraraghav/ "LinkedIn")
