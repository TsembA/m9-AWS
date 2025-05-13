
# AWS Services Overview ☁️ + Demo Project

This document provides an overview of various AWS services and their use cases, including IAM, EC2, VPC, and more.

---

## 1. AWS Services 🌐

AWS offers a variety of services for cloud infrastructure management, development, and scaling applications. Some of the core services include:

- **EC2**: Virtual servers in the cloud.
- **S3**: Scalable storage for objects.
- **VPC**: Virtual Private Cloud for creating isolated networks.
- **IAM**: Identity and Access Management for managing user access.
- **ECR**: Elastic Container Registry for storing Docker images.
- **ECS**: Elastic Container Service for managing containers.
- **EKS**: Elastic Kubernetes Service for managing Kubernetes clusters.

### Service Scopes 🔄

- **Global**: Services like IAM that span all regions (e.g., IAM).
- **Region**: Services tied to specific regions (e.g., S3, VPC).
- **AZ (Availability Zone)**: Specific data center locations within a region.

---

## 2. IAM - Identity and Access Management 🔑

### What is IAM?

IAM allows you to create and manage AWS users and assign permissions to control access to AWS resources.

### Best Practices for IAM:

- **Create an Admin User**: Instead of using the root user, create an admin user with limited privileges and then assign other permissions.
- **Use Groups**: Manage permissions by assigning them to groups rather than individual users for easier management.
- **IAM Roles**: Policies can’t be directly attached to AWS services but must be applied via IAM roles.
  
---

## 3. Regions and Availability Zones (AZ) 🌎

- **Region**: A physical location that contains multiple data centers (e.g., `us-west-2`).
- **Availability Zone (AZ)**: Multiple physical data centers within a region. AWS aims to have at least three AZs in every region.

---

## 4. VPC - Virtual Private Cloud 🏞️

VPC is a virtual network that you can configure to isolate your AWS resources.

- **Internet Gateway**: Connects the VPC to the internet.
- **NACL**: A firewall at the subnet level to control traffic in and out of your VPC.
- **Security Groups**: A firewall at the instance level, controlling inbound and outbound traffic.

---

## 5. CIDR Blocks

CIDR (Classless Inter-Domain Routing) blocks define IP address ranges. The number after the `/` determines the subnet size.

- Example: `176.31.0.1/24` - This defines a range of IP addresses for your network.

---

## 6. AWS CLI  💻

### Installation

Install AWS CLI using the following command for macOS:

```bash
brew install awscli
```

After installation, configure it with:

```bash
aws configure
```

You will be prompted to enter your **Access Key ID**, **Secret Access Key**, **Region**, and **Output Format**.

---

## 7. Common AWS EC2 Commands 🖥️

Here are some commonly used AWS EC2 commands:

- **Run EC2 Instances**:

    ```bash
    aws ec2 run-instances --image-id <ami-id> --count <number> ...
    ```

- **Describe VPCs**:

    ```bash
    aws ec2 describe-vpcs
    ```

- **Create Security Group**:

    ```bash
    aws ec2 create-security-group --group-name <group-name> --description <description>
    ```

- **Authorize Security Group Ingress**:

    ```bash
    aws ec2 authorize-security-group-ingress --group-id <group-id> --protocol tcp --port 22 --cidr <cidr-block>
    ```

- **Create Key Pair**:

    ```bash
    aws ec2 create-key-pair --key-name <key-name>
    ```

- **Describe Subnets**:

    ```bash
    aws ec2 describe-subnets
    ```

---

## 8. Common AWS IAM Commands  🔐

Here are some commonly used IAM commands:

- **Create Group**:

    ```bash
    aws iam create-group --group-name <group-name>
    ```

- **Create User**:

    ```bash
    aws iam create-user --user-name <user-name>
    ```

- **Add User to Group**:

    ```bash
    aws iam add-user-to-group --user-name <user-name> --group-name <group-name>
    ```

- **Get User**:

    ```bash
    aws iam get-user --user-name <user-name>
    ```

- **List Policies**:

    ```bash
    aws iam list-policies
    ```

- **Attach Policy to User**:

    ```bash
    aws iam attach-user-policy --user-name <user-name> --policy-arn <policy-arn>
    ```

- **Create Login Profile for User**:

    ```bash
    aws iam create-login-profile --user-name <user-name> --password <password>
    ```

- **Create IAM Policy**:

    ```bash
    aws iam create-policy --policy-name <policy-name> --policy-document <json-policy-document>
    ```

---

## Conclusion

AWS offers a wide variety of services and tools for managing cloud infrastructure, security, and containerized applications. By using the AWS CLI and following best practices for IAM and VPC setup, you can efficiently manage your AWS environment.

---
