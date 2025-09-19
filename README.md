## AMAZON SECURE NETWORKING
### Getting started with Amazon Virtual Private Cloud (VPC)
This lab guides you through the process of configuring a VPC on aws. Starting with an overview of the default VPC and its components, then div ing into building a custom VPC from scratch. With this lab you should learn tfo create subnets, route tables,internet gateways, and NAT gateways, and configure security groups to control network traffic. By the end of this lab, you'll have a solid understanding of VPC networking concepts andpractgical experience inbuilding secure and scalable network infrastructure in AWS. 
### Prerequisites 
Before you begin this lab, make sure you have the following:
* Basic understanding of networking concepts
* An AWS account
* Willingness to learn
### Cost considerations
This lab creates AWS resources that may incur costs in your account. The primary cost comes from the NAT gateway ($0.045 per hour plus data processing charges) and EC2 instances (t2.micro, approximately $0.0116 per houjr each). If you complete this tutorial in one hour anhd then clean up all resources, the total cost will be approximately $0.07. For cost optimization in develolpment environments, consider using NAT instance instead of a NAT gateway, which can reduce costs significantly. 
## Understanding the Default VPC
AWS provides a default VPC in each region, offering a pre-configured network fcr launching instgances. Lets take a look at igts key components:
* Main Route Table: allows us to control traffic flow throughout the VPC and in and out of a VPC. They are associated with one or many subnets and affects all resources within those subnets.
* Main Network ACL (NACL): acts as a firewall at the subnet level, controlling  ingress and egress traffic. The default NACL allowss all traffic unless specified. 
* Subnets: Default VPCs include a subnet in each Availability Zone within the region, providing high availability. Each subnet is associated with the Main Route Table and NACL.
* Internet Gateway (IGW): The IGW allows communication between the VPC and the internet. The default VPC includes an IGW and a default route in the Main Route Table that sends all internet-bound traffic to the IGW.
  <img width="1915" height="883" alt="Screenshot 2025-09-19 125940" src="https://github.com/user-attachments/assets/1b202d39-bd12-4738-9402-7ef52b71be7c" />

** To inspect the Default VPC, navigate to the VPC Dashboard and select Your VPCs. You can explore each component from there.

## Configuring a custom VPC:
* Create a VPC: In the VPC dashboard, choose "create VPC". specify a name tag and a CIDR block (e.g., 10.0.0.0/16). Consider CIDR.xyz to determine suitable IPv4 address ranges.
  <img width="1759" height="862" alt="Screenshot 2025-09-19 124138" src="https://github.com/user-attachments/assets/a60d149a-bc3c-42d5-ba59-9778eb56ffd2" />
* Create subnet: Create four subnets within your VPC: two public and two private. Assign them non-overlapping CIDR blocks (e.g., 10.0.1.0/24, 10.0.2.0/24, 10.0.3.0/24, 10.0.4.0/24). Place each subnet in a different Availability Zone for redundancy.
* Create an Internet Gateway: Create an IGW and attach it to your custom VPC. This enables communication with the internet.

** These steps establish the foundation for your custom VPC, creating the network infrastructure required to connect your resources.
