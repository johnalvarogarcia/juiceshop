# Implementing Juice Shop: A Vulnerable Web App on Amazon AWS

## Project Overview

Juice Shop is a purposefully vulnerable web application, designed for aspiring penetration testers to practice and hone their skills in a Capture The Flag (CTF) environment. This project involves setting up Juice Shop on a Virtual Private Cloud (VPC) using Amazon Web Services (AWS), with a focus on understanding the security implications of deploying instances in different subnet types. Below is a detailed step-by-step guide on how to set up Juice Shop on AWS.

## Detailed Description

In this project, we will:

1. **Create a Region, VPC, Subnet, and Security Group in AWS**.
2. **Launch an EC2 instance in a private subnet** to enhance security.
3. **Configure an internet gateway and route table** to enable SSH connections.
4. **Install and start Docker** on the virtual machine.
5. **Install Node.js and Juice Shop** on the virtual machine.

## Process

### Step 1: Set Up the AWS Environment

1. **Create a Region and VPC**:
   - Log into the AWS Management Console.
   - Select a region that is geographically closest to you for better performance.
   - Navigate to the VPC dashboard and create a new VPC. Assign a CIDR block (e.g., 10.0.0.0/16) to your VPC.

2. **Create Subnets**:
   - Within the VPC, create two subnets: one public and one private.
   - Assign appropriate CIDR blocks to each subnet (e.g., 10.0.1.0/24 for public, 10.0.2.0/24 for private).

3. **Create Security Groups**:
   - Define a security group with rules to allow SSH (port 22) from your IP address and HTTP (port 80) for Juice Shop access.
   - Apply this security group to your EC2 instance.

### Step 2: Launch an EC2 Instance

1. **Launch EC2 Instance in a Private Subnet**:
   - Go to the EC2 dashboard and launch a new instance.
   - Select an Amazon Machine Image (AMI) that suits your needs (e.g., Amazon Linux 2).
   - Choose an instance type (e.g., t2.micro for free tier eligibility).
   - Place the instance in the private subnet created earlier.
   - Assign the previously created security group to this instance.

### Step 3: Configure Network Components

1. **Set Up Internet Gateway and Route Table**:
   - Create an internet gateway and attach it to your VPC.
   - Update the route table associated with the public subnet to route traffic through the internet gateway.
   - For SSH access, configure a bastion host in the public subnet or set up a VPN connection to securely access the private subnet.

### Step 4: Install Docker

1. **Connect to the EC2 Instance**:
   - Use SSH to connect to your EC2 instance. If it's in a private subnet, use the bastion host or VPN for secure access.

2. **Install Docker**:
   - Update the package repository: `sudo yum update -y`.
   - Install Docker: `sudo yum install -y docker`.
   - Start Docker: `sudo service docker start`.
   - Add the EC2 user to the Docker group: `sudo usermod -aG docker ec2-user`.

### Step 5: Install Node.js and Juice Shop

1. **Install Node.js**:
   - Install Node.js using a package manager or nvm (Node Version Manager): `curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.35.3/install.sh | bash`.
   - Activate nvm: `source ~/.nvm/nvm.sh`.
   - Install Node.js: `nvm install node`.

2. **Deploy Juice Shop**:
   - Pull the Juice Shop Docker image: `docker pull bkimminich/juice-shop`.
   - Run the Juice Shop container: `docker run -d -p 3000:3000 bkimminich/juice-shop`.
   - Verify the deployment by navigating to the instance's IP address on port 3000 in your web browser.

## Conclusion

This project provided hands-on experience with AWS infrastructure, networking, and security configurations, as well as practical knowledge of deploying a vulnerable web application for penetration testing purposes. By setting up Juice Shop in a private subnet and configuring essential network components, we ensured a secure environment for testing and learning. This setup not only demonstrates technical proficiency but also a strong understanding of cloud security practices.


<h2>Platforms and Technologies Used</h2>

- <b>Amazon AWS</b> 
- <b>EC2 Virtual Machines</b>
- <b>Docker</b>


<p align="center">
Juce Shop initialized: <br/>
<img src="https://i.imgur.com/7ZZDg4I.png" height="80%" width="80%"/>
<br />
<br />


<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
