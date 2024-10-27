# Creating-an-Amazon-Virtual-Private-Cloud
Creating an Amazon Virtual Private Cloud.



VPC'S are isolated sections of the AWS Cloud that help keep my AWS resources private and secure.
There was already a default VPC in my account ever since my AWS account was created. This is because AWS has set up a default VPC to allow me to deploy resources like EC2 instances or RDS databases right away without having to create my own VPC from scratch.


TO SET UP MY VPC--Step 1
i had to define an IPV4 CIDR, which means a range of IP addresses that my VPC can allocate to the resources deployed into my VPC. 

CREATION OF THE SUBNET--Step 2
Subnets are subsections of my VPC, just like how neighbourhoods are subsections of a city.
There are already subnets existing in my account, one for every availability zone in the region that I set up my VPC in. Since my region is Oregon(US-west-2), which has 4 availability zones. I have 4 default subnets already.
I named my subnet Public 1, but that doesn't automatically make my subnet a public subnet. For a subnet to be considered public, it needs to have a route to an Internet gateway

CREATION OF THE INTERNET GATEWAY--Step 3
Internet gateways are the key VPC components that allow internet access for the resources in my VPC/subnet. An internet gateway is also how users in the public can access my resources in a public subnet.
Attaching an internet gateway to a VPC means resources in your VPC can now access the internet. The EC2 intances with public IP addresses also become accessible to users, so your application hosted on those servers become public too
While i set up an Internet gateway I attached it to a VPC and still have to set up route tables. Route tables will help ec2 instances/resources in my VPC to find their way to the internet gateway attached to my VPC- otherwise even if that connection has been established between my VPC and the internet gateway, my ec2 instances would still struggle to access the internet.


