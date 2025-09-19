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