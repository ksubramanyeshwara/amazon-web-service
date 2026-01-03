# Introduction to AWS

## Agenda

- What is Cloud and Cloud Computing?
- Public vs Private Cloud
- Why public cloud is so popular?
- What is AWS?
- Why AWS?
- Create an AWS accound and get started

## What is Virtualization?

- It is the technique to make one physical machine to act as multiple virtual machines(VM).
- Each VM behaves like a separate computer with its own OS, CPU, RAM, and storage.

### Key Components

- Physical Machine: The real hardware (CPU, RAM, SSD).
- Hypervisor: Software that creates and manages VMs.

### How it works?

- Hypervisor software installed physical server.
- Hypervisor takes the control of server's resources and partition them creating seperare VM's

> Each partition becomes an isolated VM with its own RAM, CPU, Storage. It runs indepndently from other VM's.

### Why Virtualization is Used

- Better hardware utilization
- Cost saving
- Isolation (one VM crash won’t affect others)
- Faster deployment & scaling

> You can think of Physical server as an apartment building, Hypervisor as manager and flats as virtual machines.

## What is Cloud?

Cloud is massive network of data centers connected to the internet. These servers store data, run applications, and provide computing power. When you use the cloud you will be using someone else computer over the internet.

## What is Cloud Computing?

- Cloud computing means usage of the cloud resources. It means accessing, managing, and running servers, storage, databases, networking, software, etc. over the internet.
- You pay for what you use. Examples:
  - Launching a virtual server
  - Hosting a website
  - Running a database online

> You can think Cloud as Power station and Cloud Computing as using electricity in your home

## Public vs Private Cloud

### Public Cloud

- Infrastructure is owned by a cloud provider.
- Resources are shared among many users.
- Accessed over the internet.
- Less cost.
- Examples: AWS, Azure, GCP

> You can think as living in a massive apartment complex. You rent a flat. The landlord (cloud provider) maintains everything.

### Private Cloud

- Infrastructure is owned by an organization and used by only one organization.
- Can be on-premise or hosted privately.
- More control & security.
- Higher cost & maintenance.

> You can think as owning a single-family house. It's all yours. You are responsible for maintenance.

## Why is Public Cloud So Popular?

- No upfront hardware cost
- Instant scalability
- Pay only for what you use
- No maintenance headaches
- Global availability
- Fast deployment

## What is AWS?

- AWS stands for amazon web services. It is an cloud computing platform by Amazon.
- AWS provides on-demand cloud services like:
  - Severs(EC2)
  - Storage(S3)
  - Networking
  - Databases
  - Security
- You access everything over the internet and you pay for what you use.

## Why AWS?

- No upfront cost.
  - No need to buy or maintain hardware.
- Instant scalability.
  - Increase or decrease resources in minutes.
- Global availability.
  - Data centers across many countries (Regions & AZs).
- High security.
  - Built-in security, compliance, and access control.
- Wide service range.
  - From simple servers to AI, ML, DevOps tools.
- Pay-As-You-Go Pricing.
  - Consumption based pricing.

## Create an AWS accound and get started

[Create an AWS Free Tier Account, Setup Budget Alerts ](https://www.youtube.com/watch?v=5MRTCayjzQk)

[Shout out to CodeSnippet](https://www.youtube.com/@CodeSnippetByChetanGhate) for AWS video.

# AWS Global Infrastructure

## Region

- Physical location in the world where AWS has multiple clusters of data centers.
- There are total 38 launched regions are there as of now and its growing.
- Each Region is independent and isolated to ensure high fault tolerance.
- Choose Region based on:
  - Latency to users, partners, data sources.
  - Compliance & data residency.
  - Service availability.
  - Pricing differences by Region.

## Availability Zones (AZs)

- Isolated locations within a Region.
- 120 total AZs globally.
- Each AZ consists of one or more discrete data centers with independent power, cooling, and networking.
- Connected via high-bandwidth, low-latency private fiber.

## Data Centers

- Secure physical buildings inside AZs
- Include:
  - Server, storage, networking hardware.
  - Power, cooling.
- Not publicly accessible (for security reasons)

## Edge Locations

- Points of Presence (PoPs): used by Amazon CloudFront, Route 53, Shield
- Purpose:
  - Cache content closer to users
  - Reduce latency
- Located in many cities worldwide
- Not the same as Regions

## Local Zones

- A new type of infrastructure deployment that places compute, storage, database, and other services close to large population, industry, and IT centers.
- Bridges the gap between the Region and the Edge.

- Region where you host resources based on geographic demand.
- AZ where you distribute the applications to avoid single points of failure.
- Edge location where you reduce the latency for static content delivery.
- Local zones where you support low-latency, interactive applications.

### 💡 Some common questions and their answers:

- Q: How many AZs should I use?
- A: At least two; prefer three for critical workloads.

- Q: Do Edge Locations store my data permanently?
- A: CloudFront caches objects temporarily per cache-control; persistent data lives in your origins.

- Q: When do I need multi-Region?
- A: Data sovereignty, globally distributed users, or RTO/RPO that assume regional failures.

## Cloud Building Blocks

### Compute = Your CPU & RAM

**On your laptop:**

- CPU runs programs
- RAM keeps applications fast and responsive

**In the cloud:**

- Compute runs applications, virtual machines, containers, and services

Examples:

- Web servers
- Backend APIs
- Container workloads

> If it “executes code”, it’s compute.

### Storage = Your Hard Drive / SSD

- **On your laptop:**

  - Stores files, photos, videos, documents

- **In the cloud:**

  - Stores application files, images, logs, backups, and data

- Can be:
  - Temporary or permanent
  - Fast or cost-optimized

> If it “stores data”, it’s storage.

### Networking = Your Wi-Fi / Ethernet

- **On your laptop:**

  - Connects you to the internet and other devices

- **In the cloud:**

  - Connects servers, databases, services, and users

- Handles:
  - IP addresses
  - Traffic routing
  - Secure communication

> If systems talk to each other, networking is involved.

### Databases = File Explorer + Excel

- **On your laptop:**

- File Explorer organizes files.
- Excel helps search, filter, and analyze data.

- **In the cloud:**

  - Databases store structured data like:
    - Users
    - Orders
    - Transactions

- Optimized for:
  - Fast queries
  - Reliability
  - Scaling

> If data needs structure and quick access, use a database.

### Security = Antivirus + Passwords

- **On your laptop:**

  - Antivirus, firewalls, login passwords protect you

- **In the cloud:**

  - Security ensures:
    - Only authorized access
    - Data encryption
    - Compliance with policies

- Covers:
  - Identity & access
  - Network protection
  - Monitoring & auditing

> Security is not optional — it’s built into everything.

## AWS Core Services

### 1. Compute Services

Compute services power applications, containers, and functions.

- Amazon EC2 (Elastic Compute Cloud): Virtual servers in the cloud, scalable and flexible.
- Amazon ECS (Elastic Container Service): Fully managed container orchestration.
- Amazon EKS (Elastic Kubernetes Service): Managed Kubernetes clusters.
- AWS Lambda: Serverless compute for running code without provisioning servers.
- AWS Elastic Beanstalk: Easy deployment and scaling for web apps and services.

**Use Cases:** Application hosting, batch processing, container orchestration, event-driven workloads, serverless apps.

### 2. Storage Services

Storage provides scalable, durable, and secure data storage options.

- Amazon S3 (Simple Storage Service): Object storage for any type of data, highly durable and scalable.
- Amazon EBS (Elastic Block Store): Block storage volumes for EC2 instances.
- Amazon EFS (Elastic File System): Fully managed shared file storage for EC2 and on-premises servers.
- AWS Glacier (S3 Glacier): Low-cost archival storage with retrieval options.

**Use Cases:** Data lakes, backups, archiving, file shares, databases, media storage.

### 3. Networking Services

Networking services enable secure, reliable, and scalable connectivity.

- Amazon VPC (Virtual Private Cloud): Isolated network environment in AWS.
- Elastic Load Balancing (ELB): Distributes traffic across EC2, containers, and Lambda.
- Amazon CloudFront: Global content delivery network (CDN).
- AWS Transit Gateway: Connects multiple VPCs and on-premises networks.
- AWS Direct Connect: Dedicated network connection between AWS and on-premises.

**Use Cases:** Hybrid connectivity, secure application access, global content delivery, network segmentation.

### 4. Database Services

Database services support structured and unstructured data workloads.

- Amazon RDS (Relational Database Service): Managed relational databases (MySQL, PostgreSQL, Oracle, SQL Server, MariaDB, Aurora).
- Amazon Aurora: High-performance, fully managed relational database compatible with MySQL and PostgreSQL.
- Amazon DynamoDB: Fully managed NoSQL key-value and document database.
- Amazon ElastiCache: Managed in-memory caching (Redis, Memcached).
- Amazon Neptune: Managed graph database service.

**Use Cases:** Transactional workloads, analytics, caching, key-value stores, graph applications.

### 5. Security, Identity & Compliance

Security services provide access management, encryption, and compliance.

- AWS IAM (Identity and Access Management): Fine-grained access control for AWS resources.
- AWS KMS (Key Management Service): Managed encryption key creation and control.
- AWS WAF (Web Application Firewall): Protects web apps from common exploits.
  AWS Shield: DDoS protection.
- Amazon GuardDuty: Intelligent threat detection and monitoring.
- AWS CloudTrail: Tracks and audits API calls.

**Use Cases:** Access management, encryption, compliance auditing, intrusion detection, threat protection.
