# NetworkingNginxAssignment
I will be showing you how to deploy a web server using a EC2 instance with Nginx installed on it and connecting it to a domain using AWS Route53.

Prequsities
- AWS Account

## Step 1 Route53

- Purchase a domain on AWS Route53, can be whichever one you want depending on budget.
- Once purchased, we will come back to this in a later step.

## Step 2 Creating EC2 Instance

- Create an EC2 Instance and use the following configurations

- Chose Ubuntu as the AMI

- Select t2.micro (Free Tier)

- Create an SSH key pair (ssh will allow you to remotely connect to your ec2)

- Configured the security group allowing:

- SSH (22) from my IP 

- HTTP (80) from anywhere (page open for the public then)

- Launched the instance and noted its public IPv4 address
<img width="1441" height="174" alt="image" src="https://github.com/user-attachments/assets/7f7a1099-409c-4cdd-8041-ea08e59db3bf" />

## Step 3 Installing NGINX on our EC2 Instance

- Need to connect into the EC2 by performing ssh -i "path/to/key.pem" ubuntu@ec2-3-10-199-22.eu-west-2.compute.amazonaws.com

- Update and Install NGINX with these commands

   -sudo apt update -y

   -sudo apt install nginx -y

   -sudo systemctl start nginx

   -sudo systemctl enable nginx

## Step 4 DNS Setup

- This step, we need to create a record in Route53

- Go to Hosted zones and click on your DNS

- Click on create record and put in your ip address in - This is basically mapping your domain to your ec2 public ip.

- <img width="1286" height="352" alt="image" src="https://github.com/user-attachments/assets/2000891e-996c-4331-b301-53b00d3abb76" />

## Step 5 Testing 

- Now, with these domain mapped to our EC2, we can now enter our domain and our web page should appear.

