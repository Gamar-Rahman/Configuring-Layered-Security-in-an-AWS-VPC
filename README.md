# Configuring-Layered-Security-in-an-AWS-VPC
Hands-on AWS lab demonstrating layered security in Amazon VPC using Security Groups and Network ACLs to control traffic at both the instance and subnet levels.
# Understanding and Configuring Layered Security in an AWS VPC

## Overview

This lab explores how **layered security** is implemented in Amazon VPC using **Security Groups** and **Network Access Control Lists (NACLs)**.

The objective was to design a VPC architecture where traffic is controlled at multiple levels to improve the security posture of cloud resources.

In this environment I built a custom VPC, configured routing and internet access, deployed EC2 instances, and implemented layered network security using both **instance-level and subnet-level controls**.

This approach reflects how modern cloud environments implement **defense-in-depth networking strategies**.

---

# What is Layered Security?

Layered security, also known as **defense-in-depth**, means protecting systems using multiple security controls rather than relying on a single protective layer.

In AWS networking this commonly includes:

• VPC network isolation  
• Subnet segmentation  
• Security Groups  
• Network ACLs  
• Routing control  

Each layer provides an additional security boundary that helps reduce the impact of misconfiguration or compromise.

---

# What is Amazon VPC?

Amazon **Virtual Private Cloud (VPC)** allows you to create a logically isolated network within AWS where resources such as EC2 instances, databases, and load balancers can run securely.

A VPC allows organizations to control:

- IP address ranges using CIDR blocks
- Subnets within the network
- Route tables controlling traffic flow
- Internet access
- Security boundaries using security groups and NACLs

Custom VPC design is fundamental for building **secure and scalable cloud infrastructure**.

---

# What are Security Groups?

Security Groups act as **virtual firewalls for EC2 instances**.

Key characteristics:

• Stateful filtering  
• Instance-level protection  
• Rules based on ports, protocols, and IP ranges  

Example:
Allow SSH (port 22) only from trusted IP addresses.

If inbound traffic is allowed, the response is automatically allowed.

---

# What are Network ACLs?

Network Access Control Lists (NACLs) operate at the **subnet level**.

Key characteristics:

• Stateless filtering  
• Controls inbound and outbound traffic  
• Applied to entire subnets  
• Rules evaluated in numbered order

Because NACLs are stateless, return traffic must be explicitly allowed.

This provides an **additional network-level filtering layer**.

---

# Why This Lab Matters

Cloud infrastructure can become complex very quickly.

If security is implemented only at a single layer, misconfigurations can expose resources unintentionally.

Layered security helps ensure that:

• Multiple controls protect resources  
• Misconfigurations are less likely to cause exposure  
• Network segmentation is enforced  
• Attack surface is minimized

For security teams, this layered design improves resilience and reduces risk.

---

# Problem Solved

The key question explored in this lab was:

**How can we protect cloud resources using multiple network security layers instead of relying on a single firewall rule?**

Single-layer security increases risk because one misconfiguration can expose resources.

This lab demonstrates how **Security Groups and NACLs work together to protect workloads**.

---

# Why This Solution Makes Sense

Using layered security provides several advantages:

• Instance-level filtering with Security Groups  
• Subnet-level filtering with NACLs  
• Network segmentation using subnets  
• Controlled internet access via routing rules  

If one control layer is misconfigured, another layer can still protect the resource.

This architecture reflects common **enterprise cloud security practices**.

---

# Architecture Built in This Lab

Components created:

• Custom Amazon VPC  
• Internet Gateway  
• Public and Private Subnets  
• Route Tables  
• Security Groups  
• Network ACLs  
• Two EC2 Instances  

---

# Lab Steps

## 1. Create a VPC
A custom VPC was created to provide a logically isolated network environment.

## 2. Attach Internet Gateway
An Internet Gateway was attached to enable internet communication.

## 3. Create Subnets
Two subnets were created to simulate segmented network architecture.

## 4. Configure Route Tables
Route tables were created and associated with the subnets to control traffic flow.

## 5. Create Security Groups
Security groups were configured to control instance-level traffic.

## 6. Configure Network ACL
A Network ACL was configured to filter traffic at the subnet level.

## 7. Launch EC2 Instances
Two instances were launched within the VPC to test connectivity.

## 8. Test Connectivity
Traffic behavior was tested to confirm that security rules were applied correctly.

---

# How It Works

1. Traffic enters the VPC through the Internet Gateway.
2. Route tables determine where traffic should go.
3. Network ACL evaluates subnet-level rules.
4. Security Groups evaluate instance-level rules.
5. Only traffic that passes all layers reaches the EC2 instance.

This multi-layer inspection ensures better control over network communication.

---

# Security Insight

One of the most common cloud security issues is **overly permissive network access**.

Layered security helps mitigate this risk by implementing **multiple checkpoints for traffic validation**.

This lab reinforces a key cloud security principle:

**Never rely on a single security control.**

Instead, combine multiple layers to enforce strong security boundaries.

---

# Skills Demonstrated

AWS VPC architecture  
Subnet segmentation  
Internet Gateway configuration  
Route table management  
Security Group configuration  
Network ACL configuration  
EC2 deployment  
Layered cloud security design

---

# Key Security

Secure cloud architecture requires more than launching resources.

It requires **carefully designed network controls and layered defenses** that regulate how traffic flows through the infrastructure.

Layered security using **Security Groups and Network ACLs** is a foundational concept for building secure AWS environments.


