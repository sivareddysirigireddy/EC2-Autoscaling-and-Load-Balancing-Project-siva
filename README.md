# EC2-Autoscaling-and-Load-Balancing-Project-siva
I WANT TO EXPOSE MY PROJECT 
<img width="931" height="649" alt="ASG" src="https://github.com/user-attachments/assets/040e4812-3338-4d05-9150-ed55016c6f7b" />
This project is designed to showcase the implementation of autoscaling and load balancing for EC2 instances on AWS.

Below, you'll find an overview of the project, including resources utilized and setup instructions.

Overview
The EC2 Autoscaling and Load Balancing project leverages AWS services to ensure high availability, scalability, and fault tolerance for applications running on EC2 instances.

By combining autoscaling and load balancing, the project achieves dynamic scaling of resources based on demand and distributes incoming traffic evenly across multiple instances.

Resources Utilized
The following AWS resources are utilized in this project:

VPC (Virtual Private Cloud): A new VPC is created to isolate the network environment for the EC2 instances.

Security Group: Security groups are configured to control inbound and outbound traffic to the EC2 instances.

Target Group: Target groups are used to route traffic to the registered EC2 instances within the autoscaling group.

Load Balancer: Application Load Balancer is configured to distribute incoming traffic across multiple EC2 instances.

Launch Template: A launch template is created to define the configuration settings for the EC2 instances launched by the autoscaling group.

Autoscaling Group: An autoscaling group is configured to automatically adjust the number of EC2 instances based on metrics such as CPU utilization or network traffic.

Benefits:
Scalability: The autoscaling group automatically provisions additional instances when traffic increases, ensuring smooth performance even during peak loads.

High Availability: The load balancer distributes traffic across healthy instances, preventing a single point of failure. If an instance becomes unhealthy, the autoscaling group automatically replaces it.

Cost Optimization: By automatically scaling resources based on demand, you only pay for the compute power you actually use.

Setup :
1. VPC Creation:
Create a new VPC in the AWS Management Console to isolate the network environment for the EC2 instances.

Enrollment

Enrollment

Enable auto-assign public IPv4 address to your Public1 and Public2 subnet
Enrollment

Enrollment

2. Security Group Configuration:
Create 2 Security groups.

1. ALB to accept HTTP inbound traffic from anywhere

Enrollment

2. Web-sg-1 to accept HTTP inbound traffic from ALB

Enrollment

3. Target Group Setup:
Set up a target group to route traffic to the registered EC2 instances within the autoscaling group. Define health checks and protocols.

Vpc = Vpc you created

Enrollment

4. Load Balancer Configuration:
Configure an Application Load Balancer to distribute incoming traffic across multiple EC2 instances. Define listeners and routing rules.

1. Select ALB

Enrollment

2. ALB Configuration

Enrollment

5. Launch Template Creation:
Create a launch template to define the configuration settings for the EC2 instances launched by the autoscaling group.

1. Choose an AMI from the Catalog

Enrollment

2. Select the preferred instance from the Instance type

Enrollment

3. On Advance details scroll to the User data and paste the user data provided.

Enrollment

6.Autoscaling Group Configuration:
Configure an autoscaling group to automatically adjust the number of EC2 instances based on metrics such as CPU utilization or network traffic.

Associate the autoscaling group with the launch template and target group.

Enrollment

Enrollment

Enrollment

Enrollment

