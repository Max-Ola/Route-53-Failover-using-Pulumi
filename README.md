# Route-53-Failover-using-Pulumi

Thw code here is written in python using the Pulumi framework to create two identical three-tier web applications in two different regions (US-EAST-1 and US-EAST-2) with a failover Route 53 routing policy. Here's an explanation of what the code does:

The code defines a list of regions to create the resources in, an AMI to use for the EC2 instances, and the size of the instances and RDS instance.

It also defines a database name, username, and password, a Route 53 DNS name and domain, and the number of EC2 instances to create.

The code then creates an EC2 security group that allows inbound traffic on port 80, a launch configuration for the EC2 instances, and a target group for the load balancer.

It also creates an autoscaling group for the EC2 instances, which automatically scales the number of instances based on demand, and a RDS database instance.

The code then defines the Route 53 record sets for the DNS failover policy, which point to the load balancer in each region.

Finally, the code creates a load balancer for the web application in each region, which distributes traffic to the EC2 instances.

Overall, the code creates a highly available web application with automatic failover between regions using Route 53 and load balancing to ensure that the application can continue to serve traffic even in the event of an outage in one of the regions.

This exercise would also be performed with other IaC tools such as Ansible, CloudFormation, Terraform or even Saltstack. I chose python due to it's versatility and easy-to-read syntax. Also, this code would be easily upgradeable without breaking the underlying infrastructure supporting the application.
