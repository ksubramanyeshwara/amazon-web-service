# EC2 (Elastic Compute Cloud)

- It is a virtual server that provides resizable compute capacity in the cloud.
- It provides different OS like, Linux, Mac, Windows etc
- It allows running applications without having to invest in and manage physical hardware.

**Virtual Server**

- It is a software based server that acts like a physical server.
- It is created by partitioning a single physical server into multiple isolated server(environment) using virtualization(Hypervisor).

## Key Features

- Scalability on-demand
- Customizable (Different OS)
- Global availability (regions & AZs)
- Versatile: Host a simple website, run database, AI/ML training, big data, etc.
- Pay only for what you use with options to scale up and down.
- Secure by design: Intigrated with IAM, VPC(Virtual Private Cloud).

**Use Cases**

- Hosting web applications (e.g., WordPress, e-commerce sites).
- Running enterprise applications (ERP, LMS, CRM systems).
- Performing AI/ML model training and inference.
- Running CI/CD pipelines for DevOps automation.
- Hosting game servers or real-time applications.

## AMI - Amazon Machine Image

- It ia a pre-configured template to create instance.
- It includes OS, application server and applications that will run on this instance.
- When you launch an EC2 instance, you must specify an AMI.

### Key Components of an AMI:

- Operating System (OS): Linux, Windows, macOS, or custom OS.
- Application Stack: Pre-installed software such as web servers, databases, or development tools.
- Launch Permissions: Controls which AWS accounts can use the AMI.
- Block Device Mapping: Defines the volumes to attach when the instance

## EC2 Instance Types

- General Purpose
- Compute optimized
- Memeory optimized
- Storage optimized
- Accelerated Computing

> Latency is the time delay between an action (like clicking a link) and the system's response

### General purpose

- Balanced compute, memory, and networking.
- Web servers, small databases, development and test environments.

## Compute Optimized

- CPU heavy for compute intensive task
- Batch processing, media transcoding, high-performance web servers, scientific modeling.

## Memory Optimized

- For processing large data sets.
- In-memory databases (SAP HANA, Redis), real-time big data analytics.

## Storage Optimized

- Optimized for high-speed local storage access. They handle massive read/write operations.
- NoSQL databases (Cassandra, MongoDB), data warehousing, log processing.

## Accelerated Computing

- Uses hardware accelerators (GPUs or ASICs) for specialized tasks
- 3D rendering, machine learning training, video encoding.

- Search for EC2 and select EC2 instance
- Click Launch Instance
- Give a name and select the AMI
- Select free tier eligible for your AMI
- Click on Generate new key pair
  - give a Key pair name
  - Key pair type - RSA
  - Choose .pem format
  - click on Create key pair
- Do not change anything in network settings(Will comeback later)
- Click on Launch instance

> You can click on instance id to get complete details

- ssh -i key-pair.pem AMI@Public IPv4 address
- If you get WARNING: UNPROTECTED PRIVATE KEY FILE! then change the file permission
- chmod 600 key-pair.pem
- ssh -i key-pair.pem AMI@Public IPv4 address
- Update the packages `sudo apt update`

Now you have logged onto EC2 instance through terminal.
