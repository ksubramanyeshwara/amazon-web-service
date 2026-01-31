# Simple Storage Service (S3)

- It is an object storage service that stores data as objects within buckets.
- It is highly available, scalable and secure cloud storage service.
- It allows you to store and retrieve any amount of data from anywhere on the web.
- It is commonly used for storing and retrieving files, images, videos, backups, and other types of data.

## Key Features

- Availability: 99.99% availability(Varies by storage class)
- Durability: 99.999999999% durability.
- Scalability: Unlimited storage capacity. It should not more than 5TB per object.
- Versioning: Enables keeping multiple versions of an object; protects against accidental overwrites/deletes.
- Security: Supports encryption, access control, and compliance requirements.
- Lifecycle Management: Automatically transition objects to different storage classes or delete them after a specified period.

> AWS ensures availability by replicating data across multiple data centers within an AWS region.

## Core Concepts of S3

- **Buckets**:
  - Containers for storing objects.
  - Must have globally unique names accross all AWS accounts.
  - Created in specific AWS region.
  - Can have unlimited number of objects.
  - By default 100 buckets per account.
- **Objects**:
  - Files stored in buckets(Documents, images, videos, backups, etc.)
  - Consists of:
    - Key: unique name for a single object in a bucket(file path). Example: photos/vacation/beach.jpg
    - Value: actual data (max 5TB)
    - Metadata: key-value pairs describing object
    - Version ID: if versioning enabled
    - Tags: for categorization

## Storage Classes

| Class                   | Use Case                                                        | Availability | Min Storage Duration |
| ----------------------- | --------------------------------------------------------------- | ------------ | -------------------- |
| S3 Standard             | Frequent access, low latency                                    | 99.99%       | None                 |
| S3 Intelligent-Tiering  | Unknown/changing access patterns                                | 99.9%        | None                 |
| S3 Express One Zone\*\* | High performance, for your most frequently accessed data        | 99.99%       | 30 days              |
| S3 Standard-IA          | Infrequent access, long-lived                                   | 99.9%        | 30 days              |
| S3 One Zone-IA          | Recreatable, infrequently accessed data                         | 99.5%        | 30 days              |
| S3 Glacier Instant      | Long-lived data, few times access/year, instant retrievals      | 99.9%        | 90 days              |
| S3 Glacier Flexible     | Backup and archive data, rarely access, minutes-hours retrieval | 99.99%       | 90 days              |
| S3 Glacier Deep Archive | Archive data, very rarely access, 12-48 hours retrieval         | 99.99%       | 180 days             |

## Security & Access Control

### Encryption:

- Server-Side (SSE-S3, SSE-KMS, SSE-C)
- Client-Side
- Default encryption at bucket level

### Access Management:

- IAM policies (user/role-based)
- Bucket policies (JSON-based resource policies)
- S3 Access Points (simplified management for shared datasets)
- Block Public Access (bucket/ account settings)

### Logging & Monitoring

- Access logs, CloudTrail integration, CloudWatch metrics.

## Use Cases

- Storing static website content (HTML, CSS, JS, images).
- Backup and restore.
- Hosting media assets like images, videos, and audio files.
- Storing logs, IoT data, or ML training datasets.
- Disaster recovery storage across regions.
