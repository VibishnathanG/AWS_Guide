**Amazon S3 (Simple Storage Service) - Object storage service for scalable and secure data storage.**

- **Buckets:** A container for storing objects in S3. You can create multiple buckets within an S3 account, and each bucket can store an unlimited number of objects. 

  Examples of buckets include:

  - A bucket to store all of your static website assets, such as HTML, CSS, and JavaScript files.
  - A bucket to store backups of your database.
  - A bucket to store user-uploaded files.
- **Bucket Versioning:** Enables you to keep multiple versions of an object in a bucket. This is useful for rollback purposes; in case you accidentally delete or modify an object.
- **Encryption:** You can encrypt objects at rest and in transit using AES-256 encryption. This helps to protect your data from unauthorized access. Three major types of encryptions in S3 Server-side encryption with Amazon S3 managed keys (SSE-S3), Server-side encryption with AWS Key Management Service keys (SSE-KMS), Dual-layer server-side encryption with AWS Key Management Service keys (DSSE-KMS).
- **Intelligent-Tiering:** Automatically stores your objects in the most cost-effective storage tier based on their access frequency. This can help you to save money on storage costs.
- **Server access logging:** Logs all requests made to a bucket. This can be useful for troubleshooting and security purposes.
- **Event notifications:** Can be configured to send notifications to other AWS services, such as Amazon SNS or Amazon Lambda, when certain events occur in a bucket, such as when an object is uploaded or deleted.
- **Amazon EventBridge:** An event routing service that can be used to route events from S3 to other AWS services.
- **Transfer acceleration:** Improves the speed of transferring large objects to and from S3.
- **Object Lock:** Allows you to set a retention period for objects in a bucket, so that they cannot be deleted or overwritten before the retention period expires.
- **Static website hosting:** Allows you to host a static website directly from an S3 bucket.
- **Block public access:** Prevents objects in a bucket from being made public accidentally.
- **Bucket policy:** A policy that controls who can access objects in a bucket and what actions they can perform.
- **Access control list (ACL):** A list of users and groups who have access to a bucket and the permissions they have.
- **Cross-origin resource sharing (CORS):** A configuration that allows websites from other domains to access resources in your S3 bucket.
- **Bucket metrics:** Metrics that provide information about the activity in a bucket, such as the number of objects uploaded and downloaded, and the amount of data transferred.
- **Storage Class Analysis:** Analysis the storage usage of your objects and recommends the most cost-effective storage class for each object.
- **Lifecycle rules:** Automate actions on objects in a bucket based on certain criteria, such as age or object type. For example, you can use lifecycle rules to automatically delete objects after they are 30 days old.
- **Replication rules:** Replicate objects in a bucket to another bucket in a different AWS region. This can help to improve data durability and disaster recovery.
- **Access Points:** Provide a way to control access to specific prefixes within a bucket. For example, you can create an access point that allows users to access all objects that start with the prefix "images/".
- **Multi-Region Access Points:** Provide a way to access objects in a bucket from any AWS region.
- **Batch Operations:** Allow you to perform multiple operations on objects in a bucket in a single request. This can improve the performance of your application.

**Types of storage class:**

**Standard:**

- Access: Frequent access within milliseconds
- Use cases: Websites, applications, frequently accessed data
- Pricing: $0.023 per GB per month + $0.005 per 1,000 requests

  **Standard-IA:**

- Access: Less frequent access (once a month or less)
- Use cases: Backups, archives, infrequently accessed data
- Pricing: $0.0125 per GB per month + $0.005 per 1,000 requests + minimum 30-day storage duration

  **Intelligent-Tiering:**

- Access: Dynamically changes tiers based on access patterns
- Use cases: Data with unknown or changing access patterns
- Pricing: $0.0125 per GB per month + $0.005 per 1,000 requests + $0.01 per GB month for transitions out of the Frequent Access tier

  **One Zone-IA:**

- Access: Less frequent access within milliseconds (stored in a single Availability Zone)
- Use cases: Backups, archives, infrequently accessed data with secondary importance
- Pricing: $0.010 per GB per month + $0.005 per 1,000 requests + minimum 30-day storage duration

  **Glacier:**

- Access: Infrequent access, retrieval times ranging from hours to days
- Use cases: Long-term archives, disaster recovery
- Pricing: $0.004 per GB per month + retrieval fees starting at $0.09 per GB

  **Glacier Deep Archive:**

- Access: Very infrequent access, retrieval times in hours to days
- Use cases: Long-term, rarely accessed data, compliance data
- Pricing: $0.00095 per GB per month + retrieval fees starting at $0.01 per GB

**Amazon EC2 (Elastic Compute Cloud) - Virtual servers for scalable compute capacity.**

**Components:**

- **Instance:** A virtual server in the cloud with CPU, memory, storage, and networking resources. You can create, launch, stop, and terminate instances as needed. 

  **Types:** On-Demand, Reserved, Spot Fleet, Dedicated Host, Local Storage, etc. 

  **Example:** Run a web server, batch processing tasks, or database backends.

- **Amazon Machine Image (AMI):** A template containing system software, applications, and settings for creating new instances. It defines the starting point for your instances. 

  **Types:** Amazon-provided, Community AMIs, Custom AMIs. 

  **Example:** Use a pre-configured WordPress AMI to quickly launch a web server.

  **AMI Consists of:**

- **Operating System:** This is the foundation of the AMI, and it defines the environment in which your applications and software will run. 

  Examples include popular choices like Ubuntu, CentOS, Windows Server, etc.

- **Software Applications:** You can pre-install and configure specific software applications onto the AMI, saving you time and effort when launching new instances. This could include web servers, databases, development tools, or any other software needed for your workload.
- **System Configurations:** AMIs allow you to define basic system configurations like user accounts, security groups, networking settings, and file system layouts. This ensures consistent starting points for your instances.
- **Optional Components:** Additionally, you can include other optional components in your AMI, such as:
- **Boot scripts:** Scripts that run automatically during instance launch, performing additional configuration or installation tasks.
- **Drivers:** Necessary drivers for specific hardware devices attached to the instances.
- **Pre-loaded data:** Static data that should be available on all instances launched from the AMI.

  Amazon Machine Images (AWS AMI) offers two types of virtualizations: Paravirtual (PV) and Hardware Virtual Machine (HVM). Every AWS AMI uses the Xen hypervisor on bare metal. Xen offers two kinds of virtualization: HVM (Hardware Virtual Machine) and PV (Paravirtualization). HVM (Hardware Virtual Machine) is the recommended choice over PV (Paravirtualization) on AWS because it offers better performance, compatibility, and future-proofing.

|**Feature**|**HVM**|**PV**|
| :-: | :-: | :-: |
|Performance|Better|Lower|
|Compatibility|Wider|Limited|
|OS Modification|No|Yes|
|Security Updates|Yes|No|
|Use Cases|Most workloads|Legacy workloads, minimalist setups|


**Benefits of using AMIs:**

- **Reproducibility:** Easily launch instances with identical configurations, ensuring consistency and predictability for your environment.
- **Efficiency:** Saves time and effort compared to manually configuring each instance from scratch.
- **Security:** Allows you to pre-configure security settings and minimize potential vulnerabilities.
- **Scalability:** Quickly scale your infrastructure by launching new instances from the same AMI.

  **Examples:**

- You could create an AMI with a pre-configured web server stack containing Apache, PHP, and MySQL, ready to deploy your web applications.
- You could create an AMI with all the development tools needed for your team, making it easy for new members to get started quickly.
- You could create an AMI with a customized security configuration applied, ensuring all instances adhere to your security policies.

- **Instance Type:** Defines the CPU, memory, storage, and network capacity of your instance. Choose the type that best fits your workload requirements. **Types:** General-purpose, Compute-optimized, Memory-optimized, Storage-optimized, etc.

  ` `**Example:** 

**General Purpose:**

- **Use Cases:** Web servers, databases, development environments, general workloads.
- **Ideal for:** Balanced CPU, memory, and network performance for everyday applications.
- **Examples:** t2.large (Burstable Performance),t3.large (Burstable Performance),m5.large (General Purpose),r5.large (Compute Optimized)

**Compute Optimized:**

- **Use Cases:** High-performance computing (HPC), scientific simulations, video encoding.
- **Ideal for:** CPU-intensive workloads requiring high sustained performance.
- **Examples:** c5.large (Compute Optimized),c6g.large (Compute Optimized),r5d.large (Compute Optimized)

**Memory Optimized:**

- **Use Cases:** In-memory databases, large analytics, memory-intensive workloads.
- **Ideal for:** Large amounts of memory for applications working with massive datasets.
- **Examples:** r5.large (Memory Optimized),r6g.large (Memory Optimized),z1d.large (Memory Optimized)

**Storage Optimized:**

- **Use Cases:** Databases, data warehousing, file servers, log processing.
- **Ideal for:** High-throughput storage access and I/O intensive workloads.
- **Examples:** d2.xlarge (Storage Optimized),i3.xlarge (Storage Optimized),EBS-optimized instances (e.g., t3.xlarge.ebs)

**Accelerated Computing:**

- **Use Cases:** Machine learning, AI, graphics rendering, video processing.
- **Ideal for:** Workloads requiring specialized hardware like GPUs or FPGAs.
- **Examples:** p3.2xlarge (Accelerated Computing),g4dn.xlarge (Accelerated Computing),f1.xlarge (Accelerated Computing)

**High-Performance Computing (HPC):**

- **Use Cases:** Large-scale scientific simulations, complex modeling, weather forecasting.
- **Ideal for:** Intensive parallel processing workloads requiring massive compute power.
- ` `**Examples:** hpc6a.large (High-Performance Computing),c6gn.xlarge (High-Performance Computing)

` `**Sample instance Family Classification:**



|Size|CPU Cores|Memory|EBS Storage|Network Performance|Cost|
| :- | :- | :- | :- | :- | :- |
|m5.nano|1|512 MB|8 GB|Moderate|Low|
|m5.small|1|1 GB|32 GB|Moderate|Med|
|m5.micro|1|2 GB|32 GB|Moderate|Med|
|m5.large|2|8 GB|32 GB|Moderate|High|

**User Data:** Scripts or commands automatically provided to an instance during launch. Use them to customize your instance configuration. 

**Example:** Install specific software packages or configure application settings.

- **Storage:** Options for storing data associated with your instances. 

  **Types:** Amazon Elastic Block Store (EBS) volumes, Amazon Simple Storage Service (S3) buckets, Instance Store (volatile). 

  **Example:** Use EBS volumes for persistent data that survives instance restarts.

- **Launch Template:** A blueprint for defining and launching instances with consistent configurations. Use templates for repetitive deployments. 

  **Example:** Use a template for all your web servers to ensure they have the same software and settings.

- **Spot Instance:** A way to bid for unused EC2 capacity at discounted prices. You can save money on workloads that can tolerate interruptions. 

  **Types:** Interrupt-driven, Scheduled, Dedicated Spot instances.

  ` `**Example:** Run low-priority batch jobs on Spot instances.

- **Reserved Instance:** A purchase option for dedicated EC2 capacity at a fixed hourly rate, offering significant discounts over On-Demand instances. 

  **Types:** All Upfront, Partial Upfront, Scheduled. 

  **Example:** Reserve instances for long-running, predictable workloads.

- **AMI:** Alias for Amazon Machine Image (see above).
- **Volumes:** Alias for Storage options (see above).
- **Snapshot:** Point-in-time copy of an EBS volume that you can use to create new volumes or restore data. 
- **Key Pair:** A public-private key pair used for SSH access to your instances. Keep the private key secure. 

  **Example:** Access your instance for configuration management or troubleshooting.

- **Load Balancers:** Route incoming traffic across multiple EC2 instances for high availability and scalability.

  ` `**Types:** Application Load Balancer, Network Load Balancer, Classic Load Balancer. 

  **Application Load Balancer (ALB):**

- **Best for:** HTTP/HTTPS-based applications, modern microservices architectures with containerized applications.
- **Strengths:** Layer 7 routing based on application characteristics, flexible routing based on path, headers, and cookies, advanced health checks, integration with container orchestration tools like ECS and Fargate.
- **Use cases:** Web applications, mobile backends, content delivery networks (CDNs), API gateways.

**Network Load Balancer (NLB):**

- **Best for:** High-throughput workloads with minimal processing at Layer 7, TCP/UDP-based applications.
- **Strengths:** High performance and scalability, low latency, Layer 4 routing based on IP and port, suitable for stateless workloads.
- **Use cases:** Gaming servers, database clusters, streaming applications, high-frequency trading systems.

**Example:** Distribute traffic across a pool of web servers.

- **Target Groups:** Collections of AWS resources (e.g., EC2 instances) that Load Balancers route traffic to. 

  **Example:** Define a Target Group containing your web servers.

- **Auto Scaling Groups:** Automatically adjust the number of EC2 instances based on predefined scaling policies. 

  **Example:** Scale up your web servers during peak traffic periods.

**Amazon RDS (Relational Database Service) - Managed relational database service supporting multiple engines.**

**Components:**

- **DB Instance:** A managed relational database instance in the cloud. Choose from various database engines (e.g., MySQL, PostgreSQL, Aurora). 

  **Types:** Standalone, Multi-AZ, Read Replicas. 

  **Example:** Run a production database in RDS for scalable, secure, and reliable storage.

- **DB Clusters:** Groupings of DB instances (primary and optionally read replicas) that provide high availability, data redundancy, and improved read performance.

  ` `**Types:** Multi-AZ clusters, Aurora Serverless clusters, Read Replica clusters.

  ` `**Example:** Set up a DB cluster for mission-critical databases requiring continuous uptime and fast reads.

- **Snapshots:** Point-in-time backups of your database instance. Use them for data recovery, creating new database instances, or for testing purposes. 

  **Types:** Automatic backups (configurable retention), manual snapshots, automated snapshots via lifecycle policies.

  ` `**Example:** Create a snapshot before performing major database changes or migrations.

- **Query Editor:** A web-based tool directly within the AWS Management Console for accessing your database instances and issuing SQL queries. 

  **Example:** Manage your database schema, data, and run ad-hoc queries without external tools.

- **Automated Backups:** RDS automatically backs up your database instances daily by default. Configure backup retention periods, scheduling, and encryption for enhanced security.

  ` `**Example:** Ensure data loss prevention with reliable, secure backups.

- **Subnet Groups:** Define the virtual network configuration for your DB instances, ensuring security and communication within your VPC. 

  **Types:** Public, Private. 

  **Example:** Securely connect your database to other resources within your VPC, controlling inbound and outbound traffic.

- **Parameter Groups:** Collections of settings that control various aspects of your database instance behavior.

  ` `**Types:** System parameters, engine-specific parameters.

  ` `**Example:** Configure connection timeouts, logging levels, database character sets, and more.

- **Custom Engine Versions:** While RDS typically manages engine updates, you can request access to beta versions or older patch versions for specific needs.

  ` `**Example:** Use a custom engine version if you require functionality not yet available in the generally released version.

- **Option Groups:** Manage additional features and settings beyond those in parameter groups.

  ` `**Types:** Read Replica groups, Performance Insights. 

  **Example:** Enable Performance Insights for detailed performance monitoring and data.

- **Engine Options:** Specific features or behaviors available for certain database engines, often beyond core functionality. 

  **Types:** Aurora Global Database, Aurora Serverless v2. 

  **Example:** Enable Aurora Global Database for seamless regional data replication and disaster recovery.

- **DB Cluster Identifier:** A unique name that identifies your DB cluster. Use it to reference and manage the cluster. 

  **Example:** "my-production-cluster".

- **Cluster Storage Configuration:** Define the storage type and capacity for your DB cluster's instances. 

  **Types:** Provisioned IOPS (SSD), General Purpose (HDD). 

  **Example:** Choose Provisioned IOPS for demanding workloads requiring consistent performance.

- **Instance Configuration:** Specify the compute, memory, and storage resources for each instance in your DB cluster. 

  **Types:** Various instance types based on engine and requirements.

  ` `**Example:** 

|Instance Type|Use Case|Example|
| :- | :- | :- |
|**General Purpose:**|Low-traffic websites, development environments, small databases|db.t2.micro (1 vCPU, 1 GiB RAM, 8 GiB storage) - Personal website database|
|**General Purpose (Burstable):**|Fluctuating workloads, cost-efficiency|db.t3.medium (2 vCPUs, 4 GiB RAM, 16 GiB storage) - Development/staging database|
|**General Purpose (Balanced):**|Medium-sized databases, web applications|db.m5.xlarge (4 vCPUs, 16 GiB RAM, 32 GiB storage) - E-commerce website database|
|**Compute Optimized:**|Complex queries, data warehousing, analytics|db.r5.xlarge (6 vCPUs, 32 GiB RAM, 64 GiB storage) - Data analytics application|
|**Memory Optimized:**|In-memory databases, real-time analytics|db.r5d.xlarge (8 vCPUs, 32 GiB RAM, 384 GiB in-memory storage) - Real-time fraud detection|
|**Storage Optimized (SSD):**|I/O-intensive workloads, OLTP|db.d2.xlarge (4 vCPUs, 16 GiB RAM, 64 GiB SSD storage) - Online ticket booking system|
|**Storage Optimized (NVMe SSD):**|Extreme I/O performance, demanding applications|db.i3.xlarge (4 vCPUs, 32 GiB RAM, 128 GiB NVMe SSD storage) - High-frequency trading platform|


- **Multi-AZ Deployment:** Replicate your DB cluster across multiple Availability Zones (AZs) for high availability and automatic failover during disruptions. 

  **Example:** Ensure database uptime even in the event of AZ outages.

- **RDS Proxy:** A highly available and scalable connection point for multiple database instances, simplifying application connections and load balancing. 

  **Example:** Use RDS Proxy for improved connection management and security.

- **Certificate Authority (CA):** Create and manage custom CAs within RDS to issue SSL/TLS certificates for secure database connections. 

  **Example:** Enhance communication security by using custom certificates.

- **Database Authentication:** Multiple options for authenticating users and applications to your database instances: 

  **Types:** Password authentication, IAM authentication, Kerberos authentication.

  ` `**Example:** Use IAM authentication for centralized and secure access control.



**Amazon VPC (Virtual Private Cloud) Components -**

**Networking service for creating isolated cloud resources**

**Core Components:**

- **Virtual Private Cloud (VPC):** A logically isolated section of the AWS cloud where you launch your resources. A VPC has its own IP address range and controls how its resources connect to the internet and other VPCs.
- **IPv4 CIDR:** The IP address block you define for your VPC. Subnets within the VPC fall within this range. Example: 10.0.0.0/16

Subnetting:



Each digit in binary represents a power of 2, starting from the rightmost digit with 2^0.

In this case, we have:

1 \* 2^0 = 1

1 \* 2^1 = 2

1 \* 2^2 = 4

1 \* 2^3 = 8

1 \* 2^4 = 16

Adding all the values: 1 + 2 + 4 + 8 + 16 = 31

Therefore, 00011111 in decimal is 31.

32 - (Subnet mask) = Host Bit

For example: 10.10.0.0/27

here Network bit is First 27 and last 5 is host bit which can last up 31 hosts.

32-27 = 5 

0\.0.0.1.1.1.1.1 = 31 

- **Subnet:** A segment of your VPC's IP address range where you place resources. Use subnets to further isolate different groups of resources within your VPC. Example: Public subnet for web servers, Private subnet for database instances.
- **Route Tables:** Control how traffic in your VPC routes to the internet, other VPCs, or on-premises networks. Each subnet associates with a route table. Example: Route table directs internet traffic to an internet gateway, and traffic to another VPC through a peering connection.

**Connectivity Components:**

- **Internet Gateway:** Connects your VPC to the public internet. Resources in public subnets can access the internet through the gateway.
- **Elastic IPs:** Public IP addresses associated with resources in your VPC. They remain static even if the underlying resource changes. Use them for externally accessible resources like web servers.
- **Endpoints:** Allow private VPC resources to securely access AWS services without requiring an internet gateway. Example: S3 endpoint allows access to S3 buckets without internet exposure.
- **NAT Gateways:** Enable private resources in private subnets to access the internet without public IP addresses. Use NAT gateways for outbound-only communications.

**Security Components:**

- **Network ACLs (Network Access Control Lists):** Firewall rules at the subnet level controlling inbound and outbound traffic. Apply ACLs for additional granular control within subnets.
- **Security Groups:** Define firewall rules at the resource level. Each resource can have multiple security groups attached, offering flexible security configurations.
- **DNS Firewall:** A managed DNS security service that protects your VPC from DNS-based attacks.

**VPN Connectivity:**

- **Virtual Private Network (VPN):** Connects your VPC to an on-premises network securely over an encrypted tunnel.
- **Customer Gateways:** Hardware devices deployed on-premises that connect to your VPC via a VPN.
- **Virtual Private Gateways:** AWS-managed endpoints for VPN connections within your VPC.
- **Site-to-Site VPN Connections:** Connect your VPC to an on-premises network using dedicated VPN connections.
- **Client VPN Endpoints:** Enable secure remote access to your VPC resources using VPN clients.

**Advanced Networking:**

- **Transit Gateways:** Act as central hubs for routing traffic between multiple VPCs and on-premises networks.
- **Transit Gateway Attachments:** Connect VPCs and on-premises networks to a transit gateway.
- **Transit Gateway Policy Tables and Route Tables:** Define routing rules for traffic traversing through a transit gateway.

**Management Tools:**

- **AWS Network Manager:** Suite of tools for managing and troubleshooting your VPC network.
  - **Reachability Analyzer:** Tests network connectivity between resources.
  - **Network Access Analyzer:** Monitors and records network traffic flows.

**Additional Concepts:**

- **Direct Connect:** Dedicated network connections between your on-premises network and AWS for high-bandwidth, low-latency connectivity.

**VPC Chart with sub components:**

![[Image of AWS VPC diagram with all components]](Aspose.Words.1a105e8c-96fe-4275-84e6-c4c938fef5b5.001.png)







**Amazon IAM (Identity and Access Management)**

**Definition: Who has access to what?** 

**Components:**

- **Users:** Individual AWS accounts with usernames and passwords. Use them for direct logins or for programmatic access with API keys.
- **Roles:** Set of permissions that you can associate with users, applications, or services. They don't have passwords and are not for direct logins.
- **Policies:** Documents that define the permissions granted to users or roles. They specify which AWS resources they can access and what actions they can perform.
- **Identity Providers (IdPs):** External authentication systems like Active Directory or Okta that you can integrate with IAM for SSO (Single Sign-On).
- **Access Analyzer:** Analyzes your IAM policies and resource configurations to identify potential security risks or overly permissive access.
- **AWS Organizations:** Enables centralized management of multiple AWS accounts within a single organization.

**Amazon CloudWatch**

**Components:**

- **Alarms:** Notifications triggered when metrics reach specific thresholds. You can define actions to be taken when an alarm fires, like sending an email or scaling auto scaling groups.
- **Log Groups:** Stores your log data from various AWS services, applications, and custom sources. Logs provide insights into system health, application behaviour, and troubleshooting issues.
- **Metrics:** Numerical measurements reflecting the state of your resources, like CPU usage, network traffic, or disk space. CloudWatch monitors metrics and uses them for alarms, dashboards, and billing.
- **Rules:** Automate actions based on specific log data patterns. You can filter logs and trigger actions like invoking Lambda functions or sending notifications.


**Amazon Lambda:**

**Components:**

- **Functions:** The core unit of Lambda, containing your code (e.g., Python, Node.js, Java) that executes in response to events.
- **Applications:** Groups related functions for easier management and versioning.
- **Layers:** Reusable code libraries shared across multiple functions, reducing code duplication and simplifying deployments. Can include up to five layers per function. Also, can use layers only with Lambda functions deployed as a .zip file archive. For functions defined as a container image, package your preferred runtime and all code dependencies when you create the container image.
  - **To reduce the size of your deployment packages.** Instead of including all of your function dependencies along with your function code in your deployment package, put them in a layer. This keeps deployment packages small and organized.
  - **To separate core function logic from dependencies.** With layers, you can update your function dependencies independent of your function code, and vice versa. This promotes separation of concerns and helps you focus on your function logic.
  - **To share dependencies across multiple functions.** After you create a layer, you can apply it to any number of functions in your account. Without layers, you need to include the same dependencies in each individual deployment package.
  - **To use the Lambda console code editor.** The code editor is a useful tool for testing minor function code updates quickly. However, you can’t use the editor if your deployment package size is too large. Using layers reduces your package size and can unlock usage of the code editor.

![
      Architectural differences between two Lambda functions that don't use layers, and two
        functions that share a layer.
    ](Aspose.Words.1a105e8c-96fe-4275-84e6-c4c938fef5b5.002.png)

- **Replicas:** Automatically scale your function's concurrency to handle bursts of events, ensuring responsiveness.
- **Step Functions State Machines:** Orchestrate complex workflows by chaining Lambda functions together in visual workflow diagrams.
- **Code Signing Configurations:** Implement cryptographic signing for enhanced security and verification of your Lambda code.
- **Event Source Mappings:** Automatically trigger Lambdas in response to events from other AWS services (e.g., S3 object uploads, DynamoDB streams).
- **Trigger Configuration:** Define specific settings for event source mappings, like filtering events or batching them for efficiency.
- **Destination Configuration:** Specify where to send data after successful Lambda execution (e.g., SQS queue, SNS topic).

**Example:** Trigger a Lambda function to resize images uploaded to S3 automatically.




**AWS Elastic File System (EFS): Fully managed file storage service for EC2 instances.**

**Components:**

- **File Systems:** Managed file systems accessible by multiple EC2 instances within your VPC.
- **Access Points:** Control access to specific directories within a file system, enhancing security and granular permissions.

**Example:** Share application data across a cluster of EC2 web servers using a single EFS file system.

**Amazon DynamoDB:**

**Components:**

- **Tables:** Stores your data in key-value pairs with flexible schema design.
- **Exports to S3:** Back up and archive your DynamoDB data to S3 buckets for long-term storage and disaster recovery.
- **Imports from S3:** Load large datasets into DynamoDB tables efficiently by importing from S3 buckets.
- **Clusters:** Deploy tables across multiple Availability Zones for enhanced performance, scalability, and fault tolerance.
- **Subnet Groups:** Configure the virtual network settings for your DynamoDB tables, controlling security and communication within your VPC.
- **Partition Key:** An attribute uniquely identifying an item within a DynamoDB table, optimizing data access and performance.

**Example:** Build a highly scalable NoSQL database for mobile app user profiles and activity data.

**11. AWS CloudFormation - IAAC for AWS:**

**Stacks:** CloudFormation templates define infrastructure resources as "stacks," like groups of related objects such as EC2 instances, S3 buckets, and security groups. You can create, update, or delete stacks declaratively, ensuring consistency and repeatability.

**StackSets:** Manage infrastructure across multiple AWS accounts and regions with stack sets. They apply a single template to multiple stacks, simplifying large-scale deployments and maintaining consistency.

**12. Amazon SQS, Amazon SNS, Amazon SES - Managed Messaging Services:**

**Amazon SQS:**

- **Queues:** Store messages persistently for asynchronous processing between applications.
- **Type:** Standard Queue (FIFO order, unlimited size) or FIFO Queue (strict message order, 100GB size limit).
- **Encryption:** Encrypt SQS data at rest and in transit with AES-256.
- **Access Policy:** Control who can send and receive messages using IAM policies.
- **Dead-Letter Queue (DLQ):** Optionally store undelivered messages in a DLQ for retry or analysis.

**Amazon SNS:**

- **Topics:** Publish-subscribe service for sending messages (fan-out) to multiple subscribers simultaneously.
- **Subscriptions:** Clients or services subscribe to topics to receive messages.
- **Email Services (SES):** Integrate SNS with SES to send transactional emails (e.g., notifications) triggered by SNS topics.

**13. AWS Cloud Migration - Streamlined Migrations to AWS:**

**AWS Application Migration Service (AMS):**

- **Source Servers:** Identify on-premises servers and applications for migration.
- **Applications:** Analyse server dependencies, configurations, and workloads.
- **Replication Template:** Define how servers will be replicated to AWS, including OS, applications, and data.

**AWS Database Migration Service (DMS):**

- **Replication Instances:** Virtual machines in your VPC for DMS tasks.
- **Endpoints:** Source database and target database endpoints (e.g., RDS instances).
- **Database Migration Tasks:** Define migration parameters, including the source and target databases, tables, and schema mappings.
- **Data Collectors:** Capture and transfer change data from source databases to AWS.

**14. AWS Systems Manager:**

**Components:**

- **Explorer Setup:** Discover, inventory, and visualize your AWS resources and relationships for centralized management.
- **OpsCenter:** Proactively monitor and remediate operational issues across your hybrid environment, using automation runbooks and alerting mechanisms.
- **Incident Manager:** Respond to incidents effectively with guided workflows, collaboration tools, and root cause analysis capabilities.
- **Application Management:** Deploy and manage applications consistently across multiple environments, including on-premises and other clouds.
- **Change Management:** Automate and control infrastructure changes through pre-approval workflows and rollback options.
- **Node Management:** Simplify agentless management of EC2 instances, Docker hosts, and other resources, providing patch management and configuration control.

**Example:** Use Systems Manager Explorer to identify untagged resources across your AWS accounts and apply consistent tagging policies for better organization.

**15. Amazon CloudFront:**

**Components:**

- **Distributions:** Define how content is delivered, including origin servers, caching behaviour, security settings, and edge locations.
- **Functions:** Edge Lambda functions allow you to modify content or data at the edge, closer to users, for increased performance and customization.
- **Policies:** Control access to your distributions using IAM roles or security policies.
- **Cache Statistics:** Gain insights into caching efficiency, request types, and origin traffic to optimize your distribution.

**Example:** Create a CloudFront distribution with caching enabled for your static website assets, delivering content globally with low latency.

**16. Amazon Route 53:**

**Components:**

- **Hosted Zones:** Manage DNS settings for your domains, delegating subdomains to other services as needed.
- **Domains:** Register or manage existing domain names within Route 53, enabling seamless DNS management.
- **Resolver:** Resolve DNS queries efficiently using Route 53's global infrastructure and DNSSEC validation capabilities.
- **Health Checks:** Monitor the health of your origin servers and automatically route traffic to healthy backups if issues arise.

**Example:** Use Route 53 to manage DNS records for your website, ensuring high availability and directing users to the most appropriate origin server.



