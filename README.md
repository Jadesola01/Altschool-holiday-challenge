# Altschool-holiday-challenge
setting up an Application Load Balancer on AWS

## Task
* Set up 2 EC2 instances on AWS(use the free tier instances).
* Deploy an Nginx web server on these instances(you are free to use Ansible)
* Set up an ALB(Application Load balancer) to route requests to your EC2 instances
* Make sure that each server displays its own Hostname or IP address. You can use any programming language of your choice to display this.

# Create VPC

create a vpc on the vpc dashboard

![vpc dashboard](https://user-images.githubusercontent.com/102290896/211640476-4ca2c57e-1300-4d71-ad40-c456efd874d0.jpeg)

# create Ec2 Instances

create 2 Ec2 instances using the Ec2 dasboard and assign the vpc and Private subnets created

![Ec2 instance with private subnets](https://user-images.githubusercontent.com/102290896/211649698-71b9ec8a-e9c8-4afc-a7ea-da5dfe0a7d2e.jpeg)

# Create a Bastion Host

create a bastion host assigning the same vpc and a public subnet

![Bastion Host with public subnet](https://user-images.githubusercontent.com/102290896/211650841-6d58db64-3e34-4fb8-b089-59d5ffd708ce.jpeg)

# Connect to the Bastion Host using SSH client on AWS 
Connect the bastion host and follow the instructions when you click on the ssh client 

 ![SSH connection](https://user-images.githubusercontent.com/102290896/211656035-e269244a-dc82-4af0-b764-d5193107786f.jpeg)


# Access the bastion host via ssh through the terminal
connect the bastion host to your terminal using the key-pair you generated 

![bastion host via ssh](https://user-images.githubusercontent.com/102290896/211657760-19ad7040-eef4-41c8-8576-896f1beb40d9.png)

# Connect server-1 and server-2 using the bastion host and configure the nginx server on both instances 

connect server-1 via the bastion host and install and configure your Nginx server using the command: 

`$ sudo apt-get install nginx -y`

![Installing Nginx server](https://user-images.githubusercontent.com/102290896/211659239-3a63deec-a31f-4e1d-8c88-4fee92454585.png)

# Install php8.1-fpm 

install the php8.1 version using the command 

`$ sudo apt-get install php8.1-fpm `

![php installation](https://user-images.githubusercontent.com/102290896/211660529-53ad42fa-7096-438c-b172-b810c049a2d6.png)

# Edit the Nginx configuration file 

Edit the Nginx config file to accomodate the php files

`$ sudo nano /etc/nginx/sites-available/default`

![Nginx config file](https://user-images.githubusercontent.com/102290896/211662081-4e2d72fd-bdd1-4e01-8776-03e393012316.png)

# create an index.php file in your root directory 

`$ cd /var/www/html/`

`$ sudo nano index.php`

![index php file  ](https://user-images.githubusercontent.com/102290896/211663780-68b6f715-b3d4-480b-b197-f31474870744.png)

# Restart your Nginx server 

restart and check the status of your Nginx server to ensure it runs properly 

`$ sudo systemctl restart nginx`

`$ sudo systemctl status nginx`

![Nginx status](https://user-images.githubusercontent.com/102290896/211664624-a664c0af-68b3-4d7f-9af8-395902927a5e.png)

# Create Target Group 

Navigate to the target group and create a target group to assign your instances and connect to your Loab Balancer 

![Target Group](https://user-images.githubusercontent.com/102290896/211665502-aabaf3c7-cce5-4297-b8c3-6b086e6b27b5.jpeg)


# create an Application load balancer 

Create an application load balancer and edit the inbound security groups to allow HTTP/S traffic from annywhere. also add the target group to the listeners and routing section then create the load balancer 

![Load balancer ](https://user-images.githubusercontent.com/102290896/211666541-adc8fef7-2f05-403a-b1ba-8c88006b95dc.jpeg)

# Esure your Target groups are active 

Confirm the health status of your target groups. 

![Health check](https://user-images.githubusercontent.com/102290896/211667227-53bce7ca-a94c-4d89-a082-886ea4b3f973.jpeg)


# Test to see your servers are working 

Copy the domain name on your Load balancer and load it in your browser. 

![server-1](https://user-images.githubusercontent.com/102290896/211668417-00e27e47-389f-4d67-8f0e-c8713006dbf4.jpeg)


![server-2](https://user-images.githubusercontent.com/102290896/211668704-0f302511-676d-4f05-9fee-d3e66b2a3db4.jpeg)














