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
** To inspect the Default VPC, navigate to the VPC Dashboard and select Your VPCs. You can explore each component from there.