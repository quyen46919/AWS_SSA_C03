## AWS Solution Architect Associate Roadmap 🚀

Tự học AWS SSA-C03 dựa trên khóa học youtube của Andrew Brown + ChatGPT + một đống tài liệu khác liên quan 🥸

Nguồn: https://www.youtube.com/watch?v=c3Cn4xYfxJY&t=7206s  
Playlist: https://www.youtube.com/playlist?list=PLBfufR7vyJJ6FhBhJJSaMkI-m2wyoPy-G

Các mục bên dưới không xếp theo độ ưu tiên mà là quá trình học của tôi 🐣

P/s: Trong các bài sẽ nhắc lại kiến thức của những module khác hoặc kiến thức có liên quan nên đôi khi bạn sẽ thấy nó dư thừa, nhưng với tôi nó thực sự hữu ích vì khi cần ôn lại thì không phải research thêm 🕵️‍♂️

### PART 1 - IAM

<details>

<summary>IAM (I am)</summary>

- AWS Managed vs Customer Managed vs Inline Policy
- Types of Policies Follow Along
- Anatomy of an IAM Policy
- Principle of least Privilege (PoLP)
- IAM Policy Follow Along
- AWS Account Root User
- IAM Password Policy
- IAM Password Policy Follow Along
- IAM Access Keys
- IAM Access Keys Follow Along
- IAM MFA (Multi-factor Authentication)
- IAM MFA (Multi-factor Authentication) Follow Along
- IAM Temporary Security Credentials
- IAM Identity Federation
- IAM STS (Security Token Service)
- IAM STS (Security Token Service) Follow Along
- IAM Cross Account Roles
- IAM AssumeRoleWithWebIdentity
- AWS SSO (Sign-Sign-On)

</details>

### PART 2 - Amazon S3 (Simple Storage Service)

<details>

<summary>Amazon S3 (Simple Storage Service)</summary>

- CLI Follow Along
- Bucket Overview
- Bucket Naming Rules
- Bucket Naming Rules Examples
- Bucket Restrictions & Limitations
- Bucket Types
- Bucket Folders
- Bucket Folders
- Object Overview
- Object ETags
- Object ETags Follow Along
- Object Checksums
- Object Checksums Follow Along
- Object Prefixes
- Object Prefixes Follow Along
- Object Metadata
- Object Metadata (System Defined)
- Object Metadata (User Defined)
- Object Metadata Follow Along
- WORM (Write Once Read Many)
- Object Lock
- Bucket URI
- CLI
- Request Styles
- Dualstack Endpoints
- Storage Classes Overview
- Storage Classes - Standard
- Storage Classes - RRS (Reduced Redundancy Storage) [Legacy]
- Storage Classes - Standard-IA (Infrequent Access)
- Storage Classes Follow Along
- Storage Classes - Express One Zone [New]
- Storage Classes - One-Zone-IA
- 'S3 Glacier Storage Classes' vs 'S3 Glacier "Vault"'
- Storage Classes - Glacier Instant Retrieval
- Storage Classes - Glacier Flexible Retrieval [<- Glacier "Vault"]
- Storage Classes - Glacier Deep Archive [<- Glacier "Vault"]
- Storage Classes - Intelligent-Tiering
- Storage Classes - Cheat Sheet
- Security - Overview
- Security - Block Public Access
- Security - ACL (Access Control Lists) [Legacy]
- Security - ACL Follow Along
- Security - Bucket Policies
- Security - Bucket Policies Follow Along
- Security - Bucket Policies vs IAM Policies
- Security - Access Grants
- Security - IAM Access Analyzer for S3
- Security - Internetwork traffic privacy
- CORS (Cross-Origin Resource Sharing)
- Security - CORS
- Security - CORS Follow Along
- Security - Encryption Overview
- Security - Encryption - In-Transit
- Security - Encryption - Server-Side Encryption
- Security - Encryption - Server-Side Encryption - SSE-S3
- Security - Encryption - Server-Side Encryption - SSE-KMS
- Security - Encryption - Server-Side Encryption - SSE-C
- Security - Encryption - Server-Side Encryption - DSSE-KMS
- Security - Encryption - Server-Side Encryption Follow Along
- Security - Encryption - Bucket Key
- Security - Encryption - Client-Side Encryption
- Security - Encryption - Client-Side Encryption Follow Along
- Data Consistency
- Object Replication
- Versioning
- Object Lifecycle
- Transfer Acceleration
- Presigned URL
- Presigned URL - Anatomy
- Access Points (smaller Bucket Policy)
- Multi-Region Access Points
- Object Lambda Access Points
- Mountpoint (Linux file system)
- Archived Objects
- Requesters Pay
- Requesters Pay - Header
- Requesters Pay - Troubleshooting
- Marketplace for S3
- Batch Operations
- S3 Inventory
- Select
- Event Notifications
- Storage Class Analysis
- Storage Lens
- Static Website Hosting
- Multipart Upload
- Multipart Download (Byte Range Fetching)
- Interoperability

</details>

### PART 3 - AWS API

<details>

<summary>AWS API</summary>

- AWS CLI
- Access Keys
- API Retries and Exponential Backoff
- Smithy (AWS open-source IDL -> Service Model)
- STS (Security Token Service)
- STS AssumeRole Follow Along
- Signing AS API Requests
- AWS Signature Version 4
- AWS Service IP Address Ranges
- Service Endpoints
- AWS CLI - accepting input from file CLI Input Flag (--cli-input-json|yaml)
- Configuration Files (~/.aws/credentials|config)
- AWS CLI - Named Profiles
- AWS CLI - Configure Commands / SSO
- AWS CLI - Environment Variables
- AWS CLI - Autoprompt/Autocompletion

</details>

### PART 4 - Amazon VPC (Virtual Private Cloud)

<details>

<summary>Virtual Private Cloud</summary>

- Virtual Private Cloud
- Core Components of VPC
- Key Features of VPC
- VPC Follow Along
- Default VPC
- Deleting VPC
- Default Route (Catch-All-Route) 0.0.0.0/0 ::/0
- Delete & Recreate Default VPC Follow Along
- Shared VPC via RAM (sharing subnet)
- Shared VPC Follow Along
- NACLs
- NACL Follow Along
- Security Groups
- Security Groups Follow Along
- Stateless vs Stateful
- Route Tables
- Route Tables Follow Along
- Gateways
- IGW (Internet Gateway)
- IGW Follow Along
- EO-IGW (Egress-Only Internet Gateway)
- EO-IGW Follow Along
- EIP (Elastic IPs)
- EIP Follow Along
- AWS IPv6 Support
- Migrating from IPv4 to IPv6
- Direct Connect
- VPC Endpoints
- Private Link
- Interface Endpoints (powered via PrivateLink)
- GWLB (Gateway Load Balancer) Endpoint (powered via PrivateLink)
- VPC Gateway Endpoints (private to S3 & DynamoDB)
- VPC Endpoints Comparison
- VPC Flow Logs
- AWS VPN (Virtual Private Network)
- AWS Site-to-Site VPN
- VGW (Virtual Private Gateway)
- Customer Gateway
- TGW (Transit Gateway)
- AWS Client VPN
- NAT (Network Address Translation)
- NAT Gateway
- NAT Instances
- Jumpbox/Bastion host
- VPC Lattice
- TGW (Transit Gateway) More Detail
- Traffic Mirroring
- AWS Network Firewall
- VPC Peering
- VPC Peering Follow Along
- Network Address Usage

</details>

### PART 5 - Amazon Elastic Compute Cloud (EC2)

<details>

<summary>Amazon Elastic Compute Cloud</summary>

- Cloud Init
- Cloud Init Follow Along
- EC2 UserData
- EC2 UserData Follow Along
- EC2 Metadata
- EC2 Metadata Follow Along
- EC2 Instance Types
- EC2 Instance Family
- EC2 Instance Family Follow Along
- EC2 Processors
- EC2 Instance Sizes
- EC2 Instance Profile
- EC2 Instance Lifecycle
- EC2 Instance Console Screenshot
- EC2 Hostnames
- EC2 Default Username
- EC2 Burstable Instances
- EC2 Source & Destination Checks
- EC2 System Log
- EC2 Placement Groups
- Connecting to EC2 Instance
- Connecting to EC2 Instance Follow Along
- RDP (Remote Desktop Protocol) Follow Along
- EC2 Serial Console Follow Along
- EC2 Amazon Linux

</details>

### PART 6 - Auto Scaling Groups (ASG)

<details>

<summary>Auto Scaling Groups</summary>

- Capacity Settings
- Health Check Replacements
- ELB Integration
- Dynamic Scaling Policies
- Simple Scaling Policy
- Step Scaling Policy
- Target Tracking Scaling Policy
- Predictive Scaling Policy
- Termination Policies

</details>

### PART 7 - Elastic Load Balancer (ELB)

<details>

<summary>Elastic Load Balancer</summary>

- The Rules of Traffic
- ALB (Application Load Balancer)
- NLB (Network Load Balancer)
- CLB (Classic Load Balancer)

</details>

### PART 8 - Route53 (R53)

<details>

<summary>Route53</summary>

- R53 (Route53)
- Hosted Zones
- Record Sets
- Alias Record
- R53 Traffic Flow
- Routing Policies Overview
- Simple Routing Policy
- Weighted Routing Policy
- Latency Based Routing Policy (auto direct to lower latency)
- Failover Routing Policy (primary/secondary)
- Geolocation Routing Policy
- Geoproximity Routing Policy
- Multi-Value Answer Policy
- R53 Health Checks
- R53 Resolver
- DNSSEC
- Zonal Shift
- R53 Profiles

</details>

### PART 9 - CloudFront

<details>

<summary>CloudFront</summary>

- CloudFront Lambda@Edge
- CloudFront Functions
- CloudFront Lambda@Edge vs Functions
- CloudFront Origin
</details>

### PART 10 - Elastic Block Storage (EBS)

<details>

<summary>Elastic Block Storage</summary>

- Volume Type Usage
- HDD (Hard Disk Drive)
- HDD RAID (redundant array of independent disk)
- SSD (Solid State Drive)
- Magnetic Tape

</details>

### PART 11 - AWS Snow Family

<details>

<summary>AWS Snow Family</summary>

- AWS Snowcone
- AWS Snowball Edge
- AWS Snowmobile
- AWS Snow Family Comparison
- AWS Snowcone Order a Device Follow Along

</details>

### PART 12 - AWS Transfer Family

<details>

<summary>AWS Snow Family</summary>

- AWS Snowcone
- AWS Snowball Edge
- AWS Snowmobile
- AWS Snow Family Comparison
- AWS Snowcone Order a Device Follow Along

</details>

### PART (TEMPLATE)

<details>

<summary>Tips for collapsed sections</summary>

### You can add a header

You can add text within a collapsed section.

You can add an image or a code block, too.

```ruby
   puts "Hello World"
```

</details>

### PART N - OTHER ULTILITIY SERVICES

<details>

<summary>Services</summary>

### Amazon Machine Image (AMIs)

- AMIs (Amazon Machine Image)
- AMIs (Amazon Machine Image) Follow Along (encrypted, copying to another region)

### AWS Global Accelerator

### Elastic File System (EFS)

- Elastic File System
- EFS Client

### FSx

- Windows File Server
- File Cache

### AWS Backup

###

</details>
