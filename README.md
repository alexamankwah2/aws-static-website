![Alt text](/Host_a_Static_Website_on_AWS.png)

# AWS Static Website Hosting on EC2
This project demonstrates how to host a static HTML web application on AWS using EC2 instances and a Virtual Private Cloud (VPC) with various AWS services to ensure reliability, scalability, and security.

## Architecture Overview
The architecture includes the following key components:

**VPC:** Configured with public and private subnets across two Availability Zones (AZs) for fault tolerance and high availability.
**Internet Gateway:**  Provides Internet access for resources in public subnets.
**Security Groups:**  Act as virtual firewalls to control traffic to and from EC2 instances.
**Availability Zones:**  Improve system reliability by distributing resources across multiple AZs.
**Public Subnets:**  Host infrastructure components like the NAT Gateway and Application Load Balancer.
**Private Subnets:**  Host EC2 instances (web servers) to limit exposure to the public Internet.
**EC2 Instance Connect Endpoint:** Used for secure SSH access to instances in both public and private subnets.
**NAT Gateway:** Allows EC2 instances in private subnets to access the Internet for updates.
**Application Load Balancer (ALB):** Evenly distributes traffic across EC2 instances.
**Auto Scaling Group:** Automatically adjusts the number of EC2 instances to handle traffic and maintain availability.
**SSL/TLS with AWS Certificate Manager:** Secures communications to the website.
**Amazon SNS:** Sends notifications related to Auto Scaling Group activity.
**Route 53:** Manages the domain name and DNS settings.

## Architecture Diagram
You can view the architecture diagram here.

## Technologies Used
Amazon EC2
VPC (Virtual Private Cloud)
Auto Scaling Group
Application Load Balancer
NAT Gateway
Security Groups
Amazon Route 53
AWS Certificate Manager
Amazon SNS
GitHub for version control


## Deployment Instructions
**Clone the repository:**
bash
Copy code
git clone https://github.com/your-repo-link

**Set up AWS Infrastructure:** Use the provided CloudFormation templates or Terraform scripts to set up the VPC, subnets, NAT Gateway, security groups, EC2 instances, and Load Balancer.

**Deploy the Web Application:** Upload the static HTML files to the EC2 instances using SSH or SCP.

**Configure Load Balancing and Auto Scaling:** Set up the Auto Scaling Group and Application Load Balancer to handle traffic distribution and instance scaling.

**Enable SSL/TLS:** Obtain an SSL/TLS certificate via AWS Certificate Manager and configure it with the Load Balancer for secure communication.

**Configure DNS with Route 53:** Register a domain and set up DNS records to point to the Application Load Balancer.

## Monitoring and Notifications

**Amazon SNS** is used to send alerts regarding Auto Scaling Group activities.
**Amazon CloudWatch** can be used to monitor the performance and logs of the EC2 instances and the application.

## Conclusion

This project demonstrates how to securely host a static website on AWS, using best practices for scalability, security, and fault tolerance.
