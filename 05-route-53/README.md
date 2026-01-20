# Route 53

- Route 53 is a scalable DNS(Domain Name System) service.
- It helps to route the traffic to your application reliably and with low latency.
- Route 53 refers to the standard DNS port 53.

## Core Function (What Route 53 does)

- DNS Name Resolution
  - Translates domain names (example.com) to IP addresses (like 54.x.x.x).
- DNS Routing
  - Routes end-user requests to appropriate resources (EC2, ALB, CloudFront).
  - Uses routing policies (Simple, Weighted, Latency, Failover, etc.) to send request to appropriate resources.
- Health Checking & Failover
  - Periodically checks endpoint health (HTTP/HTTPS, TCP).
  - Stops returning unhealthy IPs. (When a resource becomes unhealthy, Route 53 removes its IP address from DNS answers and routes traffic only to healthy endpoints.)
  - Routes traffic only to healthy resources.

## Core Components

- Domain Registration
  - Buy and manage domain names (e.g., example.com).
- Hosted Zones(DNS hosting)
  - Container for DNS records of a domain.
    - Public Hosted Zone: internet-facing DNS.
    - Private Hosted Zone: internal DNS for VPCs.
- DNS Records
  - Define how traffic is directed.
  - Examples: A, AAAA, CNAME, Alias

## Common DNS record types

- A record: Maps a domain name to an IPv4 address (e.g., example.com → 192.0.2.1).
- AAAA record: Maps a domain name to an IPv6 address (e.g., example.com → 2001:db8::1).
- CNAME(Canonical Name): Creates an alias from one domain name to another (e.g., www.example.com → example.com).
- MX (Mail Exchanger): Directs email traffic to the correct mail server.
- TXT Record (Text Record): Stores text information associated with a domain. Used for domain verification.
- NS Record (Name Server): Tells the internet where to find your domain's DNS information.
- Alias Record (AWS-specific)
  - Points directly to AWS resources
  - No extra cost, auto-updates IPs
  - Used for:
    - CloudFront.
    - Load Balancer.
    - S3 static websites.

## Routing Policies

- Simple Routing
  - Routes traffic to a single resource, like one web server.
- Weighted Routing
  - Traffic is distributed across multiple resources based on assigned weights (e.g., 70% to one server, 30% to another).
  - Useful for A/B testing or gradual migrations.
- Latency-based Routing
  - Routes users to closest region with low latency.
- Failover Routing
  - Automatically redirects traffic to a backup resource if the primary one becomes unhealthy.
- Geolocation Routing
  - Routes traffic based on the user's geographic location.
- Geoproximity Routing
  - Routes traffic based on the geographic location of your resources and your users.
- Multivalue Answer Routing
  - Returns multiple healthy IP addresses, allowing client-side load balancing.

## Key Features

- High Availability: Built on AWS's global infrastructure, designed for 100% availability SLA.
- Scalability: Automatically scales to handle large query volumes without manual intervention.
- Integration with AWS Services: Works seamlessly with other AWS services like EC2, S3, CloudFront, and Elastic Load Balancing.
- DNSSEC: Supports DNS Security Extensions to protect against DNS spoofing and cache poisoning attacks.
