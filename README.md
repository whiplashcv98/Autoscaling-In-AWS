# Autoscaling-In-AWS
This repository contains a hands-on guide and documentation for configuring and testing AWS Auto Scaling and an Application Load Balancer (ALB). The guide walks through the process of setting up a dynamic, scalable, and resilient web application environment on AWS.
Description
This project demonstrates how to use AWS services to manage and distribute traffic efficiently. By following the steps outlined, you will learn to:

Implement Auto Scaling: Automatically scale the number of EC2 instances in response to changes in demand, such as increased CPU utilization. This ensures your application can handle traffic spikes without manual intervention.

Configure a Load Balancer: Distribute incoming web traffic across multiple EC2 instances to improve application availability and responsiveness. This project specifically uses an Application Load Balancer (ALB) to route traffic.

Installation and Setup
To complete this hands-on lab, you will need an AWS account with the necessary permissions to create and manage EC2 instances, security groups, launch templates, auto-scaling groups, and load balancers.

Prerequisites:

An active AWS account.

Steps:

Launch Template Creation:

Create a security group that allows inbound traffic on ports 22 (SSH) and 80 (HTTP).

Create a Launch Template, specifying an AMI (e.g., Amazon Linux 2), instance type (e.g., t2.micro), and the security group you just created.

Auto Scaling Group (ASG) Creation:

Create an ASG, linking it to your Launch Template.

Set the desired capacity, minimum, and maximum instances (e.g., desired: 2, min: 1, max: 4).

Configure a target scaling policy based on CPU utilization (e.g., 50%).

Application Load Balancer (ALB) Setup:

Create a Target Group to register your EC2 instances.

Create an ALB, selecting your VPC and subnets.

Configure the ALB's listener to forward HTTP traffic on port 80 to your Target Group.

Usage
Once the infrastructure is set up, you can test the functionality of both the ASG and the ALB.

Test Auto Scaling: Connect to one of your EC2 instances and use a stress tool to simulate high CPU load. Observe how the ASG automatically launches new instances to handle the increased demand.

Test Load Balancer: Copy the DNS name of your ALB and paste it into a web browser. The ALB will distribute your requests between the running EC2 instances, showing the "Welcome to Server 1" or "Welcome to Server 2" page.


Cleanup
To avoid unnecessary charges, remember to clean up all resources after you have completed the lab:

Delete the Auto Scaling Group.

Delete the Application Load Balancer and its Target Group.

Terminate any remaining EC2 instances and delete the Launch Template.
