# Virtual Private Cloud (VPC)

- VPC is logically isolated virtual network within AWS.
- VPC allows you to securely launch and manage resources such as EC2 instances, databases, and load balancers.
- Its like a Virtual data center in the cloud.

> VPC acts as the backbone for how your applications communicate securely within AWS and with external networks.

## Key Components

- CIDR Block (Classless Inter-Domian Routing)
- Subnets
- Internet Gateway(IGW)
- Route Tables
- Network Access Translation(NAT) Gateway
- Security Groups and NACLs

## CIDR block

- Defines the IP range for your VPC
- You cannot change the primary CIDR after creation.

## Subnet

- Logical subdevision of a VPC's IP address range.
- Subnets determine how AWS resources communicate with each other and with the outside world.
- Each subnet is associated with a single Availability Zone (AZ).
- Types:
  - Public Subnet
    - Has route to the internet through Internet Gateway(IGW)
    - Used for: Load balancers, Bastion hosts, Web servers that need to be accessible from the internet
    - EC2 instance in a public subnet with a public IP can be accessed via SSH or HTTP from the internet.
  - Private Subnet
    - No direct internet access
    - Used for: App servers, Databases, Internal services.
    - An RDS instance in a private subnet is not exposed to the internet but can be accessed by an EC2 instance in the public subnet.

### How Subnets Isolate Resources

- Routing Isolation (MOST IMPORTANT)
  - each subnet is associated with one route table and it decides where traffic can go.
  - If there is no route, traffic cannot flow.
- Internet Access Isolation
  - Subnets do NOT automatically get internet.
  - Internet access requires:
    - Internet Gateway attached to VPC
    - Route table entry to Internet Gateway(IGW)
    - IGW needs a public IP to know where to send the internet’s reply.
  - Private subnet:
    - No Internet Gateway(IGW) route
    - No inbound internet access
- Security Boundary Using NACLs
  - Network ACLs (NACLs) are applied at subnet level.
  - Allow & Deny rules
  - Example:
    - Allow HTTP only
    - Deny all SSH traffic

## Internet Gateway(IGW)

- Enables internet access for VPC resources.
- It allows outbound internet connections while blocking unsolicited inbound internet connection.
- A VPC can have only one attached Internet Gateway at a time.

## Route Tables

- It defines how network traffic is directed.
- Contains set of rules(routes), that determines where traffic from subnet and gateway should be sent.
- Every subnet must be associated with a route table.
  - A destination CIDR block (where the traffic is headed).
  - A target (where the traffic should be sent, such as an Internet Gateway, NAT Gateway, or another instance)

### Types

- Main Route Table: Created by default with every VPC and automatically associated with all subnets unless explicitly overridden.
- Custom Route Tables: You can create additional route tables and associate them with specific subnets for more control.
- Routes: Each entry specifies a destination CIDR block and a target (IGW, NAT Gateway, VPC Peering, Transit Gateway, etc.).

## Network Access Translation(NAT) Gateway and NAT Instance

- Allows private subnet resources to access the internet for patching, package downloads, container pulls, or calling third‑party APIs.
- Prevents inbound internet traffic
- NAT Gateway:
  - Managed by AWS
  - Highly available
- NAT Instance:
  - EC2-based
  - Manual maintenance

## Security Groups and Network Access Control Lists(NACLs)

### Security Groups

- Stateful Virtual firewall for EC2 instances and other resources (e.g., RDS, Lambda ENI).
- Rules apply to individual instances (like EC2), not entire subnets.
- Rules
  - Allow only (no deny rules).
  - All inbound traffic is denied by default.
  - all outbound traffic is allowed by default.

> Stateful virtual firewall that remembers outgoing requests and automatically lets the "replies" back in without needing extra rules and vice-versa.

> PORT 25 is blocked by default to stop people from using their servers to send millions of spam emails.

### Network Access Control Lists (NACLs):

- Stateless virtual firewall for subnets.
- Operate at the subnet level.
- Rules
  - Explicit allow and deny rules, evaluated in order (by rule number).
  - Allows all inbound and outbound traffic by default.
