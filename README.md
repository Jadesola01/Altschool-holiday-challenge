# Altschool-holiday-challenge
setting up an Application Load Balancer on AWS

## Task
* Set up 2 EC2 instances on AWS(use the free tier instances).
* Deploy an Nginx web server on these instances(you are free to use Ansible)
* Set up an ALB(Application Load balancer) to route requests to your EC2 instances
* Make sure that each server displays its own Hostname or IP address. You can use any programming language of your choice to display this.

# Create VPC
create a vpc on the vpc dashboard
![] (![vpc dashboard](https://user-images.githubusercontent.com/102290896/211640476-4ca2c57e-1300-4d71-ad40-c456efd874d0.jpeg)

# create Ec2 Instances 
create 2 Ec2 instances using the Ec2 dasboard and assign the vpc and Private subnets created
![] (![Ec2 instance with private subnets](https://user-images.githubusercontent.com/102290896/211649698-71b9ec8a-e9c8-4afc-a7ea-da5dfe0a7d2e.jpeg)

# Create a Bastion Host
create a bastion host assigning the same vpc and a public subnet
![ ] (![Bastion Host with public subnet](https://user-images.githubusercontent.com/102290896/211650841-6d58db64-3e34-4fb8-b089-59d5ffd708ce.jpeg)

# Connect to the Bastion Host using SSH client on AWS 
![] (![SSH connection](https://user-images.githubusercontent.com/102290896/211656035-e269244a-dc82-4af0-b764-d5193107786f.jpeg)
)

# Access the bastion host via ssh through the terminal
![] (![bastion host via ssh](https://user-images.githubusercontent.com/102290896/211657760-19ad7040-eef4-41c8-8576-896f1beb40d9.png)






