# AWS Concepts and Keywords Summary

## AWS Data Transfer Cost
- Cost: Same Availability Zone private < public < Different Availability Zones within the same region < Different regions

## IAM
- **Role Creation**: Verify permissions for Amazon resources (`taskRoleArn`)
- **Password Policy**: Set a comprehensive password policy for new users, including complexity requirements and mandatory rotation period
- **User Assignment**: Cannot assign IAM to users without an AWS account
- **Temporary Delegation**: Create IAM roles to grant temporary permissions to users without authorization (e.g., EC2 accessing S3 buckets)
- **Trust Policy**: Delegate permissions from Account A to Account B (useful for granting access to a security group in A to B)
- **Permissions Boundary**: Set boundaries to explicitly deny certain policies for a developer IAM, preventing security policy bypass
- **Root User Protection**: Ensure the root user uses a strong password and multi-factor authentication (MFA)

## Amazon EC2
- **On-Premises Connection**: Possible but lacks high availability and scalability
- **Predictive Scaling**: Use when uncertain if Auto Scaling group policies are correct (uses machine learning based on CloudWatch data)
- **Cluster Placement Group**: High-speed network grouping, free data transfer within the same availability zone, suitable for HPC applications
- **Partition Placement Group**: Different hardware usage for partitions, fault isolation within the same availability zone
- **Dedicated Host vs Instance**: Dedicated Host does not share hardware, while Dedicated Instance does

## Amazon S3
- **Long-Term Storage**: Ideal for storing application log files long-term
- **Availability**: Offers over 99% availability
- **Security**: Dangerous to store sensitive information in S3 or EBS
- **Static Website Hosting**: Suitable for static websites (HTML, CSS), not for dynamic content (PHP, JavaScript)
- **Cross-Region Replication**: Requires versioning enabled, ensures strong consistency
- **Storage Classes**: 
  - Standard (3 availability zones)
  - One-Zone-IA (1 availability zone)
  - IA (Infrequent Access)
  - Glacier (long-term archival, not immediately accessible)
  - Glacier Deep Archive (longer access time)
- **Lifecycle Policies**: Automate file deletion to save storage costs

## Amazon Route53
- **DNS Service**: Converts domain names to IP addresses
- **Failover Routing**: Supports failover routing, can be configured without Lambda + CloudWatch
- **Logging**: Enable query logging to log DNS responses
- **Routing Policies**: Multi-value answer, weighted, geolocation-based routing

## Amazon CloudWatch
- **Alarms**: Can create alarms to expand EC2 instances when CPU usage exceeds 90%
- **Logs**: Real-time storage of application logs
- **Composite Alarms**: Combine multiple alarms (e.g., CPU + IOPS)

## AWS DataSync
- **Data Transfer**: Simplifies, automates, and accelerates data transfer between on-premises storage and AWS
- **Supports**: NFS, Amazon S3, Amazon EFS

## Amazon RDS
- **ACID Compliance**: Ensures transaction integrity
- **Automated Backups**: Restorable to any point within the last 30 days
- **Read Replicas**: Enhance read scalability, not suitable for failover
- **Custom**: Allows OS access for custom configurations
- **Storage Auto-Scaling**: Expands storage without downtime

## Amazon DynamoDB
- **Latency**: Consistent sub-10ms latency for applications
- **On-Demand and Provisioned Capacity**: Choose based on predictable vs unpredictable traffic
- **TTL**: Automatically remove expired items
- **Global Tables**: Cross-region replication

## Amazon Lambda
- **Serverless**: Execute code without managing servers
- **Execution Time**: Max 15 minutes per execution
- **Integrations**: Can trigger on various AWS services like S3 events

## Amazon CloudFront
- **CDN Service**: Delivers content with low latency and high transfer speeds
- **Access Control**: Can restrict access to specific countries or IPs
- **TLS Support**: Ensures secure data transmission

## AWS WAF
- **Web Application Firewall**: Protects against web exploits like SQL injection and XSS
- **Resource Protection**: Can be used with CloudFront, API Gateway, and ALB

## Amazon EFS
- **Elastic File System**: Scalable file storage accessible from AWS cloud and on-premises
- **NFS Protocol**: Supports Linux-based instances, suitable for POSIX-compliant workloads

## AWS Direct Connect
- **Dedicated Network Connection**: Provides consistent, low-latency connectivity between on-premises data centers and AWS
- **Setup Time**: Takes several weeks to establish

## AWS Backup
- **Centralized Management**: Protects data across AWS services with policy-based backup management
- **Encryption**: Ensures data encryption during transfer and storage

## Amazon Redshift
- **Data Warehouse**: Petabyte-scale data warehouse solution
- **Serverless Option**: Access and analyze data without provisioning a data warehouse

## Amazon ElastiCache
- **In-Memory Cache**: Redis and Memcached support for caching frequently accessed data
- **High Availability**: Supports replication and failover

## Amazon SQS
- **Message Queuing**: Decouples and scales microservices, distributed systems, and serverless applications
- **FIFO**: Ensures messages are processed in order

## Amazon SES vs SNS
- **SES**: Ideal for marketing and transactional emails
- **SNS**: Suitable for various notification types (SMS, email, push notifications)
