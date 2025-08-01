EC2 Autoscaling and Load Balancing
<img width="931" height="649" alt="ASG" src="https://github.com/user-attachments/assets/fdb1ca72-1a7c-40f0-b2ca-5203d8987a1d" />
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
<img width="797" height="601" alt="Vpc" src="https://github.com/user-attachments/assets/c89ad8a7-00e0-4ae1-b551-d7e15f2a5d50" />
<img width="1451" height="626" alt="VPC2" src="https://github.com/user-attachments/assets/8750c45c-2c7a-4044-a835-f103d7c35311" />
Enable auto-assign public IPv4 address to your Public1 and Public2 subnet
<img width="1456" height="479" alt="publicipv4" src="https://github.com/user-attachments/assets/33bc1815-f34f-45d0-8a45-b439620d8ed4" />
<img width="1456" height="479" alt="Enable-Auto-assgn" src="https://github.com/user-attachments/assets/95fd5361-5fae-483a-b4fc-ba926eb0bd0e" />
2. Security Group Configuration:
Create 2 Security groups.
1. ALB to accept HTTP inbound traffic from anywhere
   <img width="1451" height="626" alt="ALB-sg" src="https://github.com/user-attachments/assets/718ebc8f-4677-46ec-94f5-b91c6d91ffca" />
2. Web-sg-1 to accept HTTP inbound traffic from ALB
   <img width="1451" height="756" alt="web-sg-1" src="https://github.com/user-attachments/assets/ba41389a-2014-4a8d-9196-6e4d6c391d42" />
3. Target Group Setup:
Set up a target group to route traffic to the registered EC2 instances within the autoscaling group. Define health checks and protocols.
Vpc = Vpc you created
   <img width="1339" height="544" alt="TG1" src="https://github.com/user-attachments/assets/2228171b-11a4-4926-9e02-3c4205971492" />
4. Load Balancer Configuration:
Configure an Application Load Balancer to distribute incoming traffic across multiple EC2 instances. Define listeners and routing rules.

1. Select ALB
   <img width="534" height="562" alt="ALB" src="https://github.com/user-attachments/assets/9d744f97-0802-4788-963e-4afd9b1aafdd" />
2. ALB Configuration
3. 
   <img width="347" height="806" alt="ALB-setup" src="https://github.com/user-attachments/assets/b5292866-cc06-4414-af1e-b2f9f89db070" />
5. Launch Template Creation:
Create a launch template to define the configuration settings for the EC2 instances launched by the autoscaling group.
1. Choose an AMI from the Catalog
   <img width="932" height="806" alt="Launch-temp1" src="https://github.com/user-attachments/assets/d96276f2-0b2f-484a-9d53-2633ee373a38" />
2. Select the preferred instance from the Instance type
   <img width="932" height="806" alt="launch-temp2" src="https://github.com/user-attachments/assets/0ce8bce8-c363-4da4-8b83-58579b3eb7e6" />
3. On Advance details scroll to the User data and paste the user data provided.
   <img width="932" height="806" alt="Launch-temp3" src="https://github.com/user-attachments/assets/2de28e60-79d7-47d4-927d-eac219f9ff05" />
6.Autoscaling Group Configuration:
Configure an autoscaling group to automatically adjust the number of EC2 instances based on metrics such as CPU utilization or network traffic.
Associate the autoscaling group with the launch template and target group.
<img width="932" height="806" alt="ASG1" src="https://github.com/user-attachments/assets/017a75fd-bb63-4fbe-97a9-eeb71c6cdec0" />
<img width="932" height="806" alt="ASG2" src="https://github.com/user-attachments/assets/28aa3273-9cfa-426a-a44b-0009b76ba00e" />
<img width="709" height="806" alt="ASG3" src="https://github.com/user-attachments/assets/b4a48b61-9740-421a-bc81-03103ae02b24" />
<img width="932" height="806" alt="ASG4" src="https://github.com/user-attachments/assets/c5553421-0ef6-4126-9a94-fefae3c01433" />






