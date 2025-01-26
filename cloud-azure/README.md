# Cloud - Fundamentals

## Table of Contents
- [What is the Cloud?](#what-is-the-cloud)
- [Cloud Service Models](#cloud-service-models)
- [Understanding Virtual Networks (VNet) and Subnets](#understanding-virtual-networks-vnet-and-subnets)
- [Planning and Creating a Virtual Network in Azure](#planning-and-creating-a-virtual-network-in-azure)
- [Creating a Virtual Machine in Azure](#creating-a-virtual-machine-in-azure)
- [Deleting Azure Resources](#deleting-azure-resources)
- [Generating SSH Keys](#generating-ssh-keys)
- [Azure Usage Guidelines](#azure-usage-guidelines)

---

## What is the Cloud?

### Definition
- **Centrally Managed**: Resources are monitored and controlled by a central authority.
- **Accessible Over the Internet**: Resources and services can be used from anywhere with internet access.

### Key Components
- **Virtual Machines (VMs)**: Compute resources for running applications.
- **Virtual Networks (VNets)**: Secure networking infrastructure connecting resources.
- **Databases (DBs)**: Structured storage systems for persistent data.
- **Storage Services**: Solutions for storing files and data (e.g., AWS S3, Azure Blob Storage).

### Key Concept
The cloud provides scalable infrastructure to optimise resource management and deployment.

---

## Cloud Service Models

### Deployment Options
- **On-Premises**: Full responsibility for hardware, software, and data.
- **Cloud Models**:
  - **Infrastructure as a Service (IaaS)**: User manages applications and data; the provider handles infrastructure.
  - **Platform as a Service (PaaS)**: Users focus on applications while the provider manages the platform.
  - **Software as a Service (SaaS)**: Fully managed software solutions provided by the service.

### Responsibility Shift
As deployment moves from On-Premises to SaaS, user responsibility decreases while the provider assumes more management tasks.

---

## Understanding Virtual Networks (VNet) and Subnets

### Virtual Network (VNet)
- **Analogy**: Think of a VNet as a digital apartment building providing secure spaces for resources.
- **CIDR Block**: Defines the IP address range (e.g., `10.0.0.0/16` provides ~65,000 IPs).

### Subnets
- **Analogy**: Subnets are like rooms within the VNet apartment.
- **Subnet CIDR Block**: Subnets divide the VNet's space (e.g., `10.0.2.0/24` provides 256 IPs).

---

## Planning and Creating a Virtual Network in Azure

### Planning Steps
1. **Naming Convention**: Use `project-[name]-vnet`.
2. **CIDR Block**: Allocate `10.0.0.0/16` for the VNet.
3. **Subnets**:
   - Public Subnet: `10.0.2.0/24`
   - Private Subnet: `10.0.3.0/24`

### Creation Steps
1. **Basic Configuration**:
   - Name: `project-[name]-vnet`
   - Region: UK South
   - CIDR Block: `10.0.0.0/16`
2. **Create Subnets**:
   - Public Subnet: `10.0.2.0/24`
   - Private Subnet: `10.0.3.0/24`
3. **Add Tags**:
   - Use a naming convention like `owner: [Your Name]`.

---

## Creating a Virtual Machine in Azure

### VM Specifications
- **Name**: `project-[name]-vm`
- **Region**: UK South
- **Image**: Ubuntu Pro 18.04 LTS Gen2
- **Size**: Standard_B1s (1 vCPU, 1 GiB RAM)
- **Admin Username**: `adminuser`
- **SSH Key Pair**: Use an existing or generated key.

### Configuration Steps
1. **Network Settings**:
   - Virtual Network: Use `project-[name]-vnet`.
   - Subnet: Select the public subnet.
   - Allow inbound SSH and HTTP traffic.
2. **Disks**:
   - OS Disk Type: Standard SSD.
3. **Tagging**:
   - Add tags such as `owner: [Your Name]`.

### Connect to the VM
```bash
ssh -i ~/.ssh/[your_key].pem adminuser@[vm_public_ip]
